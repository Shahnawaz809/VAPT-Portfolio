# Metasploitable 2 - Penetration Test Report

**Date:** September 11, 2026
**Target IP:** 192.168.138.67
**Status:** ✅ ROOT ACCESS ACHIEVED

## Executive Summary
Successfully identified and exploited critical vulnerability in vsftpd 2.3.4, 
achieving complete system compromise with root-level access.

## Vulnerabilities Found

### 1. vsftpd 2.3.4 Backdoor [CRITICAL]
- **Service:** FTP (Port 21)
- **CVE:** CVE-2011-2523
- **Impact:** Remote Code Execution → Root Access
- **Status:** ✅ EXPLOITED

### 2. Weak Password Hashes [HIGH]
- 6 user passwords cracked using John the Ripper
- Time to crack: < 1 minute with rockyou.txt wordlist

### 3. Multiple Vulnerable Services [MEDIUM]
- Samba 3.0.20-Debian
- MySQL 5.0.51a
- Apache 2.2.8
- Tomcat 5.5

## Exploitation Chain

1. **Reconnaissance:** Nmap scan → 20+ open ports
2. **Identification:** vsftpd 2.3.4 on port 21
3. **Exploitation:** Metasploit exploit/unix/ftp/vsftpd_234_backdoor
4. **Access:** Meterpreter reverse shell with root privileges
5. **Proof:** /etc/shadow extracted and cracked

## Cracked Credentials

| Username | Password |
|----------|----------|
| msfadmin | msfadmin |
| user | user |
| service | service |
| postgres | postgres |
| sys | batman |
| klog | 123456789 |

## Tools Used
- Nmap
- Metasploit Framework
- Meterpreter
- John the Ripper

## CVSS Score
**9.8 (Critical)**

## Recommendations
1. Update vsftpd immediately
2. Disable FTP (use SFTP instead)
3. Network segmentation
4. Deploy IDS/IPS
5. Regular vulnerability scanning

---
**Penetration Tester:** Shahnawaz  
**Date:** September 11, 2026
