**Passive Traffic Capture**
If tcpdump is installed, unprivileged users may be able to capture network traffic, including, in some cases, credentials passed in cleartext. 
Tools like **net-creds** sniffs passwords and hashes from interface or pcap file. Concatenates fragmented packets and does not rely on ports for service identification. 
https://github.com/DanMcInerney/net-creds
***net-cred sniffs***
  1. Urls visted
  2. POST loads sent
  3. HTTP form logins/passwords
  4. HTTP searches
  5. FTP logins/passwords
  6. IRC logins/passwords
  7. POP logins/passwords
  8. IMAP logins/passwords
  9. Telnet logins/passwords
  10. SMTP logins/passwords
  11. SNMP community string
  12. NTLMv1/v2 all supported protocols: HTTP. SMB, LDAP, etc.
  13. Kerberos

***PCredz***
This tool extracts Credit card numbers, NTLM(DCE-RPC, HTTP, SQL, LDAP, etc), Kerberos (AS-REQ Pre-Auth etype 23), HTTP Basic, SNMP, POP, SMTP, FTP, IMAP, etc 
from a pcap file or from a live interface.

