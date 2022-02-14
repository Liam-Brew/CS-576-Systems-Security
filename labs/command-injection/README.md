# CS 576 Lab 02

## Command Injection

Command 1: "cat /etc/passwd"
Command 2: "cat | echo kali | sudo -S cat /etc/shadow"

## Path Traversal 

Path 1: "\0 /etc/passwd"
Path 2: " /etc/shadow"

## Security Hardening

I made the code secure by modifying how fn is created. Instead of 
using directory by itself, I split directory based on whitespace 
characters and used only the first index from that split. That 
prevented the vulnerabilities I used from working as the program
would only take in a single sub-argument (such as only the "cat" 
substring from the injected command "cat /etc/passwd"), thereby 
preventing the malicious parts of the input strings from being run. 