# Environment Setup Documentation

## Victim Environment: Metasploitable3

### Installation Steps

1. **Downloaded Metasploitable3 OVA**
   - Downloaded the pre-built Metasploitable3 OVA file from: <https://sourceforge.net/projects/metasploitable3-ub1404upgraded/files/>

   ![setup 1](./screenshots/setup-1.png)

2. **Imported OVA into VirtualBox**
   - Clicked File → Import Appliance
   - Selected the downloaded OVA file

    ![setup 2](./screenshots/setup-2.png)

3. **Configured VM Settings**
   - RAM: 2GB
   - CPU: 2 cores
   - Network: Bridged Adapter (to allow communication between VMs)

    ![setup 3](./screenshots/setup-3.png)

4. **Started the Metasploitable3 VM**
   - Logged in with default credentials:
     - Username: `vagrant`
     - Password: `vagrant`

   ![setup 4](./screenshots/setup-4.png)

5. **Network Configuration**
   - Identified IP address using `ifconfig`

   ![setup 5](./screenshots/setup-5.png)

6. **Verified Running Services**
   - Used `netstat -tuln` to check running services
   - Confirmed FTP service running on port 21

   ![setup 6](./screenshots/setup-6.png)

## Attacker Environment: Kali Linux

1. **Downloaded Kali Linux**
   - Downloaded Kali Linux VirtualBox image from official website

   ![setup 7](./screenshots/setup-7.png)

2. **Imported and Configured Kali Linux**
   - Imported the VDI file into VirtualBox
   - Configured with 4GB RAM and 2 CPU cores
   - Set network to Host-only Adapter (same as Metasploitable3)

   ![setup 8](./screenshots/setup-8.png)

3. **Started Kali Linux**
   - Default credentials:
     - Username: `kali`
     - Password: `kali`

   ![setup 9](./screenshots/setup-9.png)

4. **Network Configuration**
   - Identified IP address using `ifconfig`

   ![setup 10](./screenshots/setup-10.png)

5. **Installed Metasploit Framework**
   - Updated system: `sudo apt update && sudo apt upgrade -y`
   - Installed Metasploit: `sudo apt install metasploit-framework -y`

   ![setup 11](./screenshots/setup-11.png)

6. **Connectivity Test**
   - Pinged Metasploitable3 from Kali: `ping 192.168.56.102`
   - Confirmed connectivity between machines

   ![setup 12](./screenshots/setup-12.png)

## Service Identification

1. **Port Scanning**
   - Ran Nmap scan: `nmap -sV 192.168.56.102`
   - Identified ProFTPD service running on port 21

   ![setup 13](./screenshots/setup-13.png)

2. **Service Enumeration**
   - Connected to FTP service: `ftp 192.168.56.102`
   - Identified banner information showing ProFTPD 1.3.5
   - Attempted anonymous login

   ![setup 14](./screenshots/setup-14.png)

## Environment Verification

- Both VMs are properly configured and can communicate with each other
- Target service (ProFTPD 1.3.5) is accessible from the attacker machine
- All tools required for the attack are installed and working correctly
