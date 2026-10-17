# Overthewire Bandit Walkthrough

## Level 16 -> Level 17
* **Objective:** Find the one port in the range 31000-32000 on localhost that speaks SSL/TLS and returns credentials (an SSH private key) when the current password is submitted.
* **Step 1:** Scanned the port range for open ports: 'nmap -p 31000-32000 localhost' (5 open ports found).
* **Step 2:** Identified which services use SSL/TLS with version detection: 'nmap -sV -p 31000-32000 localhost' (2 of the 5 ports use SSL).
* **Step 3:** Tested each SSL port with OpenSSL, submitting the Level 16 password: 'openssl s_client -connect localhost:<port> -quiet'. The '-quiet' flag is required, otherwise the session treats certain input as commands instead of data. Port 31518 only echoed the input back, while port 31790 returned the RSA private key for the next level.
* **Step 4:** Opened a second terminal and saved the key to a file with 'cat > key17', then pasted the key and finished with Ctrl+D. Restricted the file permissions: 'chmod 600 key17' (SSH rejects keys readable by others).
* **Step 5:** Logged in to the next level using the private key: 'ssh -i key17 bandit17@bandit.labs.overthewire.org -p 2220'.
* **Key takeaway:** 'nmap -sV' helps separate SSL/TLS services from plain ones. Key-based authentication replaces the password here, so private key file permissions matter.