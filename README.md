# \U0001F47D ScottsTechX Responder

<p align="center">
  <img src="https://img.shields.io/badge/MITM-Attack-00ff88?style=for-the-badge&logo=linux&logoColor=black" alt="MITM"/>
  <img src="https://img.shields.io/badge/Credential-Theft-00ff88?style=for-the-badge&logo=shield&logoColor=black" alt="Credential Theft"/>
  <img src="https://img.shields.io/badge/Network-Security-00ff88?style=for-the-badge&logo=wifi&logoColor=black" alt="Network Security"/>
</p>

> **LLMNR/NBT-NS poisoner for network credential harvesting.**

---

## \u26A1 What It Does

Responder poisons LLMNR and NBT-NS requests on a network to capture username/password hashes \u2014 a classic lateral movement technique used in penetration testing and red team engagements.

\u26A0 **For authorized security testing only. Unauthorized use is illegal.**

## \U0001F680 Quick Usage

```bash
# Run with default settings (all protocols)
sudo python3 Responder.py -I eth0

# Analyze mode (no poisoning)
sudo python3 Responder.py -I eth0 -A

# Enable specific servers
sudo python3 Responder.py -I eth0 --NBTNS --LMHASH

# Spoof WPAD
sudo python3 Responder.py -I eth0 --wpadown
```

## \U0001F3AF Hash Capture

| Protocol | Hash Type | What You Get |
|----------|-----------|-------------|
| HTTP | NTLMv1/v2 | Web creds |
| SMB | NTLMv1/v2 | SMB login |
| LDAP | NTLM | AD credentials |
| MSSQL | NTLM | DB login |
| SMTP | NTLM | Mail login |

## \U0001F6E1 Defense

- **Disable LLMNR** via Group Policy
- **Harden NBT-NS** \u2014 block port 137/138
- **Enable SMB signing** \u2014 prevents relay attacks
- **Network segmentation** \u2014 isolate critical systems

---

## \u26A0 Legal Notice

This tool is for **authorized penetration testing** and **red team operations** only. Unauthorized interception of network traffic is illegal.

---

## \U0001F837 License

MIT License \u2014 [ScottsTechX](https://github.com/fredscottsbulls) \u00a9 2026
