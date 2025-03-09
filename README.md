# hacker-terminal
"Professional Hacker Terminal Simulation"
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hacker Terminal</title>
    <style>
        body {
            background-color: black;
            color: #33ff33;
            font-family: 'Courier New', monospace;
            text-align: center;
            overflow: hidden;
            margin: 0;
            padding: 0;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        h1 {
            text-shadow: 0 0 10px #33ff33;
            font-size: 3em;
            animation: flicker 1.5s infinite alternate;
            margin-bottom: 10px;
        }
        @keyframes flicker {
            0% { opacity: 1; }
            50% { opacity: 0.7; }
            100% { opacity: 1; }
        }
        .terminal {
            background: black;
            color: #33ff33;
            width: 95%;
            height: 80vh;
            padding: 10px;
            border: 1px solid #33ff33;
            text-align: left;
            overflow-y: auto;
            font-family: monospace;
            white-space: pre-wrap;
        }
    </style>
</head>
<body>
    <h1>HACKER TERMINAL</h1>
    <div class="terminal" id="terminal"></div>
    <script>
        const fakeCommands = [
            "echo 'Hacking session started'",
            "ping -c 4 192.168.1.1",
            "nmap -sV -A 192.168.1.1",
            "cat /etc/passwd",
            "whoami",
            "ifconfig | grep inet",
            "netstat -tulnp",
            "sudo apt update && sudo apt upgrade -y",
            "curl -X GET https://example.com/api/data",
            "git clone https://github.com/example/repo.git",
            "ls -la /var/www/html/",
            "chmod +x script.sh && ./script.sh",
            "exit"
        ];
        
        function typeCommand(index) {
            if (index < fakeCommands.length) {
                let terminal = document.getElementById("terminal");
                let output = document.createElement("p");
                output.innerText = "$ " + fakeCommands[index];
                terminal.appendChild(output);
                terminal.scrollTop = terminal.scrollHeight;
                
                setTimeout(() => typeCommand(index + 1), 150);
            }
        }
        
        document.addEventListener("DOMContentLoaded", () => {
            setTimeout(() => typeCommand(0), 100);
        });
    </script>
</body>
</html>
