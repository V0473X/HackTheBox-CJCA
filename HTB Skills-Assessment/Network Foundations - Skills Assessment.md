
# Overview:
	Explore the networking behind HTB Academy's lab envirionments. The assessment is divided into three chapters, but only the first two are required to complete the challenge questions and finish the assessment. The third chapter is optional for those who want to explore further.

# Assessment:
# Answers:
	Q1: What IPv4 address is used when a host wants to send and receive network traffic to itself?
	A1: The default loopback address and always associated with IPv4 is: 127.0.0.1

	Q2: What is the the name of the Program listening on localhost:5901 of the Pwnbox?
	A2: Xtigervnc 

	Q3: Which network interface allows us to interact with target machines in the HTB lab environment?
	A3: tun0

	Q4: What command-line tool is used to configure network interfaces and display their current status?
	A4: ifconfig

	Q5: What command-line tool is used to display network connections, routing information, and interface statistics?
	A5: netstat

## Optional Exercise:
	Q6: What is the FTP command used to retrieve a file? (Format: XXXX)
	A6:
	
	  ENUMERATION with NMAP:
	  - sudo nmap -sC -sV 10.129.169.192
	
	  Banner Grabbing:
	  - sudo nmap -sV --script=baner -p21,80 10.129.169.192
	
	  T/N: The ports shows anonymous login via FTP : 21. We'll try to exploit this service.
	
	  FOOTPRINTING:
	  - ftp 10.129.169.192 | login anonymous:anonymous
	  - ls -la, get Note-From-IT.txt, bye
	  - cat Note-From-IT.txt

	Q7: Bypass the request filtering found on the target machine's HTTP service, and submit the flag found in the response. The flag will be in the format: HTB{...}
	A7:
	
		NETCAT:
		nc -nv 10.129.169.192 80
		- GET / HTTP/1.1 
		- Host: 10.129.169.192
		- User-Agent: Server Administrator
		- FLAG: HTB{S00n_2_B_N3tw0rk1ng_GURU!}
