# Phase 1: Setup and Compromise the Service

This folder contains our implementation of Phase 1 of the ICS344 course project, which involves setting up and compromising a vulnerable service.

## Service Selection

For this project, we selected **ProFTPD 1.3.5** as our target service from the list of vulnerable services available on Metasploitable3.

## Environment Setup

We created two virtual environments:

1. **Victim Environment**: Metasploitable3 on VirtualBox
2. **Attacker Environment**: Kali Linux with Metasploit Framework

Detailed setup instructions and screenshots can be found in the [setup file](./setup.md).

## Attack Execution

We performed two types of attacks on the ProFTPD 1.3.5 service:

1. **Using Metasploit Framework**: We utilized the `proftpd_modcopy_exec` exploit in Metasploit to compromise the FTP service.
2. **Custom Script**: We developed a custom Bash script that automates the exploitation process using the same vulnerability.

Detailed attack documentation and screenshots can be found in the [attack file](./attack.md) and [custom script documentation](./custom_script.md).
