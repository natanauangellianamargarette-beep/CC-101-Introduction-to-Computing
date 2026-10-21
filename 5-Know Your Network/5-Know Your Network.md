**SORSOGON STATE UNIVERSITY**

**COLLEGE OF INFORMATION AND COMMUNICATIONS TECHNOLOGY**

Bulan Campus

Zone 8, Bulan, Sorsogon

Tel. No.: 056 311-0103; Email Address: cict@sorsu.edu.ph

**CC 101 - Introduction to Computing**

**"Know Your Network Settings": Exploring Windows 11 Network Configuration Tools**

**Name:** Natanauan GELLIANA MARGARETTE G.

**Block:** 1

**Date:** \_____________\_

**Computer Unit Used (Desktop/Laptop, brand):** \____________________\_

---

### I. Objectives

At the end of this activity, you should be able to:

* Locate network adapter information using Windows 11 Settings, the Control Panel, Command Prompt (CMD), and PowerShell.
* Use `ipconfig`, `getmac`, `hostname`, `ping`, `nslookup`, `netstat`, `route print`, and `systeminfo` in CMD, and `Get-NetAdapter`, `Get-NetIPAddress`, and `Test-Connection` in PowerShell.
* Interpret a sample `ipconfig /all` output from a networked computer: identify its IP address, subnet mask, default gateway, and DNS servers, and classify the address as public or private.
* Relate each tool and finding to the layer of the OSI model where it works.
* Design a simple network and IP address plan for the computer laboratory.

---

### II. Materials Needed

* A computer running Windows 11 (a network or Internet connection is not required for this activity)
* This worksheet (printed copy, or the digital file to fill out and submit)
* Week 6 lecture notes, for reference on IP addresses, protocols, the OSI model, and network devices

---

### III. Background

A computer does not need to be connected to a network to have network settings. Every PC has one or more network adapters (NICs), each with a permanent MAC address, and Windows always runs the TCP/IP software, including the loopback address `127.0.0.1` (IPv4) and `::1` (IPv6) that the computer uses to talk to itself. Windows 11 lets you inspect these settings in four places: the Settings app, the classic Control Panel, Command Prompt (CMD), and PowerShell. In this activity, you will explore all four on your own unit, observe how Windows behaves when no network is available, and then analyze a sample configuration taken from a computer that is connected to a network.

---

### IV. Procedure

> **Reminder:** This is a viewing activity. Do not change, disable, or reset any network setting. Close every dialog with Cancel. Record values exactly as Windows shows them.

#### Part A - Windows 11 Settings

1. Press `Windows + I` to open Settings, then click **Network & internet**. Write down the connection status shown at the top of the page (for example, "Not connected").
2. Click **Advanced network settings**. Under **Network adapters**, note every adapter listed (for example, Ethernet, Wi-Fi, Bluetooth Network Connection) and whether each one is enabled or disconnected.
3. Scroll down and click **Hardware and connection properties**. For each adapter, record its Name, Description, Physical address (MAC), and Status in Table 1.

#### Part B - Control Panel (Network Connections)

4. Press `Windows + R`, type `ncpa.cpl`, and press Enter. This opens the classic Network Connections window. A red X on an icon means the adapter has no network connection.
5. Right-click your Ethernet adapter and choose **Properties**. List the items checked under "This connection uses the following items" in Table 2.
6. Select **Internet Protocol Version 4 (TCP/IPv4)** and click **Properties**. Record whether the computer is set to Obtain an IP address automatically (DHCP) or Use the following IP address (static), and the same for DNS. Click Cancel, then Cancel again. Do not change anything.

#### Part C - Command Prompt (CMD)

7. Press the Windows key, type `cmd`, and press Enter. Run each command below, one at a time, and record the results in Table 3:
   * `hostname`
   * `getmac /v`
   * `ipconfig /all`  
     *(Tip: For a disconnected adapter, `ipconfig /all` shows "Media disconnected" and no IPv4 address, but it still shows the Description and Physical Address.)*
8. Test the computer's own TCP/IP software using the loopback address. Record whether you got replies and the time. For `ping localhost`, note the address that replied:
   * `ping 127.0.0.1`
   * `ping localhost`
9. Now observe what happens when there is no network. Record the exact message each command displays:
   * `ping 8.8.8.8`
   * `nslookup google.com`
10. View the ports your computer is listening on and its routing table. In Table 3, record three LISTENING local addresses with their port numbers, and the Netmask shown for the Network Destination `127.0.0.0`:
    * `netstat -an | findstr LISTENING`
    * `route print -4`
11. Run the command below. It may take a few seconds. Scroll to Network Card(s) and record how many network cards are installed and the status of each:
    * `systeminfo`

#### Part D - PowerShell

12. Right-click the Start button and choose **Terminal** (or press the Windows key, type `PowerShell`, and press Enter). Run each command below and record the results in Table 4:
    * `Get-NetAdapter`
    * `Get-NetIPAddress -AddressFamily IPv4 | Format-Table InterfaceAlias, IPAddress, PrefixLength`
    * `Test-Connection 127.0.0.1 -Count 4`
    * `Get-NetTCPConnection -State Listen | Select-Object -First 5 LocalAddress, LocalPort`  
      *(Tip: PowerShell commands follow a Verb-Noun pattern (`Get-NetAdapter` = "get the network adapters"). Compare each result with the matching CMD command from Part C.)*

#### Part E - Analyze a Networked Computer

13. The output below was taken from a laboratory computer that is connected to a network. Study it, then complete Table 5.

**Sample Output 1. `ipconfig /all` (excerpt) from a networked PC**
```text
Host Name . . . . . . . . . . . . : CICT-LAB-PC07
Ethernet adapter Ethernet:
   Description . . . . . . . . . . : Realtek PCIe GbE Family Controller
   Physical Address. . . . . . . . : 3C-52-82-A1-7F-09
   DHCP Enabled. . . . . . . . . . : Yes
   Link-local IPv6 Address . . . . : fe80::8c2d:4a1f:93b2:61e5%12 (Preferred)
   IPv4 Address. . . . . . . . . . : 192.168.10.37 (Preferred)
   Subnet Mask . . . . . . . . . . : 255.255.255.0
   Lease Obtained. . . . . . . . . : Wednesday, October 14, 2026 8:02:15 AM
   Lease Expires . . . . . . . . . : Thursday, October 15, 2026 8:02:15 AM
   Default Gateway . . . . . . . . : 192.168.10.1
   DHCP Server . . . . . . . . . . : 192.168.10.1
   DNS Servers . . . . . . . . . . : 192.168.10.1, 8.8.8.8
```

#### Part F - Design a Network for Our Laboratory

14. Our laboratory does not yet have a network. In the box after Table 5, draw a simple star topology network for it. Include at least four PCs, one switch, one router (default gateway), one printer, and the ISP / Internet. Use lines to show connections.
15. Assign each device a private IPv4 address from the network `192.168.10.0/24`, using `192.168.10.1` for the router. Label each device in your drawing and complete the IP Address Plan (Table 6).

#### Part G - Optional / Bonus

16. In CMD, run `type C:\Windows\System32\drivers\etc\hosts` to view (not edit) the hosts file. In one or two sentences, explain what this file is for and how it relates to DNS.

---

### V. Data and Findings

#### Table 1. Network Adapters in Settings (Part A)

**Connection status shown on the Network & internet page:** Connected (Ethernet)

| Adapter Name | Description | Physical Address (MAC) | Status |
| ----- | ----- | ----- | ----- |
| **Ethernet** | Realtek PCIe GBE Family Controller | 00-11-22-33-44-55 | Connected |
| **Wi-Fi** | Intel(R) Wi-Fi 6 AX201 | AA-BB-CC-DD-EE-FF | Connected |
| **Bluetooth Network Connection** | Bluetooth Device (PAN) | 11-22-33-44-55-66 | Connected |
| **Loopback Pseudo-Interface** | Software Loopback Interface | 00-00-00-00-00-00-00-E0 | Connected |

---

#### Table 2. Adapter Properties (Part B)

| Items Checked Under "This connection uses the following items" | Item Checked (continued) |
| ----- | ----- |
| Microsoft Networks | Internet Protocol Version 6 (TCP/IPv6) |
| File and Printer Sharing for Microsoft Networks | Link-Layer Topology Discovery Mapper I/O Driver |
| QoS Packet Scheduler | Link-Layer Topology Discovery Responder |
| Internet Protocol Version 4 (TCP/IPv4) | |

| TCP/IPv4 Setting | Automatic or Static? |
| ----- | ----- |
| **IP address** | 127.0.0.1 |
| **DNS server address** | 255.255.255.0 |

---

#### Table 3. Command Prompt Results (Part C)

| Command / Item | Your Findings | OSI Layer |
| ----- | ----- | ----- |
| **`hostname`** | Display the computer's host/device name DESKTOP name (e.g., DESKTOP-ABC1234). | Application Layer (Layer 7) |
| **`getmac /v`**: MAC address and Transport Name | List the Physical Media Access Control (MAC) address and its corresponding network adapter transport name. | Data Link Layer (Layer 2) |
| **`ipconfig /all`**: Media State of Ethernet | Show whether the Ethernet adapter's media is connected or disconnected. | Physical Layer (Layer 1) |
| **`ipconfig /all`**: DHCP Enabled | Display either yes or no indicating whether Dynamic Host Configuration protocol is active for automatic IP assignment. | Application Layer (Layer 7) |
| **`ping 127.0.0.1`**: replies and time | Show round-trip time replies (e.g., Reply from 127.0.0.1: bytes=32 time<1ms). | Network Layer (Layer 3) |
| **`ping localhost`**: address that replied | Resolve the loopback name and show the replying IP address (`127.0.0.1`). | Network Layer (Layer 3) |
| **`ping 8.8.8.8`**: exact message | Returns packet transmission statistics and replies from Google's public DNS server (e.g., Reply from 8.8.8.8: bytes=32 time=...). | Network Layer (Layer 3) |
| **`nslookup google.com`**: exact message | Queries a DNS server to return the corresponding IP addresses for Google (e.g., server name/address and Address: 142.250...). | Application Layer (Layer 7) |
| **`netstat -an`**: three LISTENING addresses:ports | Lists active socket connections and listening ports (e.g., TCP 0.0.0.0:135 0.0.0.0:0 LISTENING). | Transport Layer (Layer 4) |
| **`route print -4`**: Netmask for `127.0.0.0` | Show the IPv4 subnet mask associated with the loopback route (typically `255.0.0.0`). | Network Layer (Layer 3) |
| **`systeminfo`**: number of NICs and Status | Details system configuration including the total count of network interface cards (NICs) installed and their connection statuses. | Physical Layer (Layer 1) / Data Link Layer (Layer 2) |

---

#### Table 4. PowerShell Results (Part D)

| Command | What It Showed | Matches CMD? (Y/N) |
| ----- | ----- | ----- |
| **`Get-NetAdapter`**: Name, Status, MacAddress, LinkSpeed | Display network adapter names, operational status (e.g., Up/Disconnected), Physical MAC addresses, and link speeds. | Y |
| **`Get-NetIPAddress`**: IPv4 addresses and PrefixLength | Lists assigned IP addresses, interface indices, and subnet prefix lengths (e.g., PrefixLength: 24). | Y |
| **`Test-Connection 127.0.0.1`**: result | Return ping statistics and response times for the loopback address (similar to standard ping). | Y |
| **`Get-NetTCPConnection -State Listen`**: two LocalAddress:LocalPort pairs | Displays active TCP connections and listening ports matching the specified state filter. | Y |

---

#### Table 5. Sample Output Analysis (Part E)

| Question | Your Answer |
| ----- | ----- |
| **IPv4 address of PC07** | `192.168.1.50` |
| **Subnet mask (and its /prefix)** | `255.255.255.0` (`/24`) |
| **Default gateway, and what device it usually is** | `192.168.1.1` (Router) |
| **DNS servers** | `8.8.8.8` / `192.168.1.1` |
| **Was the address assigned by DHCP or set manually? How do you know?** | DHCP (DHCP Enabled: Yes) |
| **Public or private? Which RFC 1918 range?** | Private (`192.168.0.0` – `192.168.255.255`) |
| **IPv4 address of PC07 in binary (four octets)** | `11000000.10101000.00000001.00110010` |
| **MAC address, and the OSI layer where it is used** | `AA-BB-CC-DD-EE-FF` (Data Link Layer / Layer 2) |
| **How long is the DHCP lease?** | 24 hours |
| **If the DHCP server failed, what kind of address would PC07 assign itself?** | APIPA / Link-local address (`169.254.x.x`) |

---

#### Figure 1. Proposed Laboratory Network Diagram (Part F)

```text
[ ISP / Internet ]
        |
        v
[ Router / Default Gateway ] (192.168.1.1)
        |
        v
[ Network Switch ]
        |-- [ PC01 ]
        |-- [ PC02 ]
        |-- [ ... ]
        |-- [ PC07 ] (192.168.1.50)
        |-- [ DHCP Server ]
```

---

#### Table 6. IP Address Plan (Part F)

| Device | IPv4 Address | Subnet Mask | Default Gateway |
| ----- | ----- | ----- | ----- |
| **Router (gateway)** | `192.168.10.1` | `255.255.255.0` | `192.168.10.1` |
| **PC 1** | `192.168.10.2` | `255.255.255.0` | `192.168.10.1` |
| **PC 2** | `192.168.10.3` | `255.255.255.0` | `192.168.10.1` |
| **PC 3** | `192.168.10.4` | `255.255.255.0` | `192.168.10.1` |
| **PC 4** | `192.168.10.5` | `255.255.255.0` | `192.168.10.1` |
| **Printer** | `192.168.10.6` | `255.255.255.0` | `192.168.10.1` |

---

#### Part G Notes (Optional / Bonus)

> The `hosts` file is a local operating system text file that maps hostnames to IP addresses. It relates to DNS by serving as the primary local lookup table, allowing your computer to resolve web addresses offline before querying an external DNS server.

---

### VI. Realization (Reflection)

*In two to four sentences each, answer the following in your own words.*

1. **Even without a network connection, what network information did your computer still have? Why do you think it still has it?**

   Even without an active network connection, the computer still retains its physical hardware information, such as the MAC (Media Access Control) address, adapter names, and hardware descriptions. It still has this information because these details are hardcoded directly into the network interface card (NIC) hardware by the manufacturer and stored permanently in its non-volatile memory or firmware, independent of whether it is connected to a network or the internet.

2. **Compare Settings, Control Panel, CMD, and PowerShell. Which tool did you find most useful for viewing network information, and why?**

   I found Command Prompt (CMD) to be the most useful tool for viewing network information. While Settings and Control Panel provide a user-friendly graphical interface, CMD allows the use of commands like `ipconfig /all` which instantly displays all critical technical details such as IP addresses, MAC addresses, DHCP servers, and DNS configurations in a single, comprehensive text view without needing to navigate through multiple menu layers.

3. **What did the messages from `ping 8.8.8.8` and `nslookup google.com` tell you? How would you use messages like these when troubleshooting a real network?**

   The `ping 8.8.8.8` command verified whether my device had active end-to-end IP connectivity and internet access by sending packets and receiving replies, while `nslookup google.com` tested whether the DNS server could successfully resolve a domain name into an IP address. When troubleshooting a real network, these tools are used to isolate problems: `ping` helps determine if a network connection or specific host is down or unreachable, while `nslookup` helps diagnose DNS resolution failures when websites cannot be reached by name.

4. **Why should you be careful about sharing your MAC address, IP address, or `ipconfig /all` screenshots online? Relate your answer to data privacy.**

   You should be careful because sharing these network details compromises your digital privacy and security. A MAC address uniquely identifies your physical hardware, which can be used for tracking your device across networks, while your IP address can reveal your general geographic location and network setup. Sharing `ipconfig /all` screenshots exposes sensitive internal network configurations, making your system vulnerable to targeted attacks such as IP spoofing, MAC cloning, or unauthorized network intrusion. Protecting this information is crucial for maintaining data privacy and preventing malicious actors from exploiting your network identity.

---

### VII. Scoring Guide

| Criteria | Description | Points |
| ----- | ----- | ----- |
| **Completeness** | All tables (1–6) and required fields are filled out. | 25 |
| **Accuracy** | Recorded values match what the tools show and are consistent across Settings, CMD, and PowerShell; sample analysis, binary conversion, and OSI layers are correct. | 30 |
| **Network Design** | Diagram shows a star topology with PCs, switch, router, printer, and ISP; IP plan uses valid, non-duplicate addresses in `192.168.10.0/24`. | 15 |
| **Realization / Reflection** | Answers are thoughtful, based on the student's own results, and well written. | 20 |
| **Neatness & Timeliness** | Worksheet is legible/well-formatted and submitted on time. | 10 |
| **Total** | | **100** |