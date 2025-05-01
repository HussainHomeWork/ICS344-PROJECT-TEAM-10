# Phase 1: Setup and Compromise the Service

This folder contains our implementation of Phase 1 of the ICS344 course project, which involves setting up and compromising a vulnerable service.

## Service Selection

For this project, we selected **IIS FTP** as our target service from the list of vulnerable services available on Metasploitable3.

## Environment Setup

We created two virtual environments:

1. **Victim Environment**: Metasploitable3 on VirtualBox
2. **Attacker Environment**: Kali Linux with Metasploit Framework

Detailed setup instructions and screenshots can be found in the [setup file](./setup.md).

## Attack Execution

We performed two types of attacks on the IIS FTP service:

1. **Using Metasploit Framework**: We utilized the built-in exploits in Metasploit to compromise the FTP service.
2. **Custom Script**: We developed a custom Python script that automates the exploitation process.

Detailed attack documentation and screenshots can be found in the [attack file](./attack.md).
