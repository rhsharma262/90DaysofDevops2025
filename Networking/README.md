Week 1: Networking Challenge
1. Understanding OSI and TCP/IP Models
The OSI Model is a framework that explains how data travels across a network. It has 7 layers, each with a specific job:
1.	Physical Layer: Deals with hardware like cables and Wi-Fi signals.
2.	Data Link Layer: Ensures data is sent correctly between devices using MAC addresses.
3.	Network Layer: Handles routing data between networks using IP addresses.
4.	Transport Layer: Manages reliable data delivery (e.g., TCP for web browsing).
5.	Session Layer: Keeps communication sessions alive (e.g., between a browser and server).
6.	Presentation Layer: Translates data into a usable format (e.g., encryption or compression).
7.	Application Layer: Provides services like HTTP for websites or SMTP for emails.
The TCP/IP Model is simpler, with 4 layers:
1.	Network Access Layer: Combines OSI’s Physical and Data Link layers (e.g., Ethernet or Wi-Fi).
2.	Internet Layer: Handles IP addressing and routing.
3.	Transport Layer: Uses TCP (reliable) or UDP (fast) for data delivery.
4.	Application Layer: Combines OSI’s top three layers (e.g., HTTP, FTP, DNS).
________________________________________
2. Protocols and Ports for DevOps
Learn about common protocols and their port numbers:
Protocol	Port	Purpose
HTTP	80	Web traffic
HTTPS	443	Secure web traffic
FTP	21	File transfer
SSH	22	Secure remote access
DNS	53	Domain name resolution
SMTP	25	Email delivery
MySQL	3306	Database access
________________________________________
3. AWS EC2 and Security Groups
Step-by-Step Guide to Create an EC2 Instance:
1.	Log in to the AWS Console.
2.	Go to the EC2 Dashboard.
3.	Click Launch Instance.
4.	Name your instance.
5.	Choose an AMI (Amazon Machine Image).
6.	Create or select a key pair for secure access.
7.	Set up a Security Group to allow traffic on ports 80 (HTTP), 443 (HTTPS), and 22 (SSH).
8.	Launch the instance.
Configuring Security Groups:
•	Select the created Security Group.
•	Set Inbound Rules to allow traffic on required ports (e.g., 22 for SSH, 80 for HTTP).
•	Set Outbound Rules to control outgoing traffic.
________________________________________
4. Hands-On with Networking Commands
Practice these essential commands:
Command	Purpose	Example
ping	Check connectivity to a host.	ping google.com
traceroute	Trace the path packets take.	traceroute google.com (Linux)
netstat	Show network connections.	netstat -an
curl	Make HTTP requests.	curl https://api.example.com
dig	Perform DNS lookups.	dig google.com
nslookup	Query DNS records.	nslookup google.com

