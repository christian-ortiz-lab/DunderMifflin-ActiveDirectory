#  🏢 Dunder Mifflin Active Directory Pentesting Lab  

**A fun, themed Active Directory (AD) lab for practicing penetration testing—inspired by *The Office (US)*!**  

## 🔍 Overview  
This lab simulates a real-world **corporate AD environment** (but with *The Office* flair) to help you practice:  
✅ **Initial Access** (Phishing, Exploits)  
✅ **Credential Theft** (Mimikatz, LSASS Dumping)  
✅ **Privilege Escalation** (Kerberoasting, DCSync)  
✅ **Lateral Movement** (Pass-the-Hash, RDP Hijacking)  
✅ **Persistence** (Golden Tickets, GPO Backdoors)  

All while dealing with **Michael Scott’s weak passwords**, **Dwight’s overconfidence in security**, and **Kevin’s auto-logon habits**.  

---

## 🖥️ Lab Architecture  
### **Domain:** `DUNDERMIFFLIN.LOCAL`  
### **Key Servers:**  
- **DC-DWIGHT** (`192.168.1.10`) – Primary Domain Controller (Dwight’s strict but flawed setup)  
- **DC-JIM** (`192.168.1.11`) – Secondary DC (Jim’s "prankster" misconfigurations)  
- **FS-PAM** (`192.168.1.12`) – File Server (Pam’s poorly permissioned shares)  

### **Workstations:**  
| Hostname    | User           | Password       | Vulnerability                |  
|-------------|----------------|----------------|------------------------------|  
| WS-MICHAEL  | michael.scott  | `Password123!` | Domain Admin (weak creds)    |  
| WS-DWIGHT   | dwight.schrute | `Battlestar42` | "Secured" (but vulnerable SMB)|  
| WS-KEVIN    | kevin.malone   | `Chili4Life`   | Auto-logon enabled           |  

---

## 🎯 Attack Scenarios  
1. **Phish Pam** with a malicious Word macro (`Art_Exhibit_Invite.docm`).  
2. **Dump Kevin’s plaintext password** (thanks to auto-logon).  
3. **Kerberoast Jim’s service account** (`jim.admin`).  
4. **Exploit Michael’s Domain Admin** access to **DCSync** the entire domain.  
5. **Pivot to Dwight’s "secure" workstation** using Pass-the-Hash.  

---

## 🛠️ Setup Guide  
1. **Deploy VMs** (Windows Server 2019 + Windows 10).  
2. **Set up Domain Controllers** (`DC-DWIGHT`, `DC-JIM`) and promote to AD.  
3. **Create users** (see [Users & Passwords](#-users--passwords)).  
4. **Introduce vulnerabilities** (misconfigured shares, weak GPOs, etc.).  

> **Pro Tip:** Use **PowerShell scripts** to automate user creation (ask for examples!).  

---

## 🧠 Why This Lab?  
- **Realistic AD flaws** (but with *The Office* humor).  
- **Hands-on practice** for OSCP, CRTO, and pentesting exams.  
- **Customizable**—add more workstations (e.g., `WS-ANGELA` for strict ACLs).  

---

## 📚 Resources  
- [BloodHound](https://github.com/BloodHoundAD/BloodHound) – Map attack paths.  
- [Impacket](https://github.com/fortra/impacket) – For DCSync, Kerberoasting, etc.  
- [Atomic Red Team](https://atomicredteam.io/) – Simulate attacks.  

---

## 🎉 Final Notes  
> *"Identity theft is not a joke, Jim!"* — Dwight Schrute, probably after seeing Mimikatz in action.  

**Contributions welcome!** Add your own *Office*-themed vulnerabilities.  

---  
**Happy Hacking!**  
