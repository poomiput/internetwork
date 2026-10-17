# Chapter_21WirelessTshooting

> ฉบับส่งต่อ: ใช้ข้อความจาก Markdown เดิม ลิงก์ภาพอ้างเลขหน้า PDF ในโฟลเดอร์เดียวกัน ให้ดู PDF เมื่อต้องอ่านรูป ตาราง และหน้าจอ WLC

> ต้นฉบับ: [Chapter_21WirelessTshooting.pdf](Chapter_21WirelessTshooting.pdf)  
> จำนวน 30 หน้า — คงลำดับหน้าและภาพต้นฉบับทุกหน้า

> ข้อความที่ระบุ OCR ถอดจากภาพ; ส่วนที่อ่านไม่ชัดจะระบุไว้เพื่อเทียบกับต้นฉบับ

## หน้า 1

Chapter 21: Troubleshooting Wireless Connectivity 

Instructor Materials 

CCNP Enterprise: Core Networking

CISCO

[ดูภาพต้นฉบับหน้า 1 ใน PDF](Chapter_21WirelessTshooting.pdf#page=1)

---

## หน้า 2

#### Chapter 21 Content 

##### **This chapter covers the following content:** 

- **Troubleshooting Client Connectivity from the WLC -** This section discusses how to use a wireless LAN controller as a troubleshooting tool to diagnose problems with wireless clients. 

- **Troubleshooting Connectivity Problems at the AP -** This section discusses how to diagnose problems between a wireless LAN controller and an AP that might affect wireless client connectivity. 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

2

[ดูภาพต้นฉบับหน้า 2 ใน PDF](Chapter_21WirelessTshooting.pdf#page=2)

---

## หน้า 3

### Troubleshooting Client Connectivity from WLC 

- Most of your time managing and monitoring a wireless network will be spent in the wireless LAN controller GUI. 

- You can access a wealth of troubleshooting information from the controller, if you know the client’s MAC address. 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 3

[ดูภาพต้นฉบับหน้า 3 ใน PDF](Chapter_21WirelessTshooting.pdf#page=3)

---

## หน้า 4

### Troubleshooting Client Connectivity from WLC 

When one or more network users report that they are having problems, your first course of action should be to gather more information, ask questions, and try to notice patterns or similarities in the answers you receive. 

- Information from the user such as, “I cannot connect” or “The Wi-Fi is down” might mean that the user’s device cannot associate, cannot get an IP address, or cannot authenticate. 

- If you get reports from many people in the same area, perhaps an AP is misconfigured or malfunctioning. 

- Reports from many areas or from a single service set identifier (SSID) may indicate problems with a controller configuration. 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

4

[ดูภาพต้นฉบับหน้า 4 ใน PDF](Chapter_21WirelessTshooting.pdf#page=4)

---

## หน้า 5

#### Troubleshooting Client Connectivity from WLC Conditions for a Successful Wireless Association 

If you receive a report of only one wireless user having problems, it might not make sense to spend time troubleshooting a controller, where many users are supported. Instead, you should focus on that one user’s client device and its interaction with an AP. 

Figure 21-1 illustrates the following conditions that must be met for a successful association: 

- The client is within RF range of an AP and asks to associate. 

- The client authenticates. 

- The client requests and receives an IP address. 



**Figure 21-1** _Conditions for a Successful Wireless Association_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

5

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
Client → BSS → AP → Network
802.1X authentication: Client ↔ AAA server
Controller: WLC
IP Address: Client ↔ DHCP server
```

[ดูภาพต้นฉบับหน้า 5 ใน PDF](Chapter_21WirelessTshooting.pdf#page=5)

---

## หน้า 6

#### Troubleshooting Client Connectivity from WLC Cisco WLC GUI 



Cisco WLCs have two main GUI presentations, one for monitoring and one for more advanced configuration and monitoring. 

When you open a browser to the WLC management address, you see the default screen that is shown in Figure 21-2. 

The default screen displays network summary dashboard information on the right portion and monitoring tools in the list on the left. 

**Figure 21-2** _The Initial Default WLC Display_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

6

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
Cisco 8540 Wireless Controller
Monitoring: Network Summary (Access Points, Clients); Rogues (Access Points, Clients); Interferers; Wireless Dashboard (AP Performance, Client Performance); Best Practices
Advanced
Search: AP or Client Search
NETWORK SUMMARY
Wireless Networks: 5; Access Points: 1918
Active Clients: 2.4GHz 3714; 5GHz 5074
Rogues: APs 1683; Clients 33
Interferers: 2.4GHz 30181; 5GHz 40
ACCESS POINTS — BY USAGE
mrisc-245-ap11, mrisc-235-ap5, mrisc-236-ap7, mrisc-269-ap9, mrisc-246-ap10, mrisc-237-ap8, mrisc-312-ap3, pav-a-a0b0023-ap17, mrisc-310-ap1, mrisc-316-ap2
OPERATING SYSTEMS — Name | Clients
Workstation | 1845
Apple-iPhone | 1374
Intel-Device | 1035
Android | 538
Android-Samsung-Galaxy-Phone | 425
Zebra-Device | 404
Apple-iPad | 215
Z-Com-Device | 161
Microsoft-Workstation | 137
Apple-Device | 111
Lower panel headings: APPLICATIONS — BY USAGE; CLIENTS
```

[ดูภาพต้นฉบับหน้า 6 ใน PDF](Chapter_21WirelessTshooting.pdf#page=6)

---

## หน้า 7

#### Troubleshooting Client Connectivity from WLC Searching for a Client in the WLC GUI 

If you know a specific wireless client’s MAC address, you can enter it into the search bar at the top right of the screen. 

For example, in Figure 21-3, 78:4b:87:7b:af:96 is the target of the search. Because that MAC address is known to the controller, a match is shown with a client icon below the search bar. 



**Figure 21-3** _Searching for a Client in the WLC GUI_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

7

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
Cisco 8540 Wireless Controller
Monitoring: Network Summary (Access Points, Clients); Rogues (Access Points, Clients); Interferers; Wireless Dashboard (AP Performance, Client Performance); Best Practices
Advanced
Search and matching client: 78:4b:87:7b:af:96
NETWORK SUMMARY
Wireless Networks: 5; Access Points: 1917
Active Clients: 2.4GHz 2485; 5GHz 3871
Rogues: APs 1674; Clients 16
Interferers: 2.4GHz 28491; 5GHz 51
OPERATING SYSTEMS — Name | Clients
Workstation | 1089
Apple-iPhone | 864
Intel-Device | 851
Android | 376
Zebra-Device | 347
Android-Samsung-Galaxy-Phone | 273
Apple-iPad | 167
Z-Com-Device | 158
Microsoft-Workstation | 80
Apple-Device | 73
APPLICATIONS — BY USAGE
ssl, youtube, facebook, outlook-web-service, google-services, bbo, https, hp-pdl-datastr, itunes, icloud
Lower panel headings: CLIENTS; TOP WLANS
```

[ดูภาพต้นฉบับหน้า 7 ใน PDF](Chapter_21WirelessTshooting.pdf#page=7)

---

## หน้า 8

#### Troubleshooting Client Connectivity from WLC Client Search Results 

The resulting details about the client are displayed in the Client View screen, shown in Figure 21-4. From this output, you can see many details about the client device listed in the left portion of the screen, and you can see connectivity and application information displayed on the right. 



**Figure 21-4** _Client Search Results_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

8

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
CLIENT VIEW — GENERAL
User Name: Unknown
Host Name: android-6bbe8eaa76cc5fe5
MAC Address: 78:4b:87:7b:af:96
Uptime: Associated since 6 Minutes 13 Seconds
SSID: clinical
AP Name: a01600-ap12 (Ch 6)
Nearest APs: a00700b-ap102 (-80 dBm), a01107-ap37 (-89 dBm), a01002-ap8 (-91 dBm)
Device Type: Android-Samsung-Galaxy-Phone-S5-G900V
Performance: Signal Strength -54 dBm; Signal Quality 38 dB; Connection Speed 130 Mbps; Channel Width 20 MHz
Capabilities: 802.11n (2.4GHz), Spatial Stream 2
Cisco Compatible: Supported (CCX v 4)
Connection Score: 90%
CONNECTIVITY: Start → Association → Authentication → DHCP → Online (all green)
TOP APPLICATIONS — Name | Usage | % Usage
https | 1.9 MB | 50.17%
ssl | 1.3 MB | 35.66%
amazon-web-services | 289.9 KB | 7.55%
google-services | 81.6 KB | 2.13%
outlook-web-service | 47.3 KB | 1.23%
google-play | 39.2 KB | 1.02%
facebook | 35.3 KB | 0.92%
skype | 27.5 KB | 0.72%
youtube | 13.5 KB | 0.35%
http | 9.8 KB | 0.26%
```

[ดูภาพต้นฉบับหน้า 8 ใน PDF](Chapter_21WirelessTshooting.pdf#page=8)

---

## หน้า 9

#### Troubleshooting Client Connectivity from WLC Checking the Client’s Connection Status 

Before a controller will permit a client to fully associate with a basic service set (BSS), the client must progress through a sequence of states. Each state refers to a policy that the client must meet before moving on to the next state: 

1. **Start** — Client activity has just begun. 

2. **Association** — The client has requested 802.11 authentication and association with an AP. 

3. **Authentication** — The client must pass a Layer 2 Pre-Shared Key (PSK) or 802.1x authentication policy. 

4. **DHCP** — The WLC is waiting to learn the client’s IP address from a Dynamic Host Configuration Protocol (DHCP) server. 

5. **Online** — The client has passed Layer 2 and Layer 3 policies, successfully associated, and can pass traffic. 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

9

[ดูภาพต้นฉบับหน้า 9 ใน PDF](Chapter_21WirelessTshooting.pdf#page=9)

---

## หน้า 10

#### Troubleshooting Client Connectivity from WLC Checking the Client’s Association and Signal Status 

Information such as the wireless client’s username (if known), hostname, wireless MAC address, wireless connection uptime, and the SSID used can be viewed in the left portion of the Client View screen. 

In Figure 21-4, the username is not known because the client does not authenticate itself with a username. 



**Figure 21-4** _Client Search Results_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

10

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
CLIENT VIEW — GENERAL
User Name: Unknown
Host Name: android-6bbe8eaa76cc5fe5
MAC Address: 78:4b:87:7b:af:96
Uptime: Associated since 6 Minutes 13 Seconds
SSID: clinical
AP Name: a01600-ap12 (Ch 6)
Nearest APs: a00700b-ap102 (-80 dBm), a01107-ap37 (-89 dBm), a01002-ap8 (-91 dBm)
Device Type: Android-Samsung-Galaxy-Phone-S5-G900V
Performance: Signal Strength -54 dBm; Signal Quality 38 dB; Connection Speed 130 Mbps; Channel Width 20 MHz
Capabilities: 802.11n (2.4GHz), Spatial Stream 2
Cisco Compatible: Supported (CCX v 4)
Connection Score: 90%
CONNECTIVITY: Start → Association → Authentication → DHCP → Online (all green)
TOP APPLICATIONS — Name | Usage | % Usage
https | 1.9 MB | 50.17%
ssl | 1.3 MB | 35.66%
amazon-web-services | 289.9 KB | 7.55%
google-services | 81.6 KB | 2.13%
outlook-web-service | 47.3 KB | 1.23%
google-play | 39.2 KB | 1.02%
facebook | 35.3 KB | 0.92%
skype | 27.5 KB | 0.72%
youtube | 13.5 KB | 0.35%
http | 9.8 KB | 0.26%
```

[ดูภาพต้นฉบับหน้า 10 ใน PDF](Chapter_21WirelessTshooting.pdf#page=10)

---

## หน้า 11

#### Troubleshooting Client Connectivity from WLC WLC Information About a Poorly Performing Client 

In Figure 21-5 the AP is receiving the client’s signal strength at −76 dBm and the SNR at 18 dB (both rather low values), causing the current data rate to fall to 29 Mbps. A quick look at the Connection Score value reveals a low 20%. 

It is safe to assume that the client has moved too far away from the AP where it is associated, causing the signal strength to become too low to support faster performance. 



**Figure 21-5** _WLC Information About a Poorly Performing Client_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

11

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
CLIENT VIEW — GENERAL
User Name: Unknown
Host Name: android-6bbe8eaa76cc5fe5
MAC Address: 78:4b:87:7b:af:96
Uptime: Associated since 12 Seconds
SSID: clinical
AP Name: a00056-ap3 (Ch 6)
Nearest APs: a01105-ap30 (-76 dBm), ghi-022-ap10 (-91 dBm), ghi-200a-ap14 (-85 dBm)
Device Type: Android-Samsung-Galaxy-Phone-S5-G900V
Performance: Signal Strength -75 dBm; Signal Quality 18 dB; Connection Speed 29 Mbps; Channel Width 20 MHz
Capabilities: 802.11n (2.4GHz), Spatial Stream 1
Cisco Compatible: Supported (CCX v 5)
Connection Score: 20%
CONNECTIVITY: Start → Association → Authentication → DHCP → Online (all green)
TOP APPLICATIONS — Name | Usage | % Usage
https | 1.9 MB | 50.17%
ssl | 1.3 MB | 35.66%
amazon-web-services | 289.9 KB | 7.55%
google-services | 81.6 KB | 2.13%
outlook-web-service | 47.3 KB | 1.23%
google-play | 39.2 KB | 1.02%
facebook | 35.3 KB | 0.92%
skype | 27.5 KB | 0.72%
youtube | 13.5 KB | 0.35%
http | 9.8 KB | 0.26%
```

> หมายเหตุจากการตรวจ: ข้อความบรรยายต้นฉบับระบุ −76 dBm แต่ช่อง Signal Strength ในภาพระบุ −75 dBm จึงเก็บทั้งสองค่าตามตำแหน่งเดิม

[ดูภาพต้นฉบับหน้า 11 ใน PDF](Chapter_21WirelessTshooting.pdf#page=11)

---

## หน้า 12

#### Troubleshooting Client Connectivity from WLC WLC Information About a Poorly Performing Client 

Clicking on the Connection Score value displays further details in a popup window, as shown in Figure 21-6. 

The 20% value is the result of the client’s current data rate (29 Mbps) divided by the lower of the AP or client maximum data rate (144 Mbps). 

The Client Actual Rate and Connection Score values are indicators of current performance, and the other graphs show what is possible on the AP and the client. 



**Figure 21-6** _Displaying Detailed Client Performance Information_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

12

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
Connection Score: 20%
Connection Rates: AP Max Configured 217 Mbps; Client Max Capability 144 Mbps; Client Actual Rate 29 Mbps
Spatial Streams: AP Max Configured 3; Client Max Capability 2
Channel Width: AP Max Configured 20 MHz; Client Max Capability 20 MHz
Close
```

[ดูภาพต้นฉบับหน้า 12 ใน PDF](Chapter_21WirelessTshooting.pdf#page=12)

---

## หน้า 13

#### Troubleshooting Client Connectivity from WLC Checking the Client’s Mobility State 

- The WLC Client Search information includes a handy end-to-end graphical representation of a client’s wireless connection. 

- When you scroll down below the General and Connectivity sections, you see a topology diagram like the one shown in Figure 21-7. 

- The WLC’s name, management IP address, and model are displayed. Following the connection toward the right, you can see the AP name, IP address, and model where the client is associated. Moving further to the right, you can see that the client is associated to the AP. The client device is displayed with identifying information such as the device name, device type, VLAN number, and IP address. 



**Figure 21-7** _Displaying the Client Mobility State_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

13

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
MOBILITY STATE
WLC (LOCAL): 28c-8540; 172.22.25.9; AIR-CT8540-K9
→ Wired (CAPWAP)
→ AP (Local): a01600-ap12; 172.22.28.211; AIR-CAP3702I-A-K9
→ Wireless (802.11n (2.4GHz))
→ Client (VLAN3653): android-6bbe8eaa76cc5fe5; 10.21.94.104; Android-Samsung-Galaxy-Phone-S5-G900V
```

[ดูภาพต้นฉบับหน้า 13 ใน PDF](Chapter_21WirelessTshooting.pdf#page=13)

---

## หน้า 14

#### Troubleshooting Client Connectivity from WLC Checking the Client’s Wireless Policies 

By scrolling further down in the Client Search information, you can verify information about network, QoS, security, and other policies that affect the client, as shown in Figure 21-8. 

You can quickly learn the client’s IP address, VLAN number, QoS policy level used by the WLAN, security policy (WPA2), encryption cipher (CCMP AES), and authentication type (PSK with no EAP). 



**Figure 21-8** _Displaying the Wireless Policies Used by a Client_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

14

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
NETWORK & QOS — Description | Status
IP Address | 10.21.94.104
IPv6 Address | Unknown
VLAN | 3653
Source Group Tag | N/A
Fastlane Client | No
Mobility Role | No
WMM | Supported
U-APSD | Disabled
QoS Level | Silver
SECURITY & POLICY — Description | Status
Policy | RSN (WPA2)
Cipher | CCMP (AES)
Key Management | PSK
EAP Type | N/A
ACL (IP/IPv6) | None/None
mDNS Profile | default-mdns-profile
AAA Role | None
```

[ดูภาพต้นฉบับหน้า 14 ใน PDF](Chapter_21WirelessTshooting.pdf#page=14)

---

## หน้า 15

#### Troubleshooting Client Connectivity from WLC Testing a Wireless Client 

When you search for a specific client, the information displayed is of a static nature because it is obtained as a snapshot at the time of the search. The client search will need to be refreshed to get up-to-date data. You can also obtain dynamic data by testing a client in real time. 

By scrolling to the bottom of the client search information, you can see the Client Test section, which offers links to four client testing tools: 



**Figure 21-9** _Testing Ping Response Times Between the WLC and Client_ 

- **Ping Test** : The WLC sends five ICMP echo packets to the client’s IP address and measures the response time, as shown in Figure 21-9. 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

15

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
CLIENT TEST
Tabs: PING TEST (selected), CONNECTION, EVENT LOG, PACKET CAPTURE
Start
Graph vertical axis: 4000ms, 2000ms, 0ms; five plotted responses
Client reachable: 5/5 attempts succeeded.
```

> หมายเหตุจากการตรวจ: กราฟไม่มีตัวเลขกำกับแต่ละจุด จึงไม่ประมาณค่าตอบกลับจากตำแหน่งจุด

[ดูภาพต้นฉบับหน้า 15 ใน PDF](Chapter_21WirelessTshooting.pdf#page=15)

---

## หน้า 16

#### Troubleshooting Client Connectivity from WLC Testing a Wireless Client (Cont.) 

**Connection:** The WLC debugs the client for up to three minutes and checks each policy step as the client attempts to join the wireless network. 



**Figure 21-10** _Performing a Connection Test on a Successful Wireless Client_ 

Figure 21-10 shows a client that has successfully joined, and Figure 21-11 shows a client that failed Layer 2 authentication with a pre-shared key because its key did not match the key configured on the WLC. 



**Figure 21-11** _Performing a Connection Test on a Failed Wireless Client_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

16

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
CLIENT TEST
Tabs: PING TEST, CONNECTION (selected), EVENT LOG, PACKET CAPTURE
Start; Stop
Figure 21-10 — Successful client (green):
802.11 Association: Completed
Security Policy L2 PSK: Completed
Network Membership: Completed
IP Addressing: Completed
IP Additional Options: Completed
Figure 21-11 — Failed client:
802.11 Association: Completed (green)
Security Policy L2 PSK (red)
4-Way HandShake : M2 State Key Check Failed. Check credentials
Policy Type : PSK
4-Way HandShake : M2 State Key Check Failed. Check credentials
```

[ดูภาพต้นฉบับหน้า 16 ใน PDF](Chapter_21WirelessTshooting.pdf#page=16)

---

## หน้า 17

#### Troubleshooting Client Connectivity from WLC Testing a Wireless Client (Cont.) 

**Event Log:** The WLC collects and displays a log of events as the client attempts to join the wireless network, as shown in Figure 21-12. This information is very complex and detailed and is usually more suited for Cisco TAC engineers. 



**Figure 21-12** _Collecting an Event Log of a Client Join Attempt_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

17

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
CLIENT TEST
Tabs: PING TEST, CONNECTION, EVENT LOG (selected), PACKET CAPTURE
Start; Stop
Time Stamp | Module | Severity | Message Type | Message Subtype | Details
Fri Jun 28 2019 1... | Dot11 | INFO | ASSOC_REQ | MESSAGE_RECEI... | None
Fri Jun 28 2019 1... | PEM | INFO | PEM_EVENT_MSG | ADDING_WGB_C... | None
Fri Jun 28 2019 1... | PEM | INFO | PEM_EVENT_MSG | CALL_TERMINATED | from Local to Handoff Peer ...
Fri Jun 28 2019 1... | PEM | ERROR | PEM_EVENT_MSG | WEB_AUTH_USE... | None
Fri Jun 28 2019 1... | PEM | INFO | PEM_EVENT_MSG | CALL_TERMINATED | from Handoff to Unassociate...
Fri Jun 28 2019 1... | Dot11 | INFO | ASSOC_REQ | INVALID_RSN_IE | None
Fri Jun 28 2019 1... | PEM | INFO | PEM_EVENT_MSG | WLAN_SUPPORT... | None
Fri Jun 28 2019 1... | PEM | INFO | PEM_EVENT_MSG | IP_ACQUIRED_A... | None
Fri Jun 28 2019 1... | Dot11 | INFO | ASSOC_REQ | CLIENT_MOVED_... | None
Fri Jun 28 2019 1... | CIAAA | INFO | AAA_AUTH | AAA_MESSAGE_... | Accounting-Response receiv...
Fri Jun 28 2019 1... | Dot1x | ERROR | AUTH_DOT1X | WLAN_REQUIRE... | None
Fri Jun 28 2019 1... | Dot1x | ERROR | EAPOL_KEY | ERROR_INITIALIZ... | None
Fri Jun 28 2019 1... | Dot1x | ERROR | EAPOL_KEY | UNABLE_TO_ALL... | None
Fri Jun 28 2019 1... | Misce | ERROR | MISC_ROAM_EVE... |  | 00:00:00:00:00:00, 4,88:f0:3...
Fri Jun 28 2019 1... | Dot1x | ERROR | EAPOL_KEY | ERROR_INITIALIZ... | None
```

> หมายเหตุจากการตรวจ: ข้อความที่ลงท้าย ... ถูกตัดอยู่ใน GUI ต้นฉบับ จึงไม่เติมส่วนที่มองไม่เห็น

[ดูภาพต้นฉบับหน้า 17 ใน PDF](Chapter_21WirelessTshooting.pdf#page=17)

---

## หน้า 18

#### Troubleshooting Client Connectivity from WLC Testing a Wireless Client (Cont.) 

**Packet Capture:** The WLC enables a wireless packet capture at the AP where the client attempts to join, as shown in Figure 21-13. 

The captured data is saved to a specified FTP server, where it can be downloaded and analyzed using a packet analysis tool like Wireshark or LiveAction Omnipeek. 



**Figure 21-13** _Performing a Packet Capture of a Wireless Client_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

18

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
CLIENT TEST
Tabs: PING TEST, CONNECTION, EVENT LOG, PACKET CAPTURE (selected)
Capture Point: AP Name a01600-ap12; Time(min) 10
Capture Filters: Select All (unchecked)
Wireless Filters (all unchecked): Control, IAPP, Data, Management, Dot1x
IP Protocol Filters (all unchecked): ARP, IP, Broadcast, TCP, Multicast, UDP
FTP Details: IP Address 0.0.0.0; FTP Path blank; Username blank; Password masked (****)
Capture States: Client Status red; Start
```

[ดูภาพต้นฉบับหน้า 18 ใน PDF](Chapter_21WirelessTshooting.pdf#page=18)

---

## หน้า 19

### Troubleshooting Connectivity at the AP 

- In cases where you get reports from multiple users who are all having problems in the same general area, you might need to focus your efforts on an AP. 

- The problem could be as simple as a defective radio, where no clients are receiving a signal. In that case, you might have to go onsite to confirm that the transmitter is not working correctly. 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 19

[ดูภาพต้นฉบับหน้า 19 ใน PDF](Chapter_21WirelessTshooting.pdf#page=19)

---

## หน้า 20

### Troubleshooting Connectivity Problems at the AP 

The split-MAC architecture creates several different points where you can troubleshoot. Successfully operating the lightweight AP and providing a working BSS require the following: 

- The AP must have connectivity to its access layer switch. 

- The AP must have connectivity to its WLC, unless it is operating in FlexConnect mode. 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

20

[ดูภาพต้นฉบับหน้า 20 ใน PDF](Chapter_21WirelessTshooting.pdf#page=20)

---

## หน้า 21

#### Troubleshooting Connectivity Problems at the AP Displaying Information About an AP 

First, verify the connectivity between an AP and a controller. 

The easiest approach is to simply look for the AP in the list of live APs that have joined the controller. If you know which controller the AP should join, open a management session to it. Enter the AP’s name in the search bar. 

If the search reveals a live AP that is joined to the controller, information is displayed in the Access Point View screen, as shown in Figure 21-14. 



**Figure 21-14** _Displaying Information About an AP_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

21

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
Cisco 8540 Wireless Controller; Search T2412-ap44; Advanced
ACCESS POINT VIEW — GENERAL
AP Name: T2412-ap44
Location: default location
MAC Address: 70:db:98:ff:65:40
IP Address: 172.16.169.43
CDP / LLDP: 2033-burg-2419-c1, GigabitEthernet8/0/7
Ethernet Speed: 1000 Mbps
Model / Domain: AIR-CAP3702E-B-K9 / 802.11bg:-A, 802.11a:-B
Power status: PoE/Full Power
Serial Number: FJC2115M1EU
Groups: AP Group Pavilion; Flex Group default-flex-group
Mode / Sub-mode: Local / Not Configured
Max Capabilities: 802.11n 2.4GHz, 802.11ac 5GHz; Spatial Streams 3 (2.4GHz), 3 (5.0GHz); Max. Data Rate 217 Mbps (2.4GHz), 1300 Mbps (5.0GHz)
Fabric: Disabled
PERFORMANCE SUMMARY — Parameter | 2.4GHz | 5GHz
Number of clients | 0 | 0
Channels | 11 | 161
Configured Rate | Min: 12 Mbps, Max: 217 Mbps | Min: 12 Mbps, Max: 289 Mbps
Usage Traffic | 56.3 GB | 7.9 GB
Throughput | 87.7 KB | 76.0 B
Transmit Power | 2 dBm | 5 dBm
Noise | -94 | -80
Channel Utilization | 27% | 0%
Interference | 27% | 0%
Traffic | 0% | 0%
Air Quality | 97 | 59
Admin Status | Enabled | Enabled
Clean Air Status | Up | Up
```

[ดูภาพต้นฉบับหน้า 21 ใน PDF](Chapter_21WirelessTshooting.pdf#page=21)

---

## หน้า 22

#### Troubleshooting Connectivity Problems at the AP Displaying Information About an AP (Cont.) 

In Figure 21-14 the AP is named T2412-ap4, has an IP address and a valid CDP entry that shows the switch name and port number where it is connected. The AP has a live Ethernet connection with a switch and has working Power over Ethernet (PoE). 

In the right portion of the Access Point View screen, you can verify parameters related to the AP’s wireless performance and RF conditions. 



**Figure 21-14** _Displaying Information About an AP_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

22

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
Cisco 8540 Wireless Controller; Search T2412-ap44; Advanced
ACCESS POINT VIEW — GENERAL
AP Name: T2412-ap44
Location: default location
MAC Address: 70:db:98:ff:65:40
IP Address: 172.16.169.43
CDP / LLDP: 2033-burg-2419-c1, GigabitEthernet8/0/7
Ethernet Speed: 1000 Mbps
Model / Domain: AIR-CAP3702E-B-K9 / 802.11bg:-A, 802.11a:-B
Power status: PoE/Full Power
Serial Number: FJC2115M1EU
Groups: AP Group Pavilion; Flex Group default-flex-group
Mode / Sub-mode: Local / Not Configured
Max Capabilities: 802.11n 2.4GHz, 802.11ac 5GHz; Spatial Streams 3 (2.4GHz), 3 (5.0GHz); Max. Data Rate 217 Mbps (2.4GHz), 1300 Mbps (5.0GHz)
Fabric: Disabled
PERFORMANCE SUMMARY — Parameter | 2.4GHz | 5GHz
Number of clients | 0 | 0
Channels | 11 | 161
Configured Rate | Min: 12 Mbps, Max: 217 Mbps | Min: 12 Mbps, Max: 289 Mbps
Usage Traffic | 56.3 GB | 7.9 GB
Throughput | 87.7 KB | 76.0 B
Transmit Power | 2 dBm | 5 dBm
Noise | -94 | -80
Channel Utilization | 27% | 0%
Interference | 27% | 0%
Traffic | 0% | 0%
Air Quality | 97 | 59
Admin Status | Enabled | Enabled
Clean Air Status | Up | Up
```

> หมายเหตุจากการตรวจ: ชื่อ AP ในข้อความบรรยายหน้า 22 เป็น T2412-ap4 แต่ในภาพเป็น T2412-ap44

[ดูภาพต้นฉบับหน้า 22 ใน PDF](Chapter_21WirelessTshooting.pdf#page=22)

---

## หน้า 23

#### Troubleshooting Connectivity Problems at the AP Performance Summary Information 

Another important indicator is the noise level on a channel. Ideally, the noise level should be as low as possible, usually around −90 or −100 dBm, so that 802.11 signals can be received intelligibly and accurately. 

Figure 21-15 lists the 5 GHz channel 161 as having a high noise level of −80 dBm— something that is not normal or ideal. 



**Figure 21-15** _Performance Summary Information_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

23

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
PERFORMANCE SUMMARY — Parameter | 2.4GHz | 5GHz
Number of clients | 0 | 0
Channels | 11 | 161
Configured Rate | Min: 12 Mbps, Max: 217 Mbps | Min: 12 Mbps, Max: 289 Mbps
Usage Traffic | 56.3 GB | 7.9 GB
Throughput | 87.7 KB | 76.0 B
Transmit Power | 2 dBm | 5 dBm
Noise | -94 | -80
Channel Utilization | 27% | 0%
Interference | 27% | 0%
Traffic | 0% | 0%
Air Quality | 97 | 59
Admin Status | Enabled | Enabled
Clean Air Status | Up | Up
```

[ดูภาพต้นฉบับหน้า 23 ใน PDF](Chapter_21WirelessTshooting.pdf#page=23)

---

## หน้า 24

#### Troubleshooting Connectivity Problems at the AP Performance Summary Information (Cont.) 

The channel information also shows an index of air quality. This is a measure of how competing and interfering devices affect the airtime quality or performance on a channel, presented as a number from 0 (worst) to 100 (best). 

The AP shows the air quality of channel 11 as 97, which is very good. However, channel 161 is 59, which is of concern. 

You can scroll further down in the Access Point View screen to see detailed information about the AP including a list of clients it is supporting, RF troubleshooting information, clean air assessments, and a tool to reboot the AP. 



**Figure 21-15** _Performance Summary Information_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 24

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
PERFORMANCE SUMMARY — Parameter | 2.4GHz | 5GHz
Number of clients | 0 | 0
Channels | 11 | 161
Configured Rate | Min: 12 Mbps, Max: 217 Mbps | Min: 12 Mbps, Max: 289 Mbps
Usage Traffic | 56.3 GB | 7.9 GB
Throughput | 87.7 KB | 76.0 B
Transmit Power | 2 dBm | 5 dBm
Noise | -94 | -80
Channel Utilization | 27% | 0%
Interference | 27% | 0%
Traffic | 0% | 0%
Air Quality | 97 | 59
Admin Status | Enabled | Enabled
Clean Air Status | Up | Up
```

[ดูภาพต้นฉบับหน้า 24 ใน PDF](Chapter_21WirelessTshooting.pdf#page=24)

---

## หน้า 25

#### Troubleshooting Connectivity Problems at the AP Displaying Information About RF Interferers 

In Figure 21-16, the RF Troubleshoot tab has been selected to display interferer data for the channels in the 5 GHz band. 

There are no interfering neighbor or rogue APs, but there is a clean air interferer in channel 161 - the channel that the AP is using. 



**Figure 21-16** _Displaying Information About RF Interferers_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

25

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
T2412-AP44 DETAILS
Tabs: CLIENTS, RF TROUBLESHOOT (selected), CLEAN AIR, TOOLS
Bands: 2.4GHz; 5GHz (selected)
NEIGHBOR AND ROGUE APS: NO NEIGHBORS OR ROGUES
CLEAN AIR INTERFERERS
Horizontal axis Channel: 137, 141, 145, 149, 153, 157, 161, 165, 169, 173, 177
Vertical axis Severity: 0–45 (step 5)
Legends: AP Channels; interferer
Highlighted AP channel and interferer: 161
```

[ดูภาพต้นฉบับหน้า 25 ใน PDF](Chapter_21WirelessTshooting.pdf#page=25)

---

## หน้า 26

#### Troubleshooting Connectivity Problems at the AP Displaying Information About Clean Air 

Select the Clean Air tab to see more details about the interfering devices that have been detected. 

In Figure 21-17, the Active Interferers table lists one continuous transmitter device with a severity level of 45, a duty cycle of 100%, and an RSSI value of −78 dBm. 

The severity level indicates how badly the interferer is affecting the channel. The duty cycle represents the percentage of time the device is actually transmitting. 



**Figure 21-17** _Displaying Information_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

26

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
T2412-AP44 DETAILS
Tabs: CLIENTS, RF TROUBLESHOOT, CLEAN AIR (selected), TOOLS
Bands: 2.4GHz; 5GHz (selected)
ACTIVE INTERFERERS — Inte... | Affect... | Detected Time | Sev... | Dut... | RS... | Dev... | Clu...
Continu... | 161 | Mon Jul 1 10:17:46 2019 | 45 | 100 | -78 | 0xd692 | 39:c9:9...
Pagination: 10 items per page; 1 - 1 of 1 items
NON WI-FI CHANNEL UTILIZATION: vertical % Utilization 0–100, step 10; horizontal Channel Number 161
INTERFERENCE POWER: vertical RSSI (dBm) 0 to -100, step -10; horizontal Channel Number 161
Both chart legends: Continuous Transmitter, Unclassified, WiFi AOCI
```

> หมายเหตุจากการตรวจ: เก็บหัวคอลัมน์/ค่าที่ GUI ตัดด้วย ... ตามต้นฉบับ กราฟไม่มีตัวเลขบนแท่ง จึงไม่ประมาณค่าจากความสูง

[ดูภาพต้นฉบับหน้า 26 ใน PDF](Chapter_21WirelessTshooting.pdf#page=26)

---

## หน้า 27

#### Troubleshooting Connectivity Problems at the AP Displaying Information About Clean Air (Cont.) 

The two bar graphs represent the percentage of time the device is using the channel and the received signal strength level of the device. If users are complaining about problems when they are around this AP, you should focus your efforts on tracking down the continuously transmitting device. 

The best outcome is if the device can be disabled or moved to an unused channel. If not, you will likely have to reconfigure the AP to use a different channel to move away from the interference. 



**Figure 21-17** _Displaying Information_ 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 

27

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
T2412-AP44 DETAILS
Tabs: CLIENTS, RF TROUBLESHOOT, CLEAN AIR (selected), TOOLS
Bands: 2.4GHz; 5GHz (selected)
ACTIVE INTERFERERS — Inte... | Affect... | Detected Time | Sev... | Dut... | RS... | Dev... | Clu...
Continu... | 161 | Mon Jul 1 10:17:46 2019 | 45 | 100 | -78 | 0xd692 | 39:c9:9...
Pagination: 10 items per page; 1 - 1 of 1 items
NON WI-FI CHANNEL UTILIZATION: vertical % Utilization 0–100, step 10; horizontal Channel Number 161
INTERFERENCE POWER: vertical RSSI (dBm) 0 to -100, step -10; horizontal Channel Number 161
Both chart legends: Continuous Transmitter, Unclassified, WiFi AOCI
```

> หมายเหตุจากการตรวจ: เก็บหัวคอลัมน์/ค่าที่ GUI ตัดด้วย ... ตามต้นฉบับ กราฟไม่มีตัวเลขบนแท่ง จึงไม่ประมาณค่าจากความสูง

[ดูภาพต้นฉบับหน้า 27 ใน PDF](Chapter_21WirelessTshooting.pdf#page=27)

---

## หน้า 28

### Prepare for the Exam 

© 2016  Cisco and/or its affiliates. All rights reserved.   Cisco Confidential 28

[ดูภาพต้นฉบับหน้า 28 ใน PDF](Chapter_21WirelessTshooting.pdf#page=28)

---

## หน้า 29

#### Prepare for the Exam Key Topics for Chapter 21 

| Description |
| --- |
| Conditions for Successful Wireless Association |
| WLC Client States |
| WLC Information About a Poorly Performing Client |
| Tools to Test Client Operation |
| Displaying Information About an AP |
| Interpreting Air Quality Values |


[ดูภาพต้นฉบับหน้า 29 ใน PDF](Chapter_21WirelessTshooting.pdf#page=29)

---

## หน้า 30

CISCO

[ดูภาพต้นฉบับหน้า 30 ใน PDF](Chapter_21WirelessTshooting.pdf#page=30)

---
