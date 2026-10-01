# wifi-network-scanner

A network reconnaissance tool built with python & scapy that performs ARP broadcast to map all active hosts on a lan. Useful for network admins to monitor unauthorized devices.

## How It Works 

1. It takes your local network range(for example - `192.168.1.1/24`)
2. It sends an **ARP REQUEST** to every possible IP in that range.
3. All active devices connected to the wi-fi replies with their MAC address.
4. We combine the IP and MAC address and display it in a table to show all the connected devices.

## Prerequisites for Windows
**Step 1: Install Npcap**
1. Download Npcap 1.88 installer from [Npcap download](https://nmap.org/npcap)<br>
**Note:** Install Npcap in WinPcap API-compatible Mode
![`Install npcap 1.88` as shown in image](image/npcap%20download.png)
   
## About Tools, protocol, modules used in building this project

**1. Python** <br>

Python is the industry-standard programming language for cybersecurity and ethical hacking because it allows security professionals to build custom tools, automate analysis, and react to threats at lightning speed. Security teams use it for both offensive penetration testing and defensive security operations.<br>
Security analysts use Python to map networks, find active hosts, and discover open ports.<br>

* **Scapy**: A powerful library used to forge, sniff, dissect, and manipulate network packets. It allows hackers to bypass firewalls or test network defenses.<br>
* **Socket**: A built-in module used to create raw network connections, often used to build custom port scanners.<br>

**2. ARP**<br>

ARP(Address Resolution Protocol) is a fundamental networking protocol used to map a dynamic IP address (logical layer 3 address) to a permanent physical MAC address (media access control layer 2 address) on a local network.Whenever a device wants to talk to another device on the same local network, it knows the target's IP address but needs its physical MAC address to actually deliver the data packets over the hardware.<br>

**3. Ether module (from Scapy)** <br>

In networking, Ether refers to Ethernet, the standard link-layer technology used to connect devices in a physically wired local area network (LAN). When working with cybersecurity and Python, the term "ether module" usually refers to how Python libraries—specifically Scapy—handle the Ethernet Frame header (Layer 2 of the OSI model).An Ethernet frame wraps around network data (like an IP packet) so it can travel across physical wires, switches, and network interface cards using physical MAC addresses.<br>

**4. srp() Function**<br>

`srp` stands for Send and Receive Packets at Layer 2. This function does the main work - it sends our crafted packets and listens for replies from connected devices.<br>

**5. IP Range / CIDR - `192.168.1.1/24`**<br>

`/24` is CIDR notation. It tells the scanner to check 254 IP addresses (from 192.168.1.1 to 192.168.1.254). You can change it according to your network. <br>

**6. Npcap**<br>

Npcap is a specialized kernel-level packet capture and injection architecture developed by the Nmap Project for the Microsoft Windows operating system. If you are using tools like Scapy (via Python), Wireshark, or Nmap on a Windows computer, NPCAP is the engine under the hood. It bridges the gap between Windows and raw hardware interfaces.<br>

## Installation & Usage 
**Step 1: Clone the repository**
```bash
git clone https://github.com/Jigyasa0601/wifi-network-scanner.git
cd wifi-network-scanner
```
**Step 2: Run the program**
```bash
python arp-scan.py
```

## Responsible Use

Use this scanner only on networks you own or have explicit permission to test 

Network Scanning without authorization may violate network policies or applicable laws

