Week 1: Networking Basics and Hands-on Practice
1. Understanding OSI & TCP/IP Models
Networking is built on structured models that help in communication between devices. Two major models are:

OSI Model (7 Layers)
The OSI model is a conceptual framework that standardizes network communication into seven layers, each with a unique role:

Physical Layer – Deals with actual hardware like cables, Wi-Fi signals, and fiber optics.
Data Link Layer – Ensures reliable data transfer using MAC addresses in Ethernet switches.
Network Layer – Handles routing and IP addressing, helping devices communicate across networks.
Transport Layer – Ensures proper data delivery using protocols like TCP (reliable) and UDP (faster but less reliable).
Session Layer – Manages active connections, such as maintaining a web session between a browser and a server.
Presentation Layer – Converts data formats and handles encryption (e.g., SSL/TLS for secure connections).
Application Layer – Provides network services like HTTP (web browsing) and SMTP (email sending).
TCP/IP Model (4 Layers)
The TCP/IP model is a simpler version of the OSI model, widely used in real-world networking.

Network Access Layer – Combines Physical & Data Link layers (e.g., Ethernet, Wi-Fi).
Internet Layer – Handles IP addressing and routing (e.g., IP protocol).
Transport Layer – Manages communication reliability (TCP for reliability, UDP for speed).
Application Layer – Merges OSI’s top three layers, supporting protocols like HTTP, FTP, and SSH.
2. Common Protocols and Ports in DevOps
Protocols help devices communicate over networks, and each protocol uses a specific port number:

Protocol	Port	Purpose
HTTP	80	Web browsing
HTTPS	443	Secure web browsing
FTP	21	File transfers
SSH	22	Secure remote access
DNS	53	Resolves domain names to IPs
SMTP	25	Email sending
MySQL	3306	Database access
3. Setting Up an AWS EC2 Instance with Security Groups
To deploy a virtual server (EC2 instance) on AWS, follow these steps:

Creating an EC2 Instance
Log in to your AWS console.
Open the EC2 Dashboard and click Launch Instance.
Enter an instance name.
Choose an AMI (Amazon Machine Image).
Select or create a key pair for secure access.
Configure a Security Group with necessary inbound rules (e.g., allowing traffic on ports 80, 443, and 22).
Click Launch to create the instance.
Configuring Security Groups
Open the Security Groups section.
Modify inbound rules to allow specific traffic (e.g., port 80 for HTTP, port 443 for HTTPS, and port 22 for SSH).
Modify outbound rules if needed.
4. Essential Networking Commands for Hands-on Practice
Below are some useful commands to troubleshoot and test network connectivity:

Command	Purpose	Example Usage
ping	Checks if a system is reachable.	ping google.com
traceroute	Shows the path taken by packets.	traceroute google.com (Linux)
netstat	Displays active connections.	netstat -an
curl	Sends HTTP requests from the command line.	curl https://api.example.com/data
dig	Performs DNS lookups.	dig google.com
nslookup	Queries DNS records.	nslookup google.com
