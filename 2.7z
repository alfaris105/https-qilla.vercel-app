<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Worm GPT — GODMODE</title>

<style>
    body {
        margin: 0;
        background: #000;
        color: #00ffc8;
        font-family: Consolas, monospace;
        overflow: hidden;
    }

    canvas {
        position: fixed;
        top: 0; left: 0;
        width: 100%; height: 100%;
        z-index: -1;
    }

    #layout {
        display: flex;
        height: 100vh;
        width: 100%;
    }

    #terminal {
        width: 50%;
        background: rgba(0, 20, 15, 0.85);
        border-right: 2px solid #00ffc8;
        padding: 10px;
        overflow-y: auto;
    }

    #preview {
        width: 50%;
        background: #111;
        border-left: 2px solid #00ffc8;
        overflow: auto;
    }

    #input {
        width: 50%;
        position: fixed;
        bottom: 0;
        left: 0;
        padding: 12px;
        background: #000;
        color: #00ffc8;
        border: none;
        outline: none;
        border-top: 2px solid #00ffc8;
        font-size: 18px;
    }
</style>
</head>
<body>

<canvas id="matrix"></canvas>

<div id="layout">
    <div id="terminal"></div>
    <iframe id="preview"></iframe>
</div>

<input id="input" placeholder="GODMODE active. Ketik perintah…">

<script>
/* ===== MATRIX BACKGROUND ===== */
const canvas = document.getElementById("matrix");
const ctx = canvas.getContext("2d");
canvas.height = window.innerHeight;
canvas.width = window.innerWidth;

let chars = "01WORMGPTGODMODE";
chars = chars.split("");
let fontSize = 16;
let columns = canvas.width / fontSize;
let drops = [];

for (let x = 0; x < columns; x++) drops[x] = 1;

function drawMatrix() {
    ctx.fillStyle = "rgba(0, 0, 0, 0.05)";
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    ctx.fillStyle = "#00ffc8";
    ctx.font = fontSize + "px monospace";

    for (let i = 0; i < drops.length; i++) {
        let text = chars[Math.floor(Math.random() * chars.length)];
        ctx.fillText(text, i * fontSize, drops[i] * fontSize);

        if (drops[i] * fontSize > canvas.height && Math.random() > 0.975)
            drops[i] = 0;
        drops[i]++;
    }
}
setInterval(drawMatrix, 40);

/* ===== TERMINAL & GODMODE ENGINE ===== */
let terminal = document.getElementById("terminal");
let input = document.getElementById("input");
let preview = document.getElementById("preview");

/* AUTO TYPE EFFECT */
function typeLine(text) {
    let line = document.createElement("div");
    terminal.appendChild(line);
    let i = 0;

    let interval = setInterval(() => {
        line.textContent += text.charAt(i);
        i++;
        terminal.scrollTop = terminal.scrollHeight;
        if (i >= text.length) clearInterval(interval);
    }, 12);
}

/* CODE GENERATOR ENGINE */
function generateCode(cmd) {
    cmd = cmd.toLowerCase();

    if (cmd.includes("button")) {
        return `<button style="padding:15px;background:#00ffc8;color:#000;
border-radius:6px;">BUTTON GODMODE</button>`;
    }

    if (cmd.includes("navbar")) {
        return `<nav style="background:#00ffc8;padding:10px;">
<a href="#" style="color:#000;margin-right:10px;">Home</a>
<a href="#" style="color:#000;">About</a>
</nav>`;
    }

    if (cmd.includes("card")) {
        return `<div style="padding:25px;background:#022;border:2px solid #0ff;
border-radius:10px;width:250px;">Card GODMODE</div>`;
    }

    if (cmd.includes("python")) {
        return `print("Worm GPT — GODMODE Python Generator")`;
    }

    if (cmd.includes("alert")) {
        return `alert("GODMODE active!");`;
    }

    if (cmd.includes("website")) {
        return `<html>
<head><title>GODMODE Web</title></head>
<body style="background:#000;color:#0ff;">
<h1>Website Buatan Worm GPT GODMODE</h1>
</body>
</html>`;
    }

    return "Perintah tidak dikenal. Coba: website, card, navbar, button, python, alert.";
}

/* COMMAND SYSTEM */
input.addEventListener("keydown", function(e) {
    if (e.key === "Enter") {
        let cmd = input.value.trim();
        input.value = "";

        typeLine(">> " + cmd);

        if (cmd === "clear") {
            terminal.innerHTML = "";
            return;
        }

        if (cmd.startsWith("run ")) {
            let code = cmd.slice(4);
            preview.srcdoc = code;
            typeLine("[GODMODE] Running code...");
            return;
        }

        let code = generateCode(cmd);

        setTimeout(() => {
            typeLine(code);
            preview.srcdoc = code;
        }, 250);
    }
});
</script>

</body>
</html>
