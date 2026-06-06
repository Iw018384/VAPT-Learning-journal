# 🛡️ VAPT Learning Journal

## About Me
Hi, I'm Tisha Shah — a 2nd year Computer Science student, 
CEH certified, and currently building real hands-on 
cybersecurity skills.

This journal documents my daily VAPT practice — 
every command, every finding, every lesson learned.

## 🎯 Goal
Land a strong VAPT role and build expertise in 
penetration testing through daily hands-on practice.

## 📅 Daily Progress

### Day 1 — Environment Setup + Linux Fundamentals
Date: 01-06-2026

**What I did-
- Set up Kali Linux environment
- Installed VAPT tools: nmap, gobuster, nikto
- Created organized workspace folder structure
- Learned pentesting phases: Recon → Scanning → 
  Exploitation → Privilege Escalation → Reporting
- Completed OverTheWire Bandit Level 0-1
- Practiced Linux commands: ls, cd, cat, grep, find

**Key commands learned:**
- grep "keyword" file — filter specific data
- find . -type f -size 1033c — find files by size
- cat ./-filename — handle tricky filenames
- mkdir -p folder/{sub1,sub2} — create folder structure

**What I learned:**
Grep doesn't just search files — it filters any output.
Piping (|) chains commands together for efficiency.

### Day 2 — SSH + OverTheWire Bandit
Date:02-06-2026

What I did-
- Connected to remote server using SSH for first time
- Completed Bandit Levels 0-5
- Learned hidden files, file type identification, 
  command chaining

**Key commands learned:**
- ssh user@host -p port — remote server connection
- file ./* — identify file types without opening
- find . -type f -size 1033c | xargs cat — chain commands
- cat ./- — read files with tricky names
- ls -la — show hidden files

**Real VAPT connection:**
SSH is how pentesters access compromised servers remotely.
Hidden files are where attackers hide malware and passwords.
find command locates sensitive files across entire systems.

---

### Day 3 — Nmap Scanning
**Date:03-06-2026

**What I did:**
- Ran first real Nmap scan on legal target scanme.nmap.org
- Learned version detection, script scanning
- Identified 4 real security findings from 2 commands

**Key commands learned:**
- nmap target — basic port scan
- nmap -sV target — version detection
- nmap -sC target — script scan
- nmap -sV -sC -p 22,80 target — combined scan

**Findings on scanme.nmap.org:**
1. OpenSSH 6.6.1 (2014) — outdated, check for CVEs
2. Weak SSH key — 1024-bit DSA below modern standard
3. Apache 2.4.7 (2013) — outdated web server
4. Server version publicly disclosed — information disclosure

**What I learned:**
Open ports = potential entry points for attackers.
Version numbers reveal software age = known vulnerabilities.
-sC scripts act like automatic detective checks on each port.

## 🛠️ Tools I'm Learning
- Nmap — network scanning
- Gobuster — directory brute forcing (upcoming)
- Nikto — web vulnerability scanning (upcoming)
- Metasploit — exploitation framework (upcoming)

## 📚 Resources I'm Using
- OverTheWire Bandit — Linux skills
- TryHackMe — guided labs
- scanme.nmap.org — legal Nmap practice
- Claude - document everything structurally and present it on social platforms

  ### Day 4 — Gobuster + Nikto
**Gobuster findings on scanme.nmap.org:**
- .svn exposed — potential source code leak (Critical)
- .htpasswd exists — password file present (High)
- .htaccess exists — configuration file present (Medium)
- /images/ directory found
- /shared/ directory found

**Commands learned:**
- gobuster dir -u URL -w wordlist — basic directory scan
- gobuster dir -u URL -w wordlist -t 50 — faster with 50 threads
- nikto -h URL — automated web vulnerability scan
