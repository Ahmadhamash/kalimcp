# 🔐 Pentest MCP Server

MCP server for web penetration testing, built on Kali Linux Docker.  
Works with **Gemini CLI** and **Claude Desktop**.

## ⚡ Quick Start

### Requirements
- [Docker Desktop](https://www.docker.com/products/docker-desktop) must be running
- [Gemini CLI](https://github.com/google-gemini/gemini-cli) installed

---

### Step 1 — Clone the repo
```bash
git clone https://github.com/YOUR_USERNAME/pentest-mcp.git
cd pentest-mcp
```

---

### Step 2 — Build the Docker image
```bash
docker build -t pentest-mcp:latest .
```
> ⏳ First time takes 5-10 minutes

---

### Step 3 — Edit Gemini CLI config

Open:
```
C:\Users\<YOUR_NAME>\.gemini\settings.json
```

Add `pentest-tools` inside `mcpServers`:
```json
{
  "mcpServers": {
    "pentest-tools": {
      "command": "docker",
      "args": [
        "run", "--rm", "-i",
        "--cap-add", "NET_RAW",
        "--cap-add", "NET_ADMIN",
        "-e", "MAX_TIMEOUT=300",
        "pentest-mcp:latest"
      ],
      "timeout": 360000,
      "trust": true
    }
  }
}
```

---

### Step 4 — Run Gemini CLI
```bash
gemini
```
Type `/mcp` to verify connection:
```
🟢 pentest-tools - connected
```

---

## 🛠️ Available Tools

| Tool | Description |
|------|-------------|
| `nmap_scan` | Port scanning + service detection |
| `nikto_scan` | Web vulnerability scanner |
| `sqlmap_scan` | SQL injection testing |
| `wpscan_scan` | WordPress vulnerability scanner |
| `dirb_scan` | Directory brute-forcing |
| `searchsploit_query` | Search Exploit-DB for known CVEs |
| `whatweb_scan` | Web technology fingerprinting |
| `full_web_recon` | Full recon pipeline (nmap + whatweb) |

---

## 💬 Example Prompts

```
run full recon on http://your-site.com
scan with nikto: http://your-site.com
run sqlmap on http://your-site.com/page.php?id=1
search exploits for apache 2.4
run wpscan on http://your-wordpress-site.com
```

---

## ⚠️ Legal Disclaimer

This tool is for **educational purposes only**.  
Only use on systems you own or have explicit written permission to test.  
Unauthorized testing is illegal and unethical.
