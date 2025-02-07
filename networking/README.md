# Week 1: Networking Fundamentals

## 1. Understanding OSI & TCP/IP Models

### OSI Model:
The OSI (Open Systems Interconnection) model is a conceptual framework that standardizes networking functions into seven layers. Each layer serves a specific role in the communication process.

#### OSI Layers:
1. **Physical Layer** - Handles physical connections (e.g., Ethernet cables, Wi-Fi signals).
2. **Data Link Layer** - Ensures reliable data transfer over the physical medium (e.g., MAC addresses in Ethernet switches).
3. **Network Layer** - Manages packet routing and forwarding (e.g., IP addressing).
4. **Transport Layer** - Provides end-to-end communication and error handling (e.g., TCP for reliable data delivery).
5. **Session Layer** - Maintains active sessions between applications (e.g., web browser and server communication).
6. **Presentation Layer** - Converts data formats for application use (e.g., encryption with SSL/TLS).
7. **Application Layer** - Interfaces directly with user applications (e.g., HTTP, SMTP).

### TCP/IP Model:
A more simplified framework than OSI, consisting of four layers.

#### TCP/IP Layers:
1. **Network Access Layer** - Equivalent to OSI’s Physical and Data Link layers (e.g., Ethernet, Wi-Fi).
2. **Internet Layer** - Corresponds to OSI’s Network Layer, responsible for IP addressing and routing.
3. **Transport Layer** - Handles reliable/unreliable data transmission using TCP or UDP.
4. **Application Layer** - Merges OSI’s top three layers, supporting application protocols like HTTP, FTP, and DNS.

## 2. Key Network Protocols & Ports
Understanding key protocols and their respective port numbers is essential for DevOps and system administration.

| Protocol  | Port  | Function  |
|-----------|------|--------------------------|
| HTTP      | 80   | Standard web traffic     |
| HTTPS     | 443  | Secure web communication |
| FTP       | 21   | File transfer            |
| SSH       | 22   | Secure remote access     |
| DNS       | 53   | Domain name resolution   |
| SMTP      | 25   | Email transmission       |
| MySQL     | 3306 | Database connection      |

## 3. Setting Up an AWS EC2 Instance & Security Groups
### Steps to Launch an EC2 Instance:
1. Log in to the AWS Console.
2. Navigate to the EC2 Dashboard.
3. Click on **Launch Instance**.
4. Enter a name for the instance.
5. Choose an Amazon Machine Image (AMI).
6. Select or create a **Key Pair** for authentication.
7. Create a **Security Group** and allow necessary ports (e.g., 80, 443, 22).
8. Launch the instance.

### Configuring Security Groups:
- Select the created **Security Group**.
- Configure **Inbound Rules** to allow traffic on required ports (e.g., 80 for HTTP, 443 for HTTPS, 22 for SSH).
- Configure **Outbound Rules** to define outgoing traffic permissions.

## 4. Essential Networking Commands Cheat Sheet
Practicing these commands will help you troubleshoot and analyze network-related issues.

| Command    | Purpose                                  | Example                        |
|-----------|----------------------------------|------------------------------|
| `ping`    | Check connectivity to a host    | `ping google.com`           |
| `traceroute` | Trace the packet route         | `traceroute google.com` (Linux) |
| `netstat`  | Display network connections    | `netstat -an`               |
| `curl`    | Make HTTP requests via CLI      | `curl https://api.example.com/data` |
| `dig`     | Perform DNS lookups             | `dig google.com`            |
| `nslookup` | Query DNS records              | `nslookup google.com`       |

---


