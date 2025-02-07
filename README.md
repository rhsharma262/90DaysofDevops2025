# Week 1: Networking Challenge

# Tasks:

## 1. Understand OSI & TCP/IP Models

The OSI (Open Systems Interconnection) model is a conceptual framework with 7 layers.
Each layer has a specific role in data transmission, following are the 7 layers of OSI Model.

# Layers:
## 1. Physical Layer
## 2. Data Link Layer
## 3. Network Layer
## 4. Transport Layer
## 5. Session Layer
## 6. Presentation Layer
## 7. Application Layer

1. **Physical Layer**: Deals with the physical connection between devices.
Example: Ethernet cables, Wi-Fi signals, or fiber optics cables.

2. **Data Link Layer**: Ensures reliable data transfer over the physical layer. It comes over the physical layer.
Example: MAC addresses used in Ethernet switches to forward data to the correct device.

3. **Network Layer**: Handles routing and forwarding of data packets.
Example: IP addresses used by routers to send data between different networks.

4. **Transport Layer**: Ensures end-to-end communication and error recovery.
Example: TCP (Transmission Control Protocol) ensures reliable data delivery for web browsing.

5. **Session Layer**: Manages sessions between applications.
Example: Establishing and maintaining a session between a web browser and a server.

6. **Presentation Layer**: Translates data into a format the application can understand.
Example: Encryption (SSL/TLS) or data compression.

7. **Application Layer**: Provides network services to applications.
Example: HTTP for web browsing or SMTP for sending emails.


# TCP/IP Model:

The TCP/IP model is a simplified version of the OSI model with 4 layers.

## 1. Network Access Layer
## 2. Internet Layer
## 3. Transport Layer
## 4. Application Layer

1. **Network Access Layer**: Combines OSI’s Physical and Data Link layers. Example: Ethernet or Wi-Fi protocols.
2. **Internet Layer**: Corresponds to OSI’s Network Layer. Example: IP (Internet Protocol) for addressing and routing.
3. **Transport Layer**: Same as OSI’s Transport Layer. TCP (reliable) or UDP (fast) for data delivery.
4. **Application Layer**: Combines OSI’s Session, Presentation, and Application layers. Example: HTTP, FTP, DNS, or SSH.

---

# 2. Protocols and Ports for DevOps

Study the most commonly used protocols (e.g., HTTP, HTTPS, FTP, SSH, DNS) and their port numbers. 

| Protocol | Port  | Purpose                    |
|----------|------|-----------------------------|
| HTTP     | 80   | Web traffic                 |
| HTTPS    | 443  | Secure web traffic          |
| FTP      | 21   | File transfer               |
| SSH      | 22   | Secure remote access        |
| DNS      | 53   | Domain name resolution      |
| SMTP     | 25   | Email delivery              |
| MySQL    | 3306 | Database access             |

---

# 3: AWS EC2 and Security Groups

Step-by-Step Guide to Create Ec2 Instance and Configure Security Groups

1. Login to AWS Console
2. Navigate to Ec2 Dashboard
3. Launch Instance
4. Name Instance
5. Select AMI
5. Key Pair
6. Create Security Group 80, 443 and 22.
7. Launch Instance

# Security Groups:

1. Select Created Security Group
2. Configure Inbound and Outbound traffic like 80, 443, 22 or other required ports.

---

# 4. Hands-On with Networking Commands

Practice essential networking commands like: 

## Cheat Sheet for Networking Commands:
| Command     | Purpose                                    | Example                                  |
|------------|---------------------------------------------|------------------------------------------|
| `ping`     | Check connectivity to a host.               | `ping google.com`                        |
| `traceroute` | Trace the path packets take to a host.    | `traceroute google.com` (Linux)          |
| `netstat`  | Display network connections and statistics. | `netstat -an` (show all connections)     |
| `curl`     | Make HTTP requests from the command line.   | `curl https://api.example.com/data`      |
| `dig`      | Perform DNS lookups.                        | `dig google.com`                         |
| `nslookup` | Query DNS records.                          | `nslookup google.com`                    |


