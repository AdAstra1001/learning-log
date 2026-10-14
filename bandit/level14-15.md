# Overthewire Bandit Walkthrough

## Level 14 -> Level 15
* **Objective:** Retrieve the password for the next level by submitting the current level's password to port 30000 on localhost.

* **Step 1:** Read the password for the current level from the server using 'cat /etc/bandit_pass/bandit14'.
* **Step 2:** Connected to the required port using Netcat with the command: 'nc localhost 30000'.
* **Step 3:** Pasted the copied password into the blank line using 'Citrl + V' and pressed Enter
* **Step 4:** The server successfully valdated the password and printed the new cleartext password for Level 15 directly below.