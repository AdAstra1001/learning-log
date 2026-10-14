# Overthewire Bandit Walkthrough

## Level 13 -> Level 14
* **Objective:** Connect to the next level using a private SHH key stored on the server.

* **Step 1:** Found the private key file in the home directory using the 'ls' or 'find' command.
* **Step 2:** Displayed the contents of the key using 'cat ~/sshkey.private'.
* **Step 3:** Opened the native Kali Linux terminal on my local machine and created a new file with 'touch key14.txt'.
* **Step 4:** Manually copied the private key contents info 'key14.txt' and saved it using 'Ctrl + D'. 
* **Step 5:** Connected to the Level 14 server private key with the following command: 'ssh -i ~/key14.txt bandit14@bandit.labs.overthewire.org -p 2220' 
