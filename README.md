  <div align="center">

  ### ☠️ &nbsp; CYBERSECURITY &nbsp; TOOLKIT &nbsp; B Y &nbsp; R O H I T &nbsp; ☠️
  
  </div>
  
  ---

  ## 🔍 Overview

  **Cybersecurity Toolkit** is a full-featured, browser-based offensive security command generation platform built with React 19 and TypeScript. Designed for bug bounty hunters, penetration testers, and security researchers who need instant, exploit-ready terminal commands without switching between documentation tabs, cheat sheets, or wikis.

  You enter your **target domain once**. The toolkit substitutes it across **2,900+ commands** spanning **99 attack categories** — from subdomain enumeration all the way to blockchain smart contract auditing, C2 framework setup, and MITRE ATT&CK mapping.

  Beyond command generation, the platform includes an AI assistant, AI-powered threat intelligence (Google Gemini + live Google Search), a D3.js network graph visualizer, real-time team collaboration via Socket.io, findings tracking, a penetration test report generator, Slack/Discord webhook integrations, and a full state export/import system — all running in the browser with full localStorage persistence.

  ---

  ## 🌐 Live Demo

  > **[https://cybersec-toolkit.netlify.app/](https://cybersec-toolkit.netlify.app/)**

  No installation. No account. Open in any browser and start.

  ---

  ## 🛠 Tech Stack

  | Layer | Technology |
  |---|---|
  | Framework | React 19 + TypeScript 5.8 |
  | Build Tool | Vite 6.2 |
  | Styling | Tailwind CSS v4 |
  | Animations | Motion (Framer Motion v12) |
  | Graph Visualization | D3.js v7 |
  | Local Database | Dexie v4 (IndexedDB wrapper) |
  | Real-time Collab | Socket.io v4 |
  | Backend | Express.js (Gemini API proxy) |
  | AI Integration | Google Gemini (`@google/genai`) |
  | Icons | Font Awesome |
  | Markdown Rendering | react-markdown v10 |
  | Deployment | Netlify |

  ---

  ## ⚙️ How It Works

  ```
  ┌──(root💀kali)-[~/targets]
  └─$ set-target

    TARGET ~> example.com            [EXECUTE]
              │
              ▼
    Domain sanitized (strips https://, trailing slashes)
              │
              ▼
    All 2,900+ commands updated with substitutions:
      DOMAIN            → example.com
      IP                → your configured attacker IP
      BURP              → your Burp Collaborator URL
      $TOKEN            → your auth token
      $GITHUB_TOKEN     → your GitHub PAT
      $JWT              → your JWT token
              │
              ▼
    Scrolls to categories section
    Browse → Search → Copy → Run in terminal
  ```

  Every copy action runs `processCommand()` which applies all six substitutions simultaneously before writing to clipboard.

  ---

  ## 🖥 UI & Interface

  ### Matrix Rain Background

  A full-canvas animated Matrix rain effect runs behind the entire UI. Characters are drawn from a combined pool of binary digits (`01`) and Japanese katakana (`アイウエオカキクケコ...ワヲン`). Each column rains at a random starting position with per-character brightness variation. The animation runs at 25fps and fully adapts to window resizes.

  ### Target Input Terminal

  The hero section renders a styled terminal window with macOS-style traffic-light dots and a `root@kali:~/recon` path in the titlebar. Inside, a Kali-style shell prompt (`┌──(root💀kali)-[~/targets]`) frames the input field, which is prefixed with `TARGET ~>` in red. Pressing `Enter` or clicking `EXECUTE` triggers command generation. The domain is automatically cleaned — `https://` prefixes and trailing slashes are stripped before substitution.

  ### Stats Bar

  Four live metric cards sit below the target input. All values are computed at runtime from the actual imported data — never hardcoded:

  | Stat | Value | Color |
  |---|---|---|
  | Categories | 99+ | Green |
  | Commands | 2900+ | Cyan |
  | Exploits | ∞ | Red |
  | Stealth | 100% | Yellow |

  ### Command Controls Toolbar

  Eight action buttons sit above the command listing:

  | Button | Action |
  |---|---|
  | `EXPAND` | Expands all 99 category accordions |
  | `COLLAPSE` | Collapses all category accordions |
  | `COPY ALL` | Copies every visible command to clipboard as a single block |
  | `EXPORT .SH` | Downloads a bash script of all expanded visible commands, organized by category with echo statements and a header |
  | `REPORT .MD` | Downloads a Markdown report of all ✅ completed commands with descriptions |
  | `ADD COMMAND` | Opens the custom command creation modal |
  | `HISTORY` | Opens the command history modal (last 50 copies) |
  | Category Jump Dropdown | Jumps directly to a specific category and expands it |

  A live search bar above these buttons filters all visible categories and commands in real time by tool name or command text.

  ### Category Filter Bar

  A horizontally-scrollable bar of pill buttons for instant category filtering:

  - **ALL** — shows all categories
  - **⭐ FAVORITES** — shows only starred commands
  - One pill per category (99 total), each colored with that category's unique accent color

  ### Command Cards

  Each tool inside a category renders as a card with:

  - **Tool name badge** — color-coded per category
  - **⭐ Favorite toggle** — star fills on click; persisted to localStorage; appears in FAVORITES filter
  - **✅ Complete toggle** — marks command as done; completed commands are included in `.md` report export
  - **📝 Note button** — opens a per-tool note editor; indicator turns blue when a note exists; notes persist across sessions
  - **COPY button** — appears on hover, colored per category; copies the fully processed command with your domain and variables substituted in; shows `COPIED!` checkmark for 2 seconds
  - **Command display** — full command in a dark terminal block with horizontal scroll for long strings
  - **Description** — one-line explanation of what the tool does

  ### Modals & Overlays

  **Add Custom Command**
  A form for creating personal command templates. Fields: command name, command template (supports `DOMAIN`, `IP`, `$TOKEN`, `$GITHUB_TOKEN`, `$JWT` placeholders), optional description. Saved commands appear in a dedicated **Custom Commands** category with the same favorite/complete/note/copy functionality.

  **Command History**
  Tracks the last 50 copied commands with category labels and timestamps. Features:
  - Text search across command content
  - Filter by category
  - Filter by date (today / this week / all time)
  - Clear all history button

  **AI Threat Intelligence**
  Full-screen modal (also on the navbar as **THREAT INTEL**). Powered by Google Gemini with live Google Search integration. Enter a query and receive real-time intelligence from live web results — formatted as Markdown with source citations. Requires a Gemini API key in Settings.

  **Note Editor**
  A per-tool textarea modal for saving observations, custom flags, reproductions steps, or partial findings during an engagement. Notes persist by tool name across sessions.

  **Global AI Assistant**
  Full-screen AI chat panel. Context-aware — knows your current target domain. Supports four backends simultaneously depending on which keys are configured: Gemini, OpenAI, Anthropic (Claude), Ollama (local).

  ---

  ## 🗂 All 99 Attack Categories

  Categories are defined across three source files (`commands.ts`, `commands2.ts`, `commands3.ts`) and merged into a single runtime array. The count and command totals below are computed directly from the source.

  ---

  ### Web Application Security

  | # | Category | What It Covers |
  |---|---|---|
  | 1 | **XSS Hunting** | Dalfox, XSStrike, Gxss, Kxss, Airixss, PwnXSS, XSpear — reflected, stored, DOM-based |
  | 2 | **SQL Injection** | SQLMap, Ghauri, NoSQLMap, DSSS, Blisqy — detection, enumeration, dump, WAF bypass |
  | 3 | **Sensitive File Discovery** | Hidden files, backup discovery, exposed `.git`, `.env`, config files |
  | 4 | **Parameter Discovery** | Arjun, ParamSpider, x8, Gau, Waybackurls, Hakrawler, Katana, GoSpider |
  | 5 | **Directory Bruteforce** | Ffuf, Gobuster, Feroxbuster, Dirb, Wfuzz, Dirsearch — dir, file, vhost modes |
  | 6 | **JavaScript Analysis** | SubJS, Mantra, LinkFinder, SecretFinder, JSFScan — endpoint and secret extraction |
  | 7 | **WordPress Testing** | WPScan, Droopescan, CMSMap, CMSeek, WPSeku, JoomScan, Magescan |
  | 8 | **API Security Testing** | Kiterunner, Photon, GraphQLMap, InQL, JWT Tool, RESTler |
  | 9 | **CORS Exploitation** | Corsy, CORSScanner — origin bypass, credential leakage |
  | 10 | **SSRF Exploitation** | SSRFMap, Gopherus, OOB detection, AWS metadata probing |
  | 11 | **Open Redirect** | OpenRedireX — parameter-based open redirect discovery |
  | 12 | **LFI / Path Traversal** | LFISuite, Kadimus, fimap — traversal payloads, PHP wrappers |
  | 13 | **Remote Code Execution** | Commix, Tplmap — SSTI, command injection, template injection |
  | 14 | **CRLF Injection** | CRLFuzz, CRLF-Injector — HTTP response splitting |
  | 15 | **XXE Injection** | XXEinjector — file read, SSRF via XML external entities |
  | 16 | **Security Headers** | shcheck — missing headers, CSP analysis, HSTS |
  | 17 | **WAF / 403 Bypass** | byp4xx, WafNinja, IdentYwaf, GoWAF, Wafw00f |
  | 18 | **HTTP Request Smuggling** | CL.TE and TE.CL desync detection and exploitation |
  | 19 | **Advanced Web Exploits** | ysoserial, phpggc, wstunnel — deserialization, WebSocket attacks |
  | 20 | **HTTP Desync** | Advanced HTTP/1 and HTTP/2 desync techniques |
  | 21 | **Cache Poisoning** | Web cache deception and poisoning |
  | 22 | **GraphQL Mutations** | GraphQL introspection, schema extraction, mutation-based exploitation |
  | 23 | **gRPC Tester** | gRPC endpoint enumeration and proto fuzzing |
  | 24 | **WebRTC Leaks** | WebRTC IP leak detection and bypass |
  | 25 | **CSP Bypass** | CSP header analysis and bypass techniques |

  ---

  ### Reconnaissance & OSINT

  | # | Category | What It Covers |
  |---|---|---|
  | 26 | **Subdomain Enumeration** | Subfinder, Amass, Assetfinder, Findomain, Chaos, crt.sh, Sublist3r, Knockpy, DNSRecon, Fierce, MassDNS, PureDNS, ShuffleDNS, GitHub-subdomains, Shodan, OneForAll, Sudomy, Censys, Rapid7 FDNS, Riddler, CertSpotter, ThreatCrowd, Crobat, Waybackurls, Gau, Hakrawler, DNSx, Altdns, Gotator, Cero, Tlsx, Gobuster DNS + advanced variants |
  | 27 | **ASN & IP Intelligence** | Amass Intel, BGPView, ASNMap, Metabigor, Shodan ASN, Censys ASN, WHOIS/RADB, IPInfo, Reverse IP, RIPE DB, Hurricane Electric, PeeringDB, IP2Location, MapCIDR, BGPQ4, Nmap ASN targets |
  | 28 | **Live Host Discovery** | Httpx, Httprobe, GoWitness, ZGrab2, Masscan, Nmap, WhatWeb, Wappalyzer, RustScan, Aquatone, EyeWitness |
  | 29 | **OSINT & Recon** | theHarvester, SpiderFoot, Shodan, Infoga, Recon-ng, OSINT Framework, EmailHarvester |
  | 30 | **Git Disclosure** | Gitleaks, TruffleHog, GitTools — secrets in repos, `.git` folder exposure |
  | 31 | **Subdomain Takeover** | Subjack, SubOver, DNSReaper, TKO-Subs — dangling DNS CNAME detection |
  | 32 | **Email Security** | SPF, DKIM, DMARC record analysis, email spoofing checks |
  | 33 | **Source Code Analysis** | Semgrep, Bandit, njsscan, Gosec, Brakeman — SAST across multiple languages |
  | 34 | **Dark Web Scraper** | Dark web monitoring for target-specific leaked data |
  | 35 | **APT Tracker** | Track APT group TTPs, indicators, and attribution |

  ---

  ### Network & Infrastructure

  | # | Category | What It Covers |
  |---|---|---|
  | 36 | **Port Scanning** | Nmap (full, stealth, UDP, scripts), Masscan, RustScan, Naabu, Smap, Unicornscan, ZMap, Sandmap |
  | 37 | **Network Infrastructure** | SNMP enumeration, SMB (smbclient), CrackMapExec, Responder |
  | 38 | **Wireless Security** | Aircrack-ng, Wifite, Reaver, Bully, Kismet, Bettercap, Wifiphisher, Fluxion |
  | 39 | **VoIP Security** | SIP enumeration, VoIP interception, VoIP-specific fuzzing |
  | 40 | **Network Forensics** | PCAP capture and analysis, traffic inspection, Wireshark commands |

  ---

  ### Cloud & Container Security

  | # | Category | What It Covers |
  |---|---|---|
  | 41 | **Cloud Security** | ScoutSuite, Prowler, Pacu, CloudMapper, Cloudsplaining, CloudFox, GCPBucketBrute, MicroBurst (Azure) |
  | 42 | **Container Auditing** | Trivy, Grype, Kube-Hunter, Kube-Bench, AmIContained — Docker/Kubernetes |
  | 43 | **Azure AD Enum** | Azure AD enumeration, user/group/role discovery, token abuse |
  | 44 | **AWS Lambda Sec** | Lambda function enumeration, event injection, role escalation |
  | 45 | **GCP Bucket Dump** | GCP storage bucket enumeration, ACL analysis, data extraction |
  | 46 | **Serverless Fuzz** | Serverless function endpoint discovery and input fuzzing |
  | 47 | **IaC Scanner** | Terraform, CloudFormation, Kubernetes manifest security scanning |

  ---

  ### Exploitation & Post-Exploitation

  | # | Category | What It Covers |
  |---|---|---|
  | 48 | **Vulnerability Scanning** | Nuclei, Jaeles, Nikto, ZAP, Wapiti, Arachni, Skipfish, OpenVAS, Sn1per |
  | 49 | **Privilege Escalation** | PEASS-ng (linpeas/winpeas), linux-exploit-suggester, Windows-Exploit-Suggester |
  | 50 | **Active Directory** | BloodHound, Mimikatz, Impacket, Kerbrute — kerberoasting, pass-the-hash, DCSync |
  | 51 | **C2 & Post Exploitation** | Metasploit, Sliver, Covenant, Merlin, Havoc |
  | 52 | **Cobalt Strike Profiles** | Malleable C2 profile generation for Cobalt Strike |
  | 53 | **Mythic C2** | Mythic framework agent setup, payload generation, task management |
  | 54 | **Sliver C2** | Sliver implant generation, mTLS/WireGuard C2 channels |
  | 55 | **Evasion Payloads** | AV/EDR bypass, payload obfuscation, AMSI bypass |
  | 56 | **LOLBins** | Living-off-the-land binary abuse for defense evasion and execution |
  | 57 | **Phishing Templates** | GoPhish, SET, Zphisher, BlackEye, HiddenEye, Evilginx2, Modlishka, King Phisher |
  | 58 | **Social Engineering** | GoPhish, SET, Evilginx2, Modlishka, Wifiphisher, Fluxion — phishing and WiFi SE |
  | 59 | **Mobile App Sec** | APKTool, dex2jar, Frida-tools, Objection, MobSF, JADX |

  ---

  ### Reverse Engineering & Forensics

  | # | Category | What It Covers |
  |---|---|---|
  | 60 | **Reverse Engineering** | Ghidra, Radare2, GDB with GEF + Pwndbg, ltrace, strace, binutils |
  | 61 | **Ghidra Scripts** | Ghidra headless analysis, script automation, decompiler workflows |
  | 62 | **IDA Python** | IDA Pro Python scripting, patching, analysis automation |
  | 63 | **Radare2 Cmds** | Disassembly, analysis, patching, emulation with Radare2 |
  | 64 | **Frida Scripts** | Dynamic instrumentation — function hooking, argument modification, return value patching |
  | 65 | **Objection Mobile** | Runtime iOS/Android app exploration — SSL unpinning, class dumps, method hooks |
  | 66 | **Assembly Analyzer** | x86/x64 assembly inspection and manual reversing |
  | 67 | **Digital Forensics** | Autopsy, Sleuthkit, Bulk Extractor, Foremost, Scalpel, ExifTool, Volatility |
  | 68 | **Memory Forensics** | Volatility — process listing, network connections, credential extraction from RAM dumps |
  | 69 | **Disk Forensics** | File system analysis, MFT parsing, deleted file recovery |
  | 70 | **Malware Analysis** | YARA, Cuckoo, PEiD — static analysis, sandbox detonation, signature matching |
  | 71 | **Malware Unpacking** | Packer detection, OEP finding, automated dump and fix |
  | 72 | **Ransomware Decrypt** | Known ransomware family decryptors and key extraction |
  | 73 | **Event Log Analysis** | Windows EVTX parsing, threat hunting in Security/System/Application logs |
  | 74 | **Timeline Analysis** | Attack timeline reconstruction from $MFT, prefetch, registry, and event logs |
  | 75 | **Stego Extract** | Steghide, Binwalk, zsteg, Stegsolve — hidden data extraction from images/audio |

  ---

  ### Cryptography & Blockchain

  | # | Category | What It Covers |
  |---|---|---|
  | 76 | **Cryptography & Hash Cracking** | Hashcat, John the Ripper, Hydra, Medusa, ncrack, hashid, CyberChef |
  | 77 | **RSA Analyzer** | Small exponent attack, common modulus, Wiener's attack, factorization |
  | 78 | **ECC Analyzer** | Weak curve detection, invalid curve attacks, ECDSA nonce reuse |
  | 79 | **Hash Cracker** | Rainbow table attacks, rule-based cracking, hybrid attacks across hash types |
  | 80 | **Smart Contract Audit** | Solidity vulnerability scanning — reentrancy, integer overflow, access control |
  | 81 | **DeFi Exploits** | Flash loan attacks, price oracle manipulation, sandwich attacks |
  | 82 | **Web3 Scanner** | dApp security testing, wallet interaction abuse, Web3 API exploitation |
  | 83 | **NFT Forensics** | NFT contract analysis, metadata tampering, ownership trace |

  ---

  ### Hardware & Wireless

  | # | Category | What It Covers |
  |---|---|---|
  | 84 | **Hardware & IoT Security** | Binwalk, Flashrom, OpenOCD, RouterSploit, Firmwalker, Firmadyne |
  | 85 | **Hardware Trojans** | Hardware backdoor detection, side-channel analysis basics |
  | 86 | **SDR Toolkit** | Software-defined radio security — signal capture, replay attacks |
  | 87 | **RFID Cloner** | RFID/NFC card reading, cloning, and emulation |
  | 88 | **Bluetooth Sec** | BLE scanning, device pairing exploitation, Bluetooth sniffing |
  | 89 | **WiFi Cracking** | WPA/WPA2 handshake capture, PMKID attack, dictionary cracking |

  ---

  ### Threat Detection & Intelligence

  | # | Category | What It Covers |
  |---|---|---|
  | 90 | **Threat Hunting** | IOC detection, log hunting queries, behavioral anomaly detection |
  | 91 | **AI Threat Hunting** | AI anomaly monitoring, adversarial prompt detection, data poisoning detection, model exfiltration monitoring |
  | 92 | **YARA Generator** | YARA rule writing for malware family signatures and IOC detection |
  | 93 | **Sigma Rules** | Sigma rule authoring for SIEM detection engineering |
  | 94 | **MITRE Mapper** | Map techniques and findings to MITRE ATT&CK TTP IDs |
  | 95 | **APT Tracker** | Known APT group tracking, TTP overlap analysis |

  ---

  ### Advanced & Specialized

  | # | Category | What It Covers |
  |---|---|---|
  | 96 | **Fuzzing** | Protocol fuzzing, parser fuzzing, mutation-based input generation |
  | 97 | **WAF Fingerprinting** | Wafw00f, IdentYwaf — WAF vendor identification and rule mapping |
  | 98 | **CMS Auditing** | WPScan, Droopescan, CMSMap, CMSeek, JoomScan — multi-CMS platform scanning |
  | 99 | **Custom Commands** | User-created command templates with full variable substitution support |

  ---

  ## 🔲 MODULES Portal

  The **MODULES** button (top-right navbar, blue) opens a full-screen portal with ten specialized engagement management modules.

  ### Dashboard — Attack Surface Matrix
  Real-time attack surface visualization. Displays live counts of **Domains**, **IP Nodes**, **Open Ports**, and **Vulnerabilities** sourced from the Graph Visualizer's D3 node data stored in IndexedDB. Shows a live "SYSTEMS ONLINE" pulse indicator.

  ### Graph Visualizer
  An interactive **D3.js force-directed network graph** for mapping your recon results visually. Add nodes by type (domain, IP, port, vulnerability) and draw edges between them to represent discovered relationships. Graph data persists via Dexie/IndexedDB and is included in state exports.

  ### Workflow Builder
  A structured methodology workflow interface for organizing and sequencing your recon and testing phases in a defined order.

  ### Collaboration
  Real-time team collaboration powered by **Socket.io**. Share sessions, sync findings, and coordinate recon with teammates over WebSocket. The Express backend handles Socket.io connections.

  ### Integrations
  External platform integrations for professional engagements:
  - **Alert Webhooks** — Send findings directly to **Slack** or **Discord** via webhook URL with a test connection button
  - **DefectDojo / Jira API** — Auto-create vulnerability tickets by configuring an endpoint URL and API token

  ### Recon Planner
  A structured interface for defining engagement scope, planning recon phases, and organizing your attack plan before testing begins.

  ### Findings Tracker
  A dedicated vulnerability tracker for logging discovered issues, assigning severity, and tracking remediation status throughout an engagement.

  ### Report Generator
  Auto-generates a full **Penetration Test Report** in Markdown from your live session data:
  - Executive Summary section
  - Methodology section
  - Complete command history with timestamps and category labels
  - All per-tool notes rendered as findings
  - Conclusion section

  Includes an **AI ENHANCE** button that sends the draft to Gemini for a professional rewrite with three depth modes — Quick summary, OSCP/PTES structure evaluation, or full executive-ready rewrite with Risk Matrix, Remediation Plan, and MITRE ATT&CK mapping. Downloads as `pentest-report-YYYY-MM-DD.md`.

  ### State Manager
  Exports and imports the **complete session state** as JSON, including:
  - Target domain
  - All configured variables
  - Notes (all tools)
  - Command history (last 50)
  - Favorites list
  - Theme settings
  - All D3 graphs from IndexedDB

  Import overwrites current state and reloads the application. Enables cross-device session handoff and team state sharing.

  ### Cheatsheet
  Quick-reference panel with:
  - **Common Ports**: FTP (21), SSH (22), Telnet (23), SMTP (25), DNS (53), HTTP (80), POP3 (110), SMB (139/445), IMAP (143), HTTPS (443), MySQL (3306), RDP (3389), PostgreSQL (5432), HTTP-Proxy (8080)
  - **HTTP Status Codes**: 200 OK, 301/302 Redirect, 400 Bad Request, 401 Unauthorized, 403 Forbidden, 404 Not Found, 500 Internal Server Error — color coded
  - **Reverse Shells**: Ready-to-copy shells for Bash TCP, Python socket, Netcat (`-e` and `mkfifo` variants), PowerShell TCP

  ### Settings
  Configure all API keys and variables used across the toolkit:

  | Key / Variable | Used For |
  |---|---|
  | `GEMINI_API_KEY` | AI Threat Intelligence + Global AI Assistant |
  | `OPENAI_API_KEY` | Alternative AI backend (GPT) |
  | `ANTHROPIC_API_KEY` | Alternative AI backend (Claude) |
  | `OLLAMA_URL` | Local LLM endpoint (default: `http://localhost:11434`) |
  | `IP` | Attacker IP — substituted via `IP` placeholder in commands |
  | `BURP` | Burp Collaborator URL — used in OOB/blind detection commands |
  | `TOKEN` | Auth/session token for authenticated testing |
  | `GITHUB_TOKEN` | GitHub PAT for GitHub-based recon (github-subdomains etc.) |
  | `JWT` | JWT token for API security testing commands |

  ---

  ## 🤖 AI Features

  ### AI Threat Intelligence (Gemini + Google Search)
  Accessed via the **THREAT INTEL** navbar button. Queries Google Gemini with live Google Search grounding — the model fetches real search results before responding. Enter any query:

  ```
  latest Apache Struts CVEs
  Log4j exploitation 2025
  CVE-2024-XXXXX proof of concept
  active ransomware TTPs this month
  ```

  Results render as formatted Markdown with cited source URLs. Responses draw exclusively from live search results, not training data, ensuring current information.

  ### Global AI Assistant (Multi-Backend)
  A full chat panel supporting four AI backends simultaneously based on configured keys:
  - **Google Gemini** (primary)
  - **OpenAI** (GPT-4-class)
  - **Anthropic Claude**
  - **Ollama** (fully local and offline)

  The assistant is target-aware — it knows your current domain and responds as an elite cybersecurity AI. Use it to ask about specific techniques, explain tool output, generate custom command variations, or get exploitation guidance for your current target.

  ### AI Report Enhancer
  Inside the Report Generator module. Three enhancement depth levels:
  - **Quick** — Summarize key findings and highlight critical risks
  - **Heuristic** — Evaluate structure against OSCP and PTES report templates
  - **Deep** — Full professional rewrite: Executive Summary, Risk Matrix, Remediation Plan, MITRE ATT&CK technique mapping

  ---

  ## 🔧 Variable Substitution System

  Six placeholders are replaced at copy time via `processCommand()`:

  ```
  Placeholder                  Replaced With
  ────────────────────────────────────────────
  DOMAIN                    →  Your target domain (e.g., target.com)
  IP                        →  Your attacker IP (from Settings)
  BURP / BURP_COLLABORATOR  →  Your Burp Collaborator hostname
  $TOKEN                    →  Auth/session token
  $GITHUB_TOKEN             →  GitHub Personal Access Token
  $JWT                      →  JWT token
  ```

  Example:
  ```bash
  # Stored command
  subfinder -d DOMAIN -all -recursive -o subs.txt

  # After entering target.com → clicking EXECUTE → clicking COPY
  subfinder -d target.com -all -recursive -o subs.txt
  ```

  Custom commands you create via **ADD COMMAND** use the same placeholders and receive identical substitution treatment.

  ---

  ## 💾 Persistence & Storage

  Every setting, preference, and session state is automatically persisted — nothing is lost on refresh.

  | Data | Storage |
  |---|---|
  | Target domain | `localStorage` |
  | Variables (IP, tokens, keys) | `localStorage` |
  | Starred favorites | `localStorage` |
  | Completed commands | `localStorage` |
  | Custom commands | `localStorage` |
  | Per-tool notes | `localStorage` |
  | Command history (last 50) | `localStorage` |
  | Active category | `localStorage` |
  | Theme (light/dark) | `localStorage` |
  | Accent color (green/blue/purple/red) | `localStorage` |
  | D3 graph nodes and edges | **IndexedDB** (via Dexie) |

  The State Manager exports all of the above — including IndexedDB graphs — as a single JSON file.

  ---

  ## 📤 Export Capabilities

  | Export | Format | What's Included |
  |---|---|---|
  | **EXPORT .SH** | Bash script | All visible expanded commands, organized by category with section headers and `echo "[*] Starting..."` statements. Auto-generated header with target name, toolkit credit, and date |
  | **REPORT .MD** | Markdown | All commands marked ✅ Complete with tool name, description, and bash code block per command |
  | **Pentest Report** | Markdown | Executive Summary, Methodology, full command history with timestamps, all saved notes as findings, Conclusion |
  | **Install Script** | Bash script | Installs every tool in the toolkit on Debian/Ubuntu — Go tools, Python packages, Ruby gems, Git clones to `/opt/` — covers all 37+ tool categories |
  | **Config Backup** | JSON | Favorites, completed, custom commands, variables, notes, domain, theme |

  ---

  ## 🎨 Theme System

  Two brightness modes × four accent colors = **8 theme combinations**.

  **Brightness:**
  - 🖤 **Dark Mode** (default) — Black background, terminal aesthetic
  - 🤍 **Light Mode** — Inverted scheme for daylight environments

  **Accent Colors:**
  - 🟢 **Green** (default) — `#00ff41` classic terminal green
  - 🔵 **Blue** — Electric blue
  - 🟣 **Purple** — Deep purple
  - 🔴 **Red** — Warning red

  Theme state persists to localStorage and is included in config export/import.

  ---

  All AI features (Threat Intel, AI Assistant, Report Enhancer) require the Gemini key. Every other feature — all 2,900+ commands, exports, favorites, history, graph, collab — works without any API key.

  ---

  ## ⚖️ Ethical & Legal Use

  > The UI displays: **`⚠ Authorized Penetration Testing Only ⚠`**

  This toolkit generates commands. It does not execute them on your behalf, contact any servers, or send your target data anywhere. All command substitution happens locally in your browser.

  Using the generated commands against systems without authorization is illegal under:
  - **Computer Fraud and Abuse Act (CFAA)** — United States
  - **Computer Misuse Act** — United Kingdom
  - **Information Technology Act** — India
  - And equivalent legislation worldwide

  By using this toolkit you agree:
  - ✅ You have **explicit written authorization** to test the target systems
  - ✅ Bug bounty usage stays within the **defined scope** of each program
  - ✅ You are solely responsible for your actions
  - ❌ The author accepts **zero liability** for any unauthorized or illegal use

  ---

  ## 👤 Author

  **Rohit** — Automation Developer & Bug Bounty Hunter

  [![GitHub](https://img.shields.io/badge/GitHub-rohit--1006-00ff41?style=for-the-badge&logo=github&logoColor=black)](https://github.com/rohit-1006)
  [![Live Tool](https://img.shields.io/badge/🔗_Live_Tool-cybersec--toolkit.netlify.app-00ff41?style=for-the-badge)](https://cybersec-toolkit.netlify.app/)

  ---

  <div align="center">

  **CYBER RECON TOOLKIT © 2026 — All rights reserved.**

  _Stay legal. Stay ethical. Happy hunting._ ☠️

  </div>
