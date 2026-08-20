# index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>System Diagnostic</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }
        body {
            background-color: #000000;
            color: #00ff66;
            font-family: 'Courier New', Courier, monospace;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 15px;
        }

        /* Terminal Screen View */
        #terminal-view {
            width: 100%;
            max-width: 450px;
            display: flex;
            flex-direction: column;
            gap: 8px;
            font-size: 14px;
        }

        .log-line {
            line-height: 1.3;
        }

        .red-text { color: #ff3333; }
        .green-text { color: #00ff66; }

        .progress-bar-container {
            width: 100%;
            height: 16px;
            background-color: #111;
            margin: 4px 0 10px 0;
            border-radius: 2px;
            overflow: hidden;
        }

        .progress-bar {
            height: 100%;
            width: 0%;
            background-color: #00ff66;
            box-shadow: 0 0 10px #00ff66;
            transition: width 0.1s linear;
        }

        /* Card Overlay View */
        #card-view {
            display: none;
            width: 100%;
            max-width: 360px;
            background-color: #080808;
            border: 2px solid #00ff66;
            border-radius: 8px;
            padding: 35px 20px;
            text-align: center;
            box-shadow: 0 0 25px rgba(0, 255, 102, 0.6), inset 0 0 15px rgba(0, 255, 102, 0.1);
        }

        .heart-icon {
            font-size: 48px;
            margin-bottom: 20px;
        }

        .card-title {
            color: #ff3366;
            font-size: 26px;
            font-weight: bold;
            letter-spacing: 1.5px;
            line-height: 1.2;
            margin-bottom: 25px;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
        }

        .card-text {
            color: #ffffff;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
            font-size: 15px;
            line-height: 1.6;
        }

        .card-text p {
            margin-bottom: 15px;
        }

        .highlight-green {
            color: #00ff66;
            font-size: 17px;
            font-weight: 600;
        }

        .btn-run {
            margin-top: 25px;
            background: transparent;
            color: #00ff66;
            border: 1px solid #00ff66;
            padding: 10px 24px;
            font-family: 'Courier New', Courier, monospace;
            font-size: 12px;
            letter-spacing: 1px;
            cursor: pointer;
            transition: all 0.2s ease;
        }

        .btn-run:hover {
            background-color: #00ff66;
            color: #000;
            box-shadow: 0 0 10px #00ff66;
        }
    </style>
</head>
<body>

    <div id="terminal-view"></div>

    <div id="card-view">
        <div class="heart-icon">❤️</div>
        <div class="card-title">SYSTEM<br>COMPROMISED</div>
        <div class="card-text">
            <p>Congratulations.</p>
            <p>Your device wasn't actually hacked...</p>
            <p class="highlight-green">I hacked your heart instead. 😏❤️</p>
            <p>And unfortunately for you...<br>there's no antivirus for that. 😂</p>
        </div>
        <button class="btn-run" onclick="resetHack()">RUN AGAIN</button>
    </div>

<script>
    const sequence = [
        { type: 'text', text: '> Initializing secure connection...' },
        { type: 'text', text: '> Connecting to remote server...' },
        { type: 'text', text: '> Connection established.' },
        { type: 'text', text: '> Scanning target...' },
        { type: 'text', text: '> Finding vulnerable ports...' },
        { type: 'text', text: '> Port 443 OPEN' },
        { type: 'text', text: '> Port 8080 OPEN' },
        { type: 'text', text: '> Bypassing firewall...' },
        { type: 'text', text: '> Firewall bypassed.' },
        { type: 'text', text: '> Accessing encrypted database...' },
        { type: 'text', text: '> Decrypting files...' },
        { type: 'progress', duration: 1000 },
        { type: 'text', text: '> Downloading secret files...' },
        { type: 'progress', duration: 1200 },
        { type: 'text', text: '> Analyzing personal data...' },
        { type: 'text', text: '> ERROR: Too much cuteness detected.', color: 'red-text' },
        { type: 'text', text: '> Attempting emergency override...' },
        { type: 'text', text: '> Override successful.' },
        { type: 'text', text: '> Searching for weakness...' },
        { type: 'text', text: '> WEAKNESS FOUND.', color: 'red-text' },
        { type: 'text', text: '> Target vulnerability: HEART ❤️', color: 'red-text' },
        { type: 'text', text: '> Injecting LOVE.exe...' },
        { type: 'progress', duration: 800 }
    ];

    const terminal = document.getElementById('terminal-view');
    const card = document.getElementById('card-view');

    async function startHack() {
        terminal.innerHTML = '';
        terminal.style.display = 'flex';
        card.style.display = 'none';

        for (const step of sequence) {
            if (step.type === 'text') {
                const div = document.createElement('div');
                div.className = `log-line ${step.color || ''}`;
                div.textContent = step.text;
                terminal.appendChild(div);
                await new Promise(r => setTimeout(r, 220));
            } else if (step.type === 'progress') {
                const container = document.createElement('div');
                container.className = 'progress-bar-container';
                const bar = document.createElement('div');
                bar.className = 'progress-bar';
                container.appendChild(bar);
                terminal.appendChild(container);

                await new Promise(r => {
                    setTimeout(() => { bar.style.width = '100%'; }, 50);
                    setTimeout(r, step.duration);
                });
            }
        }

        await new Promise(r => setTimeout(r, 600));
        terminal.style.display = 'none';
        card.style.display = 'block';
    }

    function resetHack() {
        startHack();
    }

    startHack();
</script>
</body>
</html>

