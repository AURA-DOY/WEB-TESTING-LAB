# ⬡ VulnLabs — Browser-Based Web Security Training

> A fully **client-side** vulnerable web application for practicing real-world web security attacks.  
> No Docker. No server. No install. Just open the HTML file and start hacking.

![Static Badge](https://img.shields.io/badge/author-AURA-DOY-00ff88?style=flat-square)
![Static Badge](https://img.shields.io/badge/type-CTF%20%2F%20Training-00ff88?style=flat-square)
![Static Badge](https://img.shields.io/badge/stack-HTML%20%2F%20JS-00aaff?style=flat-square)
![Static Badge](https://img.shields.io/badge/server-none%20required-ffcc00?style=flat-square)
![Static Badge](https://img.shields.io/badge/license-All%20Rights%20Reserved-ff4455?style=flat-square)

---

## What is VulnLabs?

VulnLabs is a single-file intentionally vulnerable web app built for security students, bug bounty hunters, and pentesters who want to practice attacking web vulnerabilities in a safe, local, offline environment.

Every lab simulates vulnerabilities you'll find on real bug bounty programs and pentests — with a built-in **CTF flag system** that tracks your progress as you exploit each one.

---

## Labs Included

| # | Lab | Techniques Covered | Difficulty |
|---|-----|--------------------|------------|
| 01 | **SQL Injection** | Login bypass, UNION extraction, blind boolean | 🟢 Beginner |
| 02 | **XSS** | Reflected, Stored, DOM-based, cookie theft | 🟢 Beginner |
| 03 | **Auth Bypass** | Default creds, JWT alg:none, password reset flaw, cookie tamper | 🟢 Beginner |
| 04 | **File Upload** | MIME bypass, double extension, null byte, web shell exec | 🟡 Intermediate |
| 05 | **Command Injection** | `;` `&&` `\|` backtick and `$()` subshell injection | 🟡 Intermediate |
| 06 | **IDOR** | Accessing other users' data by changing object IDs | 🟢 Beginner |
| 07 | **CSRF** | Forged cross-origin requests, no token validation | 🟢 Beginner |
| 08 | **LFI / Path Traversal** | `../` traversal, `/etc/passwd`, `php://filter` wrapper | 🟡 Intermediate |
| 09 | **XXE Injection** | External entity file read, SSRF via XML | 🟡 Intermediate |
| 10 | **SSTI** | Jinja2 `{{7*7}}`, config dump, RCE chain | 🔴 Advanced |
| 11 | **Open Redirect** | External redirect, `javascript:` XSS, `//` bypass | 🟢 Beginner |

---

## Features

- 🚩 **CTF Flag System** — capture flags as you exploit each vulnerability
- 💉 **Payloads Actually Execute** — XSS fires, command injection shows output, IDOR leaks real data
- 🧠 **Hints Built In** — every lab has a hint box with payloads to try
- 🗃️ **Simulated Database** — users, products, sessions all in-memory JS
- 🎨 **Hacker Terminal UI** — dark theme, monospace fonts, scanline effect
- 📴 **100% Offline** — no network requests, no backend, no dependencies

---

## Deployment

### Option 1 — Just Open It (Easiest)

```bash
# Clone the repo
git clone https://github.com/AURA-DOY/WEB-TESTING-LAB
cd vulnlabs

# Open directly in browser

# On Linux / Kali:
xdg-open vuln-labs.html

# On macOS:
open vuln-labs.html

# On Windows:
start vuln-labs.html
```

That's it. The file runs entirely in your browser with zero dependencies.

---

### Option 2 — Serve via Python (Recommended)

```bash
git clone https://github.com/AURA-DOY/WEB-TESTING-LAB
cd vulnlabs

# Python 3
python3 -m http.server 8080

# Then open:
# http://localhost:8080/vuln-labs.html
```

---

### Option 3 — Serve via PHP

```bash
git clone https://github.com/AURA-DOY/WEB-TESTING-LAB
cd vulnlabs

php -S localhost:8080

# Then open:
# http://localhost:8080/vuln-labs.html
```

---

### Option 4 — Serve via Node.js

```bash
git clone https://github.com/AURA-DOY/WEB-TESTING-LAB
cd vulnlabs

npx serve .

# Then open the URL shown in terminal
```

---

### Option 5 — Kali Linux Quick Start

```bash
git clone https://github.com/AURA-DOY/WEB-TESTING-LAB
cd vulnlabs
python3 -m http.server 8080 &
firefox http://localhost:8080/vuln-labs.html
```

---

## Usage

1. Open `vuln-labs.html` in any modern browser
2. Pick a lab from the home screen or top navigation
3. Read the **hint box** for payload suggestions
4. Enter payloads in the input fields and observe the output
5. Capture flags — each successful exploit awards a 🚩 flag shown in the bottom bar
6. Try to capture all flags!

---

## Example Payloads to Get Started

### SQL Injection — Login Bypass
```
Username: admin'--
Password: anything
```

### XSS — Reflected
```html
<script>alert(document.cookie)</script>
<img src=x onerror=alert(1)>
<svg onload=alert('XSS')>
```

### JWT — alg:none Bypass
```
eyJhbGciOiJub25lIn0.eyJ1c2VyIjoiYWRtaW4iLCJyb2xlIjoiYWRtaW4ifQ.
```

### LFI — Path Traversal
```
../../../../etc/passwd
php://filter/convert.base64-encode/resource=config
```

### Command Injection
```
127.0.0.1; whoami
127.0.0.1 && cat /etc/passwd
127.0.0.1 | id
```

### SSTI — Jinja2 Detection
```
{{7*7}}
{{config}}
```

---

## Who Is This For?

- 🎓 Students learning web security for the first time
- 🐛 Bug bounty hunters practicing techniques offline
- 🔐 Pentesters warming up before an engagement
- 👨‍🏫 Instructors who need a zero-setup demo environment
- 🏆 CTF players practicing common web challenge categories

---

## Disclaimer

> **This tool is for educational purposes only.**  
> All vulnerabilities are simulated in a safe browser sandbox.  
> Only use these techniques on systems you own or have explicit written permission to test.  
> The author is not responsible for any misuse of this tool.

---

## Copyright & License

```
Copyright (c) 2026 AURA-DOY (https://github.com/AURA-DOY)
All Rights Reserved.

This project and all of its contents — including but not limited to
source code, design, UI, lab structure, and documentation — are the
exclusive intellectual property of AURA-DOY.

You MAY:
  - Use this tool for personal, educational, and non-commercial purposes
  - Fork the repository for personal use
  - Share the original repository link

You MAY NOT:
  - Redistribute, republish, or repackage this tool as your own
  - Claim authorship or ownership of this project or any part of it
  - Use this project in commercial products or services without
    explicit written permission from the author
  - Remove or alter this copyright notice

Unauthorized use, reproduction, or distribution of this work,
in whole or in part, may result in legal action.

For permissions beyond the scope of this license, contact:
https://github.com/AURA-DOY
```

---

## Contributing

Pull requests welcome! Ideas for new labs:

- WebSockets injection
- Prototype pollution
- Race conditions
- NoSQL injection
- Deserialization
- GraphQL attacks
- CORS misconfiguration

---

⭐ If this helped you learn something, drop a star — it helps others find it!

*Made with 🖤 by [AURA-DOY](https://github.com/AURA-DOY)*
