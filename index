<!DOCTYPE html>
<html lang="hu">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CRITICAL SYSTEM FAILURE</title>

<style>
body {
    margin: 0;
    background: black;
    color: #00ff00;
    font-family: "Courier New", monospace;
    height: 100vh;
    display: flex;
    flex-direction: column;
    overflow: hidden;
    animation: screenFlash 0.15s infinite;
}

@keyframes screenFlash {
    0% { background: black; }
    50% { background: #300000; }
    100% { background: black; }
}

#terminal {
    flex: 1;
    padding: 15px;
    font-size: 4vw;
    white-space: pre-line;
    overflow-y: auto;
    animation: shake 0.12s infinite;
}

@keyframes shake {
    0% { transform: translate(0); }
    25% { transform: translate(-3px,2px); }
    50% { transform: translate(3px,-2px); }
    75% { transform: translate(-2px,-3px); }
    100% { transform: translate(0); }
}

.alert {
    position: fixed;
    inset: 0;
    background: rgba(255,0,0,0.2);
    animation: alertFlash 0.25s infinite;
    pointer-events: none;
}

@keyframes alertFlash {
    0% { opacity: 0; }
    50% { opacity: 1; }
    100% { opacity: 0; }
}

#redButton {
    display: none;
    position: fixed;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 6vw;
    padding: 20px 40px;
    background: red;
    color: white;
    border: none;
    border-radius: 15px;
    box-shadow: 0 0 40px red;
    animation: buttonFlash 0.15s infinite;
    z-index: 50;
}

@keyframes buttonFlash {
    0% { background: red; }
    50% { background: darkred; }
    100% { background: red; }
}

/* HACK ABLAKOK */
.hack-window {
    position: fixed;
    width: 80vw;
    max-width: 340px;
    background: #020202;
    border: 2px solid #00ff00;
    box-shadow: 0 0 25px #00ff00;
    color: #00ff00;
    padding: 10px;
    z-index: 30;
    font-size: 3.5vw;
    animation: glitchIn 0.25s ease, flicker 0.2s infinite;
}

.hack-window.red {
    border-color: red;
    color: red;
    box-shadow: 0 0 25px red;
}

.hack-title {
    font-weight: bold;
    border-bottom: 1px solid currentColor;
    margin-bottom: 6px;
}

@keyframes glitchIn {
    from { opacity: 0; transform: scale(0.7); }
    to { opacity: 1; transform: scale(1); }
}

@keyframes flicker {
    0% { opacity: 1; }
    50% { opacity: 0.75; }
    100% { opacity: 1; }
}

#reveal {
    display: none;
    position: fixed;
    inset: 0;
    background: black;
    color: white;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    z-index: 100;
}

#reveal img {
    max-width: 70vw;
    border-radius: 20px;
    box-shadow: 0 0 40px white;
}

#reveal h1 {
    font-size: 8vw;
}
</style>
</head>

<body>

<div class="alert"></div>
<div id="terminal"></div>

<button id="redButton">🚨 ABORT LAUNCH 🚨</button>

<div id="reveal">
    <h1>Nyugi, csak én voltam 😘</h1>
</div>

<script>
const terminal = document.getElementById("terminal");
const button = document.getElementById("redButton");
const reveal = document.getElementById("reveal");


const lines = [
"!!! CRITICAL SYSTEM BREACH !!!",
"Bypassing firewall...",
"Injecting malicious payload...",
"Root access granted",
"Tracking device location...",
"Accessing camera feed...",
"Downloading personal files...",
"██████████████████ 100%",
"",
"MISSILE LAUNCH SEQUENCE ARMED",
"TARGET LOCKED",
"",
"!!! MANUAL ABORT REQUIRED !!!"
];

let i = 0;

function chaos() {
    if (i < lines.length) {
        terminal.innerHTML += lines[i] + "\n";
        terminal.scrollTop = terminal.scrollHeight;
        i++;
        setTimeout(chaos, 150);
    } else {
        button.style.display = "block";
        startHackWindows();
    }
}
chaos();

/* HACK ABLAKOK LOGIKA */
const hackMessages = [
{t:"FIREWALL", m:"BREACHED"},
{t:"GPS", m:"LOCATION LOCKED"},
{t:"KERNEL", m:"OVERRIDE ACTIVE"},
{t:"CAMERA", m:"LIVE FEED STREAMING"},
{t:"DATA", m:"EXFILTRATION 87%"},
{t:"WARNING", m:"UNAUTHORIZED ACCESS"}
];

function spawnHackWindow() {
    const d = document.createElement("div");
    const msg = hackMessages[Math.floor(Math.random()*hackMessages.length)];

    d.className = "hack-window" + (Math.random() > 0.6 ? " red" : "");
    d.style.top = Math.random()*65 + "vh";
    d.style.left = Math.random()*10 + "vw";

    d.innerHTML = `
        <div class="hack-title">${msg.t}</div>
        <div>${msg.m}</div>
        <div>0x${Math.random().toString(16).slice(2,10)}</div>
    `;

    document.body.appendChild(d);
    setTimeout(()=>d.remove(), 2500);
}

function startHackWindows() {
    setInterval(spawnHackWindow, 600);
}

button.onclick = () => {
    reveal.style.display = "flex";
    if (sound) sound.play();
    if (navigator.vibrate) navigator.vibrate([300,100,300,100,500]);
};
</script>

</body>
</html>
