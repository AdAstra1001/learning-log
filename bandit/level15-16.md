# Portfolio: Overthewire Bandit Walkthrough

## Level 15 -> Level 16
* **Objective:** Submit the current password to port 30001 on localhost using SSL/TLS encryption.

* **Step 1:** Established a secure SSL/TLS connection using OpenSSL: 'openssl s_client -connect localhost:30001'
* **Step 2:** Verified the secure tunnel was open and active (indicated by a blank waiting terminal line).
* **Step 3:** Pasted the level 15 password and received the Level 16 password in response.
