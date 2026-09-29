# CYBER SECURITY MASTER GUIDE

> Master roadmap untuk belajar cybersecurity, web security, defensive security, CTF, dan bug bounty secara legal.
>
> **Scope keselamatan:** contoh pengujian aktif di bawah diarahkan ke `127.0.0.1`, VM, container, CTF, atau target yang secara eksplisit mengizinkan pengujian. Untuk program bug bounty, policy program selalu menjadi batas utama.

## 🔎 SEARCH

GitHub Markdown tidak menyediakan search box interaktif yang berjalan di browser secara native. Gunakan `Ctrl+F` / `Find in page`, atau pencarian repository GitHub. Daftar topik:

`Linux` · `Networking` · `HTTP` · `OWASP` · `Burp` · `Nmap` · `FFUF` · `Nuclei` · `SQLi` · `XSS` · `IDOR` · `SSRF` · `CSRF` · `JWT` · `API` · `Recon` · `Bug Bounty` · `CTF` · `Blue Team` · `Cloud` · `Mobile` · `DevSecOps` · `DFIR` · `Reverse Engineering`

---

# 1. ROADMAP

```text
Linux → Networking → HTTP/Web → Python/Bash/JS/SQL
→ OWASP → Burp → Web Labs → Recon → API/AuthZ
→ CTF → Bug Bounty Methodology → Reporting → Specialization
```

Jangan menghafal command tanpa memahami protokol, vulnerability, dampak, dan mitigasinya.

---

# 2. SUMBER BELAJAR UTAMA

## Web Security

| Resource | Fokus |
|---|---|
| PortSwigger Web Security Academy | Web security + interactive labs |
| OWASP WSTG | Metodologi web application security testing |
| OWASP Top 10 | Application security awareness |
| Hacker101 | Web security + CTF |
| Intigriti Hackademy | Web vulnerabilities + bug bounty |
| Bugcrowd University | Researcher education |
| YesWeHack Dojo | CTF + bug bounty training |
| Hack The Box Academy/Labs | Hands-on cybersecurity |
| TryHackMe | Guided cybersecurity learning |
| OverTheWire | Linux/security wargames |
| picoCTF | Beginner-friendly CTF |
| Root-Me | Security challenges |
| PentesterLab | Web hacking exercises |
| CyberDefenders | Blue-team/DFIR challenges |
| Blue Team Labs Online | Defensive security labs |

PortSwigger menyediakan learning paths, materi, dan interactive labs gratis yang mencakup SQL injection, XSS, CSRF, SSRF, access control, authentication, API testing, race conditions, GraphQL, NoSQL injection, Web LLM attacks, dan banyak topik lain. citeturn0search0turn0search1turn0search12

OWASP WSTG merupakan framework pengujian keamanan aplikasi web yang mencakup metodologi dan skenario testing; versi yang tersedia secara resmi mencakup v4.2 sementara proyek juga sedang mengembangkan v5.0. citeturn0search2turn0search9

Hacker101 adalah kursus web security gratis dengan video, materi, dan CTF yang dirancang sebagai lingkungan latihan aman. citeturn1search8turn1search0

Intigriti Hackademy menyediakan materi gratis mengenai vulnerability categories, write-up, tips bug bounty, video, dan reporting. citeturn1search1

Bugcrowd University adalah proyek pendidikan open-source gratis untuk security researchers, dengan modul seperti recon/discovery dan vulnerability classes. citeturn1search5

YesWeHack Dojo menyediakan CTF, learning modules, sandbox, dan roadmap bug bounty. citeturn1search4turn1search6

---

# 3. LINUX FUNDAMENTALS

## Konsep

- filesystem
- users/groups
- permissions
- processes
- services
- environment variables
- SSH
- package management
- logs
- networking CLI
- shell scripting
- cron/systemd

## Command dasar

```bash
pwd
ls -la
cd /path
find . -type f
file filename
cat filename
less filename
head filename
tail -f logfile
grep -R "keyword" .
sort
uniq
cut
awk
sed
xargs
wc
du -sh .
df -h
free -h
uname -a
id
whoami
ps aux
top
ss -tulpn
ip addr
ip route
env
printenv
history
```

## Permissions

```bash
ls -l
chmod 644 file.txt
chmod 755 script.sh
chown user:group file.txt
```

`r=read`, `w=write`, `x=execute`.

## Bash

```bash
#!/usr/bin/env bash
set -euo pipefail
TARGET="http://127.0.0.1:3000"
echo "Testing: $TARGET"
```

Pelajari variables, functions, loops, conditions, exit codes, pipes, redirection, traps, dan error handling.

---

# 4. NETWORKING

## Wajib

- IPv4/IPv6
- subnetting
- TCP/UDP
- ports
- DNS
- ARP
- DHCP
- HTTP/HTTPS
- TLS
- SSH
- SMTP
- FTP
- SMB
- routing
- NAT
- firewall
- proxy/VPN

## Command

```bash
ip addr
ip route
ip neigh
ss -tulpn
ping 127.0.0.1
traceroute 127.0.0.1
dig example.com
nslookup example.com
host example.com
curl -I https://example.com
```

---

# 5. HTTP & WEB FUNDAMENTALS

Pelajari URL, request/response, headers, cookies, sessions, methods, status codes, redirects, caching, CORS, CSP, Same-Origin Policy, browser storage, DOM, REST, GraphQL, dan WebSocket.

## Methods

```text
GET POST PUT PATCH DELETE HEAD OPTIONS
```

## Status

```text
2xx success
3xx redirect
4xx client error
5xx server error
```

## curl lab

```bash
curl -v http://127.0.0.1:3000/
curl -I http://127.0.0.1:3000/
curl -X OPTIONS -i http://127.0.0.1:3000/
curl -H 'Content-Type: application/json' \
  -d '{"username":"test","password":"test"}' \
  http://127.0.0.1:3000/api/login
```

---

# 6. PROGRAMMING

## Python

```python
import requests

url = "http://127.0.0.1:3000/"
r = requests.get(url, timeout=10)
print(r.status_code)
print(r.headers)
print(r.text[:500])
```

Pelajari `requests`, `socket`, `subprocess`, `json`, `re`, `hashlib`, `base64`, `urllib.parse`, argparse, logging, file I/O.

## JavaScript

Pelajari DOM, fetch, cookies, localStorage, sessionStorage, promises, async/await, JSON, browser APIs, prototypes.

## SQL

```sql
SELECT
INSERT
UPDATE
DELETE
WHERE
JOIN
GROUP BY
ORDER BY
UNION
subqueries
transactions
```

Fokus keamanan: prepared statements, parameterized queries, allow-list validation, least privilege.

---

# 7. SECURITY FUNDAMENTALS

- CIA triad
- authentication
- authorization
- accounting
- least privilege
- defense in depth
- attack surface
- threat modeling
- vulnerability
- exploit
- impact
- risk
- CVE
- CWE
- CVSS

```text
Vulnerability = kelemahan
Exploit = teknik memanfaatkan kelemahan
Impact = akibat
Risk = kemungkinan × dampak (secara konseptual)
```

---

# 8. OWASP TOP 10 / APPLICATION SECURITY

Pelajari kategori OWASP secara langsung dari sumber resmi dan pahami bahwa taxonomy dapat berubah. Fokus konsep:

```text
Broken Access Control
Security Misconfiguration
Software Supply Chain Security
Cryptographic Failures
Injection
Insecure Design
Authentication Failures
Software/Data Integrity Failures
Security Logging/Alerting Failures
Exceptional-condition handling
```

OWASP Top 10 adalah awareness document, bukan daftar lengkap seluruh vulnerability aplikasi.

---

# 9. OWASP WSTG METHODOLOGY

Struktur besar testing:

```text
Information Gathering
Configuration/Deployment
Identity Management
Authentication
Authorization
Session Management
Input Validation
Error Handling
Cryptography
Business Logic
Client-side Testing
API Testing
```

WSTG mendokumentasikan framework dan teknik pengujian web secara sistematis. citeturn0search6turn0search17

---

# 10. WEB VULNERABILITY MASTER LIST

## SQL Injection

Konsep: input pengguna memengaruhi query database secara tidak aman.

Pelajari:

- classic SQLi
- UNION
- error-based
- blind
- time-based
- second-order
- prepared statements
- ORM pitfalls

Pertahanan:

```text
parameterized queries
prepared statements
allow-list validation
least-privilege DB accounts
```

## XSS

```text
Reflected
Stored
DOM-based
```

Pelajari context, encoding, sanitization, DOM sources/sinks, CSP.

Pertahanan:

```text
context-aware output encoding
safe DOM APIs
validation
sanitization when appropriate
CSP
HttpOnly cookies
```

## CSRF

Pelajari state-changing requests, CSRF tokens, SameSite, Origin/Referer validation, re-authentication.

## Broken Access Control / IDOR / BOLA

Pertanyaan inti pada lab:

```text
Apakah server memeriksa ownership?
Apakah role enforcement terjadi server-side?
Apakah object-level authorization diterapkan?
Apakah horizontal/vertical privilege escalation mungkin?
```

Pertahanan: server-side authorization, object-level authorization, deny-by-default, centralized policy.

## Authentication

Pelajari password handling, sessions, MFA, recovery, enumeration, rate limiting, session fixation, invalidation.

## SSRF

Model:

```text
user-controlled URL → application server → destination
```

Pelajari allowlists, URL parsing, redirects, egress controls, private-network restrictions.

## File Upload

Pelajari extension/MIME/content validation, filename handling, storage isolation, size limits, executable storage.

## Path Traversal

Pelajari canonicalization, path normalization, base-directory restrictions, safe file APIs.

## Command Injection

Pelajari mengapa shell execution berbahaya, direct process APIs, allowlisted arguments, privilege separation.

## JWT

Pelajari header, payload, signature, expiry, issuer, audience, key management, algorithm handling. Decoding bukan verification.

## API Security

```text
Authentication
Authorization
BOLA/BFLA
Input validation
Mass assignment
Excessive data exposure
Rate limiting
CORS
GraphQL
WebSocket
Error handling
Versioning
```

## Business Logic

Pelajari workflow bypass, state transition, coupon/quantity logic, multi-step flows, race conditions, authorization assumptions.

## Advanced web topics

PortSwigger saat ini mencantumkan juga request smuggling, SSTI, insecure deserialization, prototype pollution, GraphQL, NoSQL injection, web cache poisoning/deception, HTTP Host header attacks, OAuth, Web LLM attacks, dan lainnya. citeturn0search3turn0search12

---

# 11. BURP SUITE

Komponen yang perlu dikuasai:

```text
Proxy
Repeater
Intruder
Decoder
Comparer
Logger
Target
Scope
HTTP history
Site map
Extensions
```

Workflow lab:

```text
Browser → Burp Proxy → Local/authorized lab
```

Burp Community Edition dapat digunakan untuk latihan dasar; PortSwigger menyediakan tutorial dan Academy labs. citeturn0search1turn0search15

---

# 12. NMAP

Gunakan hanya terhadap host sendiri/lab/authorized scope.

```bash
nmap 127.0.0.1
nmap -sV 127.0.0.1
nmap -sC 127.0.0.1
```

Pelajari host discovery, port scanning, service detection, NSE, output formats, dan false positives.

---

# 13. CONTENT DISCOVERY & FUZZING

Tools:

```text
ffuf
feroxbuster
gobuster
dirsearch
wfuzz
```

Contoh localhost:

```bash
ffuf -u http://127.0.0.1:3000/FUZZ -w /path/to/wordlist.txt
```

Pelajari wordlists, status codes, response size, filtering, recursion, rate limits, false positives.

---

# 14. NUCLEI

Konsep:

```text
Target → Template → Request → Matcher → Finding → Manual verification
```

Contoh lab:

```bash
nuclei -u http://127.0.0.1:3000
```

Scanner output bukan otomatis bukti vulnerability.

---

# 15. WIRESHARK / TCPDUMP

Wireshark filter dasar:

```text
http
dns
tcp
udp
tcp.port == 80
ip.addr == 127.0.0.1
```

Tcpdump lab:

```bash
tcpdump -D
tcpdump -i any -nn
```

Pelajari TCP streams, DNS, HTTP, TLS, ARP, packet capture, dan filtering.

---

# 16. METASPLOIT / LAB EXPLOITATION

Pelajari konsep:

```text
module
exploit
payload
auxiliary
post
session
```

Gunakan hanya VM/CTF yang memang dibuat untuk latihan. Fokus memahami vulnerability dan mitigasi, bukan menyerang sistem pihak lain.

---

# 17. PASSWORD & HASH SECURITY

Pelajari:

```text
encoding ≠ encryption ≠ hashing
MD5
SHA-1
SHA-2
SHA-3
bcrypt
scrypt
Argon2
salt
pepper
KDF
entropy
```

File hash:

```bash
sha256sum file.txt
sha512sum file.txt
```

---

# 18. GIT & SECRET DISCOVERY

Risiko umum:

```text
API keys
access tokens
private keys
.env
CI secrets
cloud credentials
```

Tool:

```text
git
gitleaks
trufflehog
```

Lab repository sendiri:

```bash
git status
git log --all --oneline
git diff
gitleaks detect --source .
```

---

# 19. RECONNAISSANCE

## Passive

- public DNS
- certificate transparency
- public documentation
- public source code
- public URLs
- historical URLs
- technology fingerprinting

## Active — hanya jika policy mengizinkan

- HTTP probing
- port discovery
- endpoint enumeration
- controlled content discovery

Model:

```text
Program → Scope → Assets → DNS → HTTP → Technologies → Endpoints → Manual testing
```

Tools umum:

```text
subfinder
amass
assetfinder
dnsx
httpx
naabu
nmap
```

---

# 20. JAVASCRIPT / ENDPOINT RECON

Cari secara manual dalam aplikasi/lab:

```text
/api/
graphql
admin
debug
internal
upload
callback
redirect
token
id
user
role
file
download
```

Tools:

```text
Burp
curl
browser DevTools
httpx
```

Endpoint yang ditemukan tidak otomatis berarti vulnerable.

---

# 21. BUG BOUNTY — METHODOLOGY

## Step 1 — Pilih program

Platform umum:

```text
HackerOne
Bugcrowd
Intigriti
YesWeHack
```

## Step 2 — Baca policy

```text
Scope
Out of scope
Rate limits
Automation rules
Prohibited testing
Data handling
Disclosure
Reward rules
Safe harbor
```

## Step 3 — Asset mapping

```text
Program
 ↓
In-scope assets
 ↓
Technologies
 ↓
Endpoints
 ↓
Authentication boundaries
```

## Step 4 — Manual testing

Prioritaskan pemahaman:

```text
Access control
Authentication
Business logic
API
File upload
SSRF
XSS
Injection
Misconfiguration
```

## Step 5 — Verify

Temuan harus:

```text
in-scope
reproducible
security-relevant
non-destructive
evidence-backed
```

## Step 6 — Report

```text
Title
Summary
Asset
Endpoint
Preconditions
Steps to reproduce
Expected behavior
Actual behavior
Impact
Evidence
Remediation
```

HackerOne menjelaskan Hacker101 sebagai kursus web security gratis dan menyediakan CTF untuk latihan aman. citeturn1search8turn1search10

YesWeHack secara eksplisit menyarankan hunter memulai dengan Dojo, membaca scope/rules sebelum testing, lalu mengirim laporan yang berisi reproduction steps, impact/severity, dan remediation. citeturn1search9turn1search2

---

# 22. REPORT TEMPLATE

```markdown
# [Vulnerability] — [Affected Endpoint]

## Summary
Jelaskan vulnerability secara singkat.

## Asset
https://example.invalid/

## Endpoint
`GET /api/example`

## Preconditions
Akun/role yang diperlukan.

## Steps to Reproduce
1. Login menggunakan test account.
2. Buka endpoint.
3. Kirim request.
4. Amati response.
5. Bandingkan expected vs actual.

## Expected Behavior
...

## Actual Behavior
...

## Security Impact
Dampak yang dapat dibuktikan.

## Evidence
Screenshot/request-response yang tidak mengekspos data sensitif.

## Remediation
Perbaikan teknis.

## Scope / Authorization
Testing dilakukan sesuai scope dan policy program.
```

---

# 23. TRIAGE CHECKLIST

```text
[ ] Target in scope?
[ ] Testing permitted?
[ ] Reproducible?
[ ] Impact demonstrated?
[ ] Not just informational?
[ ] Not duplicate if known?
[ ] No unnecessary sensitive data collected?
[ ] No destructive action?
[ ] Clear reproduction steps?
[ ] Evidence sufficient?
[ ] Remediation reasonable?
```

---

# 24. CTF / TRAINING LABS

Mulai dari:

```text
PortSwigger Web Security Academy
Hacker101 CTF
OWASP Juice Shop
OWASP WebGoat
DVWA
OverTheWire
picoCTF
TryHackMe
Hack The Box
Root-Me
PentesterLab
```

PortSwigger menyediakan lab untuk SQLi, XSS, CSRF, SSRF, access control, authentication, file upload, JWT, GraphQL, race conditions, API testing, dan lainnya. citeturn0search12

Hacker101 CTF dirancang sebagai lingkungan aman untuk belajar menemukan vulnerability/flags. citeturn1search0turn1search15

---

# 25. BLUE TEAM / SOC

Pelajari:

```text
SIEM
EDR
IDS/IPS
log analysis
alert triage
incident response
threat intelligence
network monitoring
MITRE ATT&CK
Sigma
YARA
```

Tools:

```text
Wireshark
Zeek
Suricata
Wazuh
Elastic
Splunk
Sysmon
YARA
Volatility
```

Workflow:

```text
Alert → Validate → Scope → Evidence → Timeline → Root cause
→ Contain → Eradicate → Recover → Lessons learned
```

---

# 26. CLOUD SECURITY

Pelajari:

```text
AWS
Azure
GCP
IAM
storage
security groups
networking
logging
KMS
secrets
containers
Kubernetes
serverless
```

Tools:

```text
AWS CLI
Azure CLI
gcloud
kubectl
Trivy
Checkov
Prowler
```

Gunakan akun/lab cloud sendiri.

---

# 27. MOBILE SECURITY

Pelajari Android/iOS fundamentals, APK, ADB, permissions, local storage, WebView, deep links, IPC, TLS, certificate pinning concepts.

Tools:

```text
adb
apktool
jadx
MobSF
Frida
Objection
Burp Suite
```

Gunakan aplikasi training atau aplikasi yang secara eksplisit mengizinkan testing.

---

# 28. DEVSECOPS

Pelajari:

```text
SAST
DAST
SCA
IaC scanning
secret scanning
container scanning
SBOM
CI/CD security
dependency security
threat modeling
```

Tools:

```text
Semgrep
CodeQL
Bandit
Gitleaks
Trivy
Checkov
OWASP Dependency-Check
npm audit
pip-audit
```

Contoh repository sendiri:

```bash
npm audit
pip-audit
gitleaks detect --source .
trivy fs .
```

---

# 29. CRYPTOGRAPHY

Pelajari:

```text
symmetric encryption
asymmetric encryption
digital signatures
MAC/HMAC
key exchange
PKI
TLS
randomness
entropy
password hashing
```

Tools:

```bash
openssl version
openssl rand -hex 32
sha256sum file.txt
gpg --version
```

---

# 30. DIGITAL FORENSICS

Pelajari:

```text
disk images
file systems
metadata
timeline analysis
memory
browser artifacts
logs
network captures
malware artifacts
```

Tools:

```text
Autopsy
The Sleuth Kit
Volatility
Wireshark
ExifTool
binwalk
strings
```

---

# 31. REVERSE ENGINEERING

Pelajari:

```text
assembly
ELF
PE
processes
memory
debugging
calling conventions
symbols
static analysis
dynamic analysis
```

Tools:

```text
Ghidra
Cutter
radare2
gdb
lldb
strings
objdump
readelf
```

---

# 32. BINARY / PWN — CTF ONLY

Pelajari:

```text
stack
heap
buffer overflow
ASLR
NX
PIE
RELRO
ROP
format strings
memory corruption
```

Tools:

```text
gdb
pwndbg
GEF
checksec
pwntools
```

Target hanya binary latihan/CTF.

---

# 33. MALWARE ANALYSIS — DEFENSIVE

Pelajari static analysis, dynamic analysis, IOC, YARA, sandboxing, behavior analysis, network indicators.

Tools:

```text
YARA
Ghidra
Wireshark
Volatility
REMnux
FLARE-VM
```

Gunakan sample dan lingkungan yang memang disediakan untuk analisis.

---

# 34. OSINT

Pelajari:

```text
DNS
certificate transparency
metadata
public documentation
public repositories
search operators
technology intelligence
```

Workflow:

```text
Collect → Verify → Correlate → Attribute → Document
```

Jangan menggunakan OSINT untuk doxxing atau merugikan individu.

---

# 35. MASTER TOOL LIST

## Core

```text
curl
wget
git
python3
pipx
jq
ripgrep
openssl
docker
```

## Recon

```text
Nmap
Masscan
Naabu
Amass
Subfinder
Assetfinder
DNSx
Httpx
```

## Web

```text
Burp Suite
OWASP ZAP
Caido
ffuf
Feroxbuster
Gobuster
Dirsearch
Wfuzz
Nikto
Nuclei
```

## Network

```text
Wireshark
tcpdump
tshark
Zeek
Suricata
```

## Password/hash auditing — lab/authorized only

```text
Hashcat
John the Ripper
Hydra
Medusa
```

## Exploitation labs

```text
Metasploit
sqlmap
Impacket
Netcat
Socat
```

## Reverse

```text
Ghidra
Cutter
radare2
GDB
pwndbg
strings
objdump
readelf
```

## Forensics

```text
Autopsy
Sleuth Kit
Volatility
ExifTool
binwalk
Foremost
```

## DevSecOps

```text
Semgrep
CodeQL
Gitleaks
Trivy
Checkov
Prowler
```

## Blue Team

```text
Wazuh
Elastic
Splunk
Sigma
YARA
Suricata
Zeek
Sysmon
```

---

# 36. COMMAND CHEAT SHEET

## System

```bash
whoami
id
uname -a
hostname
cat /etc/os-release
ps aux
ss -tulpn
df -h
free -h
```

## Network

```bash
ip addr
ip route
ip neigh
dig example.com
host example.com
curl -I https://example.com
```

## Local web lab

```bash
curl -v http://127.0.0.1:3000/
curl -I http://127.0.0.1:3000/
curl -X OPTIONS -i http://127.0.0.1:3000/
```

## Nmap local lab

```bash
nmap 127.0.0.1
nmap -sV 127.0.0.1
nmap -sC 127.0.0.1
```

## Hash

```bash
sha256sum file
sha512sum file
```

## Git

```bash
git status
git log --oneline --all
git branch -a
git remote -v
git diff
```

---

# 37. LOCAL LAB

Contoh OWASP Juice Shop dengan Docker:

```bash
docker pull bkimminich/juice-shop
docker run --rm -p 3000:3000 bkimminich/juice-shop
```

Buka:

```text
http://127.0.0.1:3000/
```

Lakukan testing di aplikasi lab tersebut, bukan terhadap situs publik secara sembarangan.

---

# 38. BUG BOUNTY DAILY WORKFLOW

```text
1. Pilih program authorized
2. Baca policy
3. Catat scope
4. Asset mapping
5. Pelajari aplikasi
6. Identifikasi teknologi
7. Mapping endpoint
8. Pahami authentication
9. Pahami authorization
10. Manual testing
11. Verify
12. Evidence minimal
13. Report
14. Monitor triage
15. Retest jika diminta/diizinkan
```

Jangan mengejar jumlah report; utamakan validitas dan reproduktibilitas.

---

# 39. REPORTING RULES

Laporan yang baik harus menjawab:

```text
Apa bug-nya?
Di mana?
Bagaimana mereproduksi?
Apa expected behavior?
Apa actual behavior?
Apa dampak yang terbukti?
Bagaimana memperbaikinya?
```

Jangan memasukkan data sensitif yang tidak diperlukan.

---

# 40. RESOURCE LINKS

## Official / Training

- [PortSwigger Web Security Academy](https://portswigger.net/web-security)
- [PortSwigger Learning Paths](https://portswigger.net/web-security/learning-paths)
- [PortSwigger All Labs](https://portswigger.net/web-security/all-labs)
- [OWASP Web Security Testing Guide](https://wstg.owasp.org/)
- [OWASP Projects](https://owasp.org/projects/)
- [Hacker101](https://www.hacker101.com/)
- [Hacker101 CTF](https://ctf.hacker101.com/)
- [Intigriti Hackademy](https://www.intigriti.com/researchers/hackademy)
- [Bugcrowd University](https://github.com/bugcrowd/bugcrowd_university)
- [YesWeHack Dojo](https://dojo-yeswehack.com/)
- [Hack The Box](https://www.hackthebox.com/hacker)
- [TryHackMe](https://tryhackme.com/)
- [OverTheWire](https://overthewire.org/)
- [picoCTF](https://picoctf.org/)
- [Root-Me](https://www.root-me.org/)
- [PentesterLab](https://pentesterlab.com/)
- [CyberDefenders](https://cyberdefenders.org/)
- [Blue Team Labs Online](https://blueteamlabs.online/)

## Bug Bounty Platforms

- [HackerOne](https://www.hackerone.com/)
- [Bugcrowd](https://www.bugcrowd.com/)
- [Intigriti](https://www.intigriti.com/)
- [YesWeHack](https://yeswehack.com/)

**Selalu cek program page terbaru sebelum testing karena scope, reward, rate limit, dan rules dapat berubah.** YesWeHack sendiri menekankan pembacaan scope/rules sebelum testing dan quality reporting. citeturn1search9

---

# 41. STUDY ORDER

```text
LEVEL 1
Linux → Networking → HTTP → Git → Python/Bash/JS/SQL

LEVEL 2
OWASP → Burp → Authentication → Authorization → Sessions

LEVEL 3
SQLi → XSS → CSRF → SSRF → File Upload → Path Traversal
→ API → JWT/OAuth → Business Logic → Race Conditions

LEVEL 4
PortSwigger Labs → Juice Shop → WebGoat → Hacker101 CTF
→ TryHackMe/HTB/Root-Me/PentesterLab

LEVEL 5
Recon → Authorized Bug Bounty → Verification → Reporting

LEVEL 6
Cloud / Mobile / Active Directory / DFIR / Reverse / Blue Team / DevSecOps
```

---

# 42. MASTER CHECKLIST

```text
[ ] Linux
[ ] Networking
[ ] TCP/IP
[ ] DNS
[ ] HTTP
[ ] TLS
[ ] Git
[ ] Python
[ ] Bash
[ ] SQL
[ ] JavaScript
[ ] OWASP
[ ] WSTG
[ ] Burp
[ ] Authentication
[ ] Authorization
[ ] Sessions
[ ] SQLi
[ ] XSS
[ ] CSRF
[ ] SSRF
[ ] IDOR/BOLA
[ ] File Upload
[ ] Path Traversal
[ ] Command Injection
[ ] JWT
[ ] OAuth
[ ] API
[ ] GraphQL
[ ] WebSocket
[ ] Business Logic
[ ] Race Conditions
[ ] Recon
[ ] CTF
[ ] Reporting
[ ] Blue Team
[ ] Cloud
[ ] Mobile
[ ] DevSecOps
[ ] DFIR
[ ] Reverse Engineering
```

---

# 43. IMPORTANT: “100% LENGKAP”

Tidak ada satu file yang secara realistis dapat memuat setiap website cybersecurity, setiap CVE, setiap tool, setiap command, setiap teknik, dan seluruh research yang pernah dibuat. Cybersecurity berubah terus.

File ini sengaja dibuat sebagai **master index + handbook**. Untuk detail yang berubah, gunakan dokumentasi resmi dan lab resmi yang ditautkan. PortSwigger secara eksplisit menyebut Academy sebagai living resource yang terus diperbarui; WSTG juga terus dikembangkan. citeturn0search1turn0search9

Prinsip:

```text
Learn the protocol
↓
Understand the vulnerability
↓
Practice in a legal lab
↓
Verify the result
↓
Understand the defense
↓
Test only authorized targets
↓
Document
↓
Report responsibly
```

---

# 44. ETHICAL TESTING GATE

Sebelum command pengujian aktif:

```text
[ ] Target milik saya?
atau
[ ] Ada izin eksplisit?
atau
[ ] Program bug bounty menyatakan target tersebut in-scope?

[ ] Aktivitas ini diizinkan policy?
[ ] Rate limit dipatuhi?
[ ] Tidak destructive?
[ ] Tidak mengambil data yang tidak diperlukan?
```

Jika jawabannya tidak jelas: gunakan localhost, VM, Docker, CTF, atau lab training.

---

# 45. PRINCIPLE

> **Understand the system before trying to break it. Understand the impact before reporting it. Understand the defense after finding it.**

Cybersecurity bukan sekadar kumpulan command. Skill utamanya adalah memahami sistem, menemukan kelemahan secara terukur, membuktikan dampaknya tanpa merusak, lalu menjelaskan cara memperbaikinya.

---

# 46. READY-TO-USE SECURITY LAB SCRIPTS

Bagian ini berisi script yang dapat langsung disalin. Setiap script menjelaskan dependency, bagian yang boleh diubah, contoh penggunaan, dan batasan penggunaan.

> **PENTING:** script yang melakukan discovery/scanning harus digunakan pada `localhost`, VM, CTF, aplikasi lab, atau aset yang secara eksplisit berada dalam scope pengujian. Untuk bug bounty, baca policy program sebelum automation.

## 46.1 Struktur folder yang disarankan

```text
cyber-lab/
├── scripts/
│   ├── http-check.sh
│   ├── security-headers.py
│   ├── local-nmap.sh
│   ├── content-discovery.sh
│   ├── nuclei-lab.sh
│   ├── scope-check.sh
│   └── hash-file.py
├── scope.txt
├── reports/
└── evidence/
```

---

## 46.2 HTTP CHECKER — Bash

### Fungsi
Memeriksa apakah aplikasi lab dapat diakses dan menampilkan response headers.

### Script

```bash
#!/usr/bin/env bash

# ============================================================
# HTTP CHECKER - SAFE LAB VERSION
# ============================================================
# YANG PERLU DIGANTI:
#   TARGET="http://127.0.0.1:3000"
#
# Ganti TARGET hanya dengan aplikasi milik sendiri, VM, CTF,
# atau target yang secara eksplisit mengizinkan pengujian.
#
# DEPENDENCY:
#   curl
#
# Debian/Ubuntu:
#   sudo apt update
#   sudo apt install -y curl
#
# JALANKAN:
#   chmod +x http-check.sh
#   ./http-check.sh
#
# ATAU:
#   TARGET="http://127.0.0.1:8080" ./http-check.sh
# ============================================================

set -u

TARGET="${TARGET:-http://127.0.0.1:3000}"

printf '[*] Target: %s\n' "$TARGET"
printf '[*] HTTP headers:\n\n'

curl --fail-with-body \
     --silent \
     --show-error \
     --max-time 10 \
     -I "$TARGET"

printf '\n[+] Pemeriksaan selesai.\n'
```

---

## 46.3 SECURITY HEADERS CHECKER — Python

### Fungsi
Memeriksa security headers umum pada aplikasi lab.

### Install

```bash
python3 -m pip install requests
```

### Script

```python
#!/usr/bin/env python3

"""
SECURITY HEADERS CHECKER - LAB VERSION

YANG PERLU DIGANTI:
    TARGET = "http://127.0.0.1:3000"

Gunakan hanya terhadap aplikasi milik sendiri atau target
yang secara eksplisit mengizinkan pemeriksaan.
"""

import requests

TARGET = "http://127.0.0.1:3000"

HEADERS = [
    "Content-Security-Policy",
    "Strict-Transport-Security",
    "X-Content-Type-Options",
    "Referrer-Policy",
    "Permissions-Policy",
]

try:
    response = requests.get(
        TARGET,
        timeout=10,
        allow_redirects=True,
    )
except requests.RequestException as exc:
    print(f"[!] Request gagal: {exc}")
    raise SystemExit(1)

print(f"[*] Target : {TARGET}")
print(f"[*] Status : {response.status_code}")
print(f"[*] Final  : {response.url}")
print()

for header in HEADERS:
    value = response.headers.get(header)
    if value:
        print(f"[+] {header}: {value}")
    else:
        print(f"[-] {header}: NOT PRESENT")
```

### Menjalankan

```bash
python3 security-headers.py
```

**Catatan:** header yang tidak ada tidak otomatis berarti vulnerability. Konteks aplikasi menentukan apakah header tersebut diperlukan.

---

## 46.4 LOCAL NMAP CHECK

### Fungsi
Discovery dasar terhadap mesin lab sendiri.

### Install

```bash
sudo apt update
sudo apt install -y nmap
```

### Script

```bash
#!/usr/bin/env bash

# ============================================================
# LOCAL NMAP CHECK
# ============================================================
# DEFAULT TARGET = 127.0.0.1
#
# YANG BOLEH DIGANTI:
#   TARGET="127.0.0.1"
#
# Jangan mengganti TARGET menjadi host publik kecuali host
# tersebut memang milikmu atau berada dalam scope pengujian.
# ============================================================

set -euo pipefail

TARGET="${TARGET:-127.0.0.1}"

printf '[*] Target: %s\n' "$TARGET"
printf '[*] Running service detection...\n\n'

nmap -sV --version-light "$TARGET"

printf '\n[+] Selesai.\n'
```

### Parameter penting

```text
-sV              = service/version detection
--version-light  = versi detection yang lebih ringan
```

---

## 46.5 CONTENT DISCOVERY DENGAN FFUF — LAB

### Install

Ikuti dokumentasi resmi FFUF atau gunakan paket yang tersedia pada distro kamu.

### Script

```bash
#!/usr/bin/env bash

# ============================================================
# FFUF CONTENT DISCOVERY - LAB ONLY
# ============================================================
# YANG PERLU DIGANTI:
#   TARGET="http://127.0.0.1:3000/FUZZ"
#   WORDLIST="/path/to/wordlist.txt"
#
# TARGET wajib menggunakan FUZZ.
#
# Contoh:
#   TARGET="http://127.0.0.1:3000/FUZZ" \
#   WORDLIST="/opt/SecLists/Discovery/Web-Content/common.txt" \
#   ./content-discovery.sh
#
# Jangan menjalankan directory fuzzing terhadap target publik
# tanpa izin atau tanpa aturan automation yang mengizinkannya.
# ============================================================

set -euo pipefail

TARGET="${TARGET:-http://127.0.0.1:3000/FUZZ}"
WORDLIST="${WORDLIST:-./wordlist.txt}"

if [[ "$TARGET" != *FUZZ* ]]; then
    echo "[!] TARGET harus mengandung FUZZ"
    exit 1
fi

if [[ ! -f "$WORDLIST" ]]; then
    echo "[!] Wordlist tidak ditemukan: $WORDLIST"
    echo "    Ubah variabel WORDLIST ke lokasi wordlist milikmu."
    exit 1
fi

ffuf \
    -u "$TARGET" \
    -w "$WORDLIST" \
    -rate 5 \
    -mc 200,204,301,302,307,401,403
```

### Yang perlu diganti

```text
TARGET   = URL aplikasi lab
WORDLIST = lokasi wordlist
```

`-rate 5` sengaja dibuat rendah untuk latihan. Untuk bug bounty, rate limit harus mengikuti policy program.

---

## 46.6 NUCLEI — LAB ONLY

### Fungsi
Menjalankan template vulnerability scanner terhadap aplikasi lab.

```bash
#!/usr/bin/env bash

# ============================================================
# NUCLEI LAB RUNNER
# ============================================================
# YANG PERLU DIGANTI:
#   TARGET="http://127.0.0.1:3000"
#
# Scanner output harus diverifikasi secara manual.
# Temuan dari scanner bukan otomatis vulnerability yang valid.
# ============================================================

set -euo pipefail

TARGET="${TARGET:-http://127.0.0.1:3000}"

nuclei \
    -u "$TARGET" \
    -severity info,low,medium,high,critical
```

### Prinsip verifikasi

```text
Scanner finding
      ↓
Baca template/finding
      ↓
Reproduce di lab
      ↓
Periksa response
      ↓
Tentukan false positive atau valid
      ↓
Dokumentasikan
```

---

## 46.7 SCOPE GUARD — MEMBACA SCOPE.TXT

Script ini dibuat untuk membantu mencegah kesalahan target ketika bekerja dengan daftar aset yang memang sudah diizinkan.

### Format `scope.txt`

```text
example.com
api.example.com
app.example.com
```

### Script

```bash
#!/usr/bin/env bash

# ============================================================
# SCOPE GUARD
# ============================================================
# Fungsi: memastikan hostname yang akan diuji tercantum dalam
# daftar scope.txt.
#
# PENTING:
# File ini TIDAK menentukan legalitas. Policy program tetap
# menjadi sumber kebenaran.
# ============================================================

set -euo pipefail

SCOPE_FILE="${SCOPE_FILE:-./scope.txt}"
TARGET="${1:-}"

if [[ -z "$TARGET" ]]; then
    echo "Usage: $0 hostname"
    echo "Contoh: $0 app.example.com"
    exit 1
fi

if [[ ! -f "$SCOPE_FILE" ]]; then
    echo "[!] Scope file tidak ditemukan: $SCOPE_FILE"
    exit 1
fi

if grep -Fqx "$TARGET" "$SCOPE_FILE"; then
    echo "[+] IN SCOPE: $TARGET"
    exit 0
fi

echo "[-] TIDAK DITEMUKAN DI scope.txt: $TARGET"
echo "[!] Jangan menguji target sebelum scope/policy diverifikasi."
exit 2
```

### Penggunaan

```bash
chmod +x scope-check.sh
./scope-check.sh app.example.com
```

### Catatan penting

Subdomain seperti `dev.example.com` tidak otomatis boleh diuji hanya karena `example.com` tercantum. Periksa aturan program.

---

## 46.8 HASH FILE — PYTHON

### Fungsi
Menghitung SHA-256 file untuk integritas/evidence.

```python
#!/usr/bin/env python3

"""SHA-256 file checker."""

import hashlib
import sys
from pathlib import Path

if len(sys.argv) != 2:
    print(f"Usage: {sys.argv[0]} FILE")
    raise SystemExit(1)

path = Path(sys.argv[1])

if not path.is_file():
    print(f"[!] File tidak ditemukan: {path}")
    raise SystemExit(1)

sha256 = hashlib.sha256()

with path.open("rb") as file:
    for chunk in iter(lambda: file.read(1024 * 1024), b""):
        sha256.update(chunk)

print(f"SHA256  {sha256.hexdigest()}  {path}")
```

### Penggunaan

```bash
python3 hash-file.py evidence.txt
```

---

## 46.9 RECON NOTES GENERATOR

Script ini hanya membuat struktur catatan; tidak melakukan scanning.

```bash
#!/usr/bin/env bash

# YANG PERLU DIGANTI:
#   PROGRAM="nama-program"

set -euo pipefail

PROGRAM="${1:-my-program}"
DIR="bug-bounty/$PROGRAM"

mkdir -p "$DIR"/{findings,evidence}

touch "$DIR"/{scope.md,recon.md,assets.txt,urls.txt,endpoints.md,technologies.md,notes.md}

echo "[+] Struktur dibuat: $DIR"
```

Hasil:

```text
bug-bounty/my-program/
├── scope.md
├── recon.md
├── assets.txt
├── urls.txt
├── endpoints.md
├── technologies.md
├── notes.md
├── findings/
└── evidence/
```

---

# 47. TEMPLATE INSTALLATION UNTUK SCRIPT

Setiap kali menambahkan tool baru ke repository, gunakan format berikut:

```markdown
## TOOL NAME

### Fungsi
Jelaskan fungsi tool.

### Dependency
- dependency-1
- dependency-2

### Installation
```bash
# command installation
```

### Konfigurasi
```text
YANG PERLU DIGANTI:
TARGET=...
WORDLIST=...
OUTPUT=...
```

### Basic usage
```bash
# command aman untuk lab
```

### Parameter
- `-x` = penjelasan
- `-y` = penjelasan

### Output
Jelaskan arti output.

### Troubleshooting
Jelaskan error umum.

### Safety
Gunakan hanya pada target yang dimiliki atau diizinkan.
```

---

# 48. ATURAN MEMBUAT SCRIPT SIAP PAKAI

Setiap script baru dalam repository ini sebaiknya selalu mempunyai:

```text
[ ] Nama script
[ ] Tujuan
[ ] Dependency
[ ] Cara install dependency
[ ] Variabel yang perlu diganti
[ ] Nilai default yang aman
[ ] Contoh command
[ ] Penjelasan setiap parameter
[ ] Contoh output
[ ] Troubleshooting
[ ] Batasan penggunaan
[ ] Catatan scope/izin
```

## Variabel konfigurasi yang disarankan

```bash
TARGET="http://127.0.0.1:3000"
WORDLIST="./wordlist.txt"
OUTPUT="./results.txt"
TIMEOUT=10
RATE=5
```

Dengan pola ini, pengguna tidak perlu mencari bagian script yang harus diubah.

---

# 49. SCRIPT VS TOOL — JANGAN SALAH MEMAHAMI

Script wrapper seperti:

```text
nmap
ffuf
nuclei
curl
```

bukan pengganti pemahaman tool.

Sebelum menjalankan automation:

```text
1. Baca dokumentasi tool
2. Pahami command
3. Pahami target
4. Pahami output
5. Pahami false positive
6. Pastikan scope
7. Jalankan dengan rate rendah terlebih dahulu
8. Verifikasi hasil secara manual
```

---

# 50. BUG BOUNTY AUTOMATION SAFETY CHECK

Sebelum menjalankan script terhadap program bug bounty:

```text
[ ] Program masih aktif?
[ ] Asset berada dalam scope?
[ ] Endpoint berada dalam scope?
[ ] Automation diizinkan?
[ ] Rate limit diketahui?
[ ] Scanner diizinkan?
[ ] Crawling diizinkan?
[ ] Brute force dilarang atau diizinkan?
[ ] Data pengguna boleh diakses sampai batas apa?
[ ] Destructive testing dilarang?
[ ] Disclosure rule sudah dibaca?
```

Jika policy tidak jelas, jangan mengasumsikan bahwa aktivitas tersebut diizinkan.

---

# 51. SCRIPT TROUBLESHOOTING CHECKLIST

Jika script gagal:

```bash
command -v curl
command -v nmap
command -v ffuf
command -v nuclei
python3 --version
git --version
```

Periksa:

```bash
echo "$PATH"
pwd
ls -la
```

Untuk permission:

```bash
chmod +x script.sh
```

Untuk Bash syntax:

```bash
bash -n script.sh
```

Untuk Python syntax:

```bash
python3 -m py_compile script.py
```

Jangan langsung menjalankan script yang gagal berulang kali tanpa membaca error. Identifikasi dependency atau konfigurasi yang salah terlebih dahulu.

---

# 52. FINAL READY-TO-USE WORKFLOW

```text
Install tool
    ↓
Read documentation
    ↓
Create local lab
    ↓
Set TARGET=127.0.0.1
    ↓
Run script
    ↓
Read output
    ↓
Understand finding
    ↓
Reproduce manually
    ↓
Document evidence
    ↓
Learn remediation
    ↓
Only then consider authorized bug-bounty testing
```

**Default aman:** semua contoh script menggunakan `127.0.0.1` atau aplikasi lab. Untuk target bug bounty, nilai `TARGET`, scope, rate, dan jenis automation harus disesuaikan dengan policy program yang bersangkutan.
