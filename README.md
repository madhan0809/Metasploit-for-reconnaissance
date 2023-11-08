# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## PROGRAM:
Find out the ip address of the attackers system


## OUTPUT:

![output 1](https://github.com/madhan0809/Metasploit-for-reconnaissance/assets/119165530/58da5b1a-2c17-42e9-8908-93173a6e323b)

## Invoke msfconsole:
## OUTPUT:
![output 2](https://github.com/madhan0809/Metasploit-for-reconnaissance/assets/119165530/73e41658-f2d6-42ba-9f2e-2b7daac4dbe9)


Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## OUTPUT:
![output 3](https://github.com/madhan0809/Metasploit-for-reconnaissance/assets/119165530/64509c14-ca8b-4914-be3c-690ee0932600)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:

![output 4](https://github.com/madhan0809/Metasploit-for-reconnaissance/assets/119165530/ccc37f64-25dc-432c-bdf3-f38451050668)


 ## Step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:
![output 5](https://github.com/madhan0809/Metasploit-for-reconnaissance/assets/119165530/8570b3ae-2f3b-4ffb-a145-c182e1649c0a)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:

![output 6](https://github.com/madhan0809/Metasploit-for-reconnaissance/assets/119165530/d2cbc2bb-3b0d-4c62-9467-1e3443f12bf5)

![output 7](https://github.com/madhan0809/Metasploit-for-reconnaissance/assets/119165530/eb75f15e-453c-4179-a4fd-8ee660ccd5b2)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![output 8](https://github.com/madhan0809/Metasploit-for-reconnaissance/assets/119165530/cbf4c804-f966-4fbc-98f3-08426b4e729e)

The info command provides information regarding a module or platform
## OUTPUT:

![output 9](https://github.com/madhan0809/Metasploit-for-reconnaissance/assets/119165530/ea124c81-fb69-4753-8dad-119916d22b20)


Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![output 10](https://github.com/madhan0809/Metasploit-for-reconnaissance/assets/119165530/6d998135-8d8f-4f89-a18d-104ce2ee5cf0)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![output 11](https://github.com/madhan0809/Metasploit-for-reconnaissance/assets/119165530/00b8cd72-882d-4bd9-b3c3-b3b5a77287ff)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![output 12](https://github.com/madhan0809/Metasploit-for-reconnaissance/assets/119165530/71ae79f9-cb74-4be1-9bd9-4cb571c1b1b7)


Use the set rhosts command to set the parameter and run the module, as follows:

![output 13](https://github.com/madhan0809/Metasploit-for-reconnaissance/assets/119165530/100f079b-29cb-44da-8feb-3fb2715c6971)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![output 14](https://github.com/madhan0809/Metasploit-for-reconnaissance/assets/119165530/a3f72cf1-dab4-49ab-ba73-343323f67151)


set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![output 15](https://github.com/madhan0809/Metasploit-for-reconnaissance/assets/119165530/e569f204-976b-49cc-91d3-025326b552c6)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
