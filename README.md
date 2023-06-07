# Network-Security# Linux-Forensics

<h1> This is an exercise provided by the TryHackMe DFIR course </h1>

 
 #### All images and copyrights are protected for TryHackMe

<h2>Description</h2>
Project: Network Security Practise 
Objective: Attack a network and gain information as a red team.

<h2>Tools/ Utilities Used</h2>

- <b>Linux Virtual Machine</b>
- <b>terminal ( command tool)</b>
- <b>Attack Box</b>

Tasks:

1- Find a password for a secret.txt file.

2- FIdn the content for a flag.txt file in the /root

3- Find the content of  flag. txt in the /home/librarian directory.


Actions:

To get to the secret.txt we need to do some rec ( reconnaissance) using the nmap with the IP for the target machine

  
![NETWORK rec nmap](https://github.com/TheRashaSharif/Network-Security/assets/98124961/1580c6ad-8fe0-42bb-b68a-9cb586b1cd4e)

we see the ports that open, one of them is the FTP and we can see the ftp in the same IP address for the target machine

![Network ftp](https://github.com/TheRashaSharif/Network-Security/assets/98124961/493c2164-40b3-4538-8a00-6fb808ad3f78)

This will allow us also to use the command ls to get a list of the files
then we can get the secret.txt and type bye or exit to get out of the ftp

To display the content we can use the command cat seceret.txt
The password is as the following:ABC789xyz123

![Network seceret password](https://github.com/TheRashaSharif/Network-Security/assets/98124961/0f06a5da-3984-4339-9829-6e10c1cc25a4)

This was task (1) password for seceret.txt is 



Task ( 2) is in the root so let's go there by typing 
root@10.10.11.118
the password can be anything but by trying the same one ABC789xyz123 a couple of times it worked and we gained access to the target 
![Networking root](https://github.com/TheRashaSharif/Network-Security/assets/98124961/b54cb36f-2516-4392-a340-311aeabb7883)

The password won't be displayed, there is no show password option which is the challenge.

to answer task 2 and find the content of flag.txt we have to find it by looking into psw ( print working directory)
then command ls to list the files
then use the cat flag,txt to get the content of it which is THM{FTP_Server_Owned}


![Network flag task 2](https://github.com/TheRashaSharif/Network-Security/assets/98124961/3db9b0f9-d716-48ad-9529-3f757060dbb4)

Task (3) is to find the flag.txt content in the /home/librarian
let's go there by changing directory to home 
cd /home
there we will type pwd to print the working directory
there is an account that is called librarian we can ls to list what is in it
flag.txt is the targeted file we can cat flag.txt to get the content:
THM{Librarian_account_compromised}

As shown this is completing task 3

![Networking task 3](https://github.com/TheRashaSharif/Network-Security/assets/98124961/6d9adc4b-81c1-448c-aa35-b2619436c535)
