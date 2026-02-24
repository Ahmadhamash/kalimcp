# 🔐 Pentest MCP Server

MCP server for web penetration testing, built on Kali Linux Docker.  
Works with **Gemini CLI** and **Claude Desktop**.

## ⚡ Quick Start (Windows)

### Requirements
- [Docker Desktop](https://www.docker.com/products/docker-desktop) (must be running)
- [Gemini CLI](https://github.com/google-gemini/gemini-cli) installed

### One-click setup

```bash
git clone https://github.com/Ahmadhamash/kalimcp.git
cd kalimcp
cd pentest-mcp
setup.bat
```

That's it. The script will:
1. Build the Docker image
2. Add pentest-tools to your Gemini CLI config automatically

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

---

## Manual Setup (Linux/Mac)

```bash
# Build image
docker build -t pentest-mcp:latest .

# Add to Gemini config
mkdir -p ~/.gemini
# Edit ~/.gemini/settings.json and add pentest-tools block (see gemini_cli_config.json)
```
