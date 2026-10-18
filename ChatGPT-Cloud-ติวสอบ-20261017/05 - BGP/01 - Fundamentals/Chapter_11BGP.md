# Chapter_11BGP

> ฉบับ Markdown แปลงจาก PDF ด้วย pdftotext (ข้อความล้วน ไม่ได้ตรวจทานด้วยมือ) — รูป ตาราง และไดอะแกรมให้เปิด PDF ตามลิงก์ของแต่ละหน้า

> ต้นฉบับ: [Chapter_11BGP.pdf](Chapter_11BGP.pdf)  
> จำนวน 55 หน้า — คงลำดับหน้าตามต้นฉบับ

## หน้า 1

Chapter 11: BGP
Instructor Materials

CCNP Enterprise: Core Networking

[ดูภาพต้นฉบับหน้า 1 ใน PDF](Chapter_11BGP.pdf#page=1)

---

## หน้า 2

Chapter 11 Content
This chapter covers the following content:
• BGP Fundamentals - This section provides an overview of the
fundamentals of the BGP routing protocol.
• Basic BGP Configuration - This section walks through the process
of configuring BGP to establish a neighbor session and how routes
are exchanged between peers.
• Route Summarization - This section provides an overview of how
route summarization works with BGP and some of the design
considerations with summarization.
• Multiprotocol BGP for IPv6 - This section explains how BGP
provides support for IPv6 routing and configuration.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

2

[ดูภาพต้นฉบับหน้า 2 ใน PDF](Chapter_11BGP.pdf#page=2)

---

## หน้า 3

BGP Fundamentals
•

Border Gateway Protocol (BGP) is an EGP standardized path vector routing protocol
that provides scalability, flexibility, and network stability. When BGP was created, the
primary design consideration was for IPv4 inter-organization connectivity on public
networks like the Internet and on private dedicated networks.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

3

[ดูภาพต้นฉบับหน้า 3 ใน PDF](Chapter_11BGP.pdf#page=3)

---

## หน้า 4

BGP Fundamentals

Autonomous System Numbers
From the perspective of BGP, an autonomous system (AS) is a collection of
routers under a single organization’s control, using one or more IGPs and
common metrics.
•

An organization requiring connectivity to the internet must obtain an autonomous
system number (ASN) from the Internet Assigned Numbers Authority (IANA).

•

RFC 4893 expanded the ASN field from 2 bytes to accommodate 4 bytes (32-bit
range). This allows for 4,294,967,295 unique ASNs, providing quite an increase from
the original 65,535 ASNs.

•

The IANA requires organizations or individuals requesting AS numbers to meet the
following conditions:
•Proof of a publicly allocated network range
•Proof that Internet connectivity is provided through multiple connections
•Demonstrated need for a unique routing policy from their providers.
© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

4

[ดูภาพต้นฉบับหน้า 4 ใน PDF](Chapter_11BGP.pdf#page=4)

---

## หน้า 5

BGP Fundamentals

Autonomous System Numbers (Cont.)
Similar to IP Addresses, the AS number assignments include private address
ranges that cannot be used for Internet traffic. These ranges are:
• ASNs 64,512–65,535 are private ASNs in the 16-bit ASN range.
• ASNs 4,200,000,000–4,294,967,294 are private ASNs within the extended

32-bit range.
• Use only the ASN assigned by IANA, the ASN assigned by your service

provider, or a private ASN. Using another organization’s ASN without
permission could result in traffic loss and cause havoc on the internet.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

5

[ดูภาพต้นฉบับหน้า 5 ใน PDF](Chapter_11BGP.pdf#page=5)

---

## หน้า 6

BGP Fundamentals

Path Attributes
BGP uses path attributes (PAs) associated with each network path. The
PAs provide BGP with granularity and control of routing policies within
BGP. The BGP prefix PAs are classified as follows:
• Well-known mandatory
• Well-known discretionary
• Optional transitive
• Optional non-transitive

Per RFC 4271, well-known attributes must be recognized by all BGP
implementations. Well-known mandatory attributes must be included
with every prefix advertisement; well-known discretionary attributes may
or may not be included with a prefix advertisement.
© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

6

[ดูภาพต้นฉบับหน้า 6 ใน PDF](Chapter_11BGP.pdf#page=6)

---

## หน้า 7

BGP Fundamentals

Loop Prevention
BGP is a path vector routing protocol and does not contain a complete
topology of the network, as link-state routing protocols do. BGP behaves
like distance vector protocols, ensuring that a path is loop free.
The Loop Prevention Mechanism:
• AS 100 advertises the 172.16.1.0/24
prefix to AS 200.
• AS 200 advertises the prefix to AS 400,
which then advertises the prefix to AS
300.
• AS 300 advertises the prefix back to AS
100 with an AS_Path of 300 400 200 100.
AS 100 sees itself in the AS_Path variable
and discards the prefix.
© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

7

[ดูภาพต้นฉบับหน้า 7 ใน PDF](Chapter_11BGP.pdf#page=7)

---

## หน้า 8

BGP Fundamentals

Address Families
•

RFC 2858 added Multi-Protocol BGP (MP-BGP) capability by adding an extension called the
address family identifier (AFI).

•

An address family correlates to a specific network protocol, such as IPv4 or IPv6, and additional
granularity is provided through a subsequent address-family identifier (SAFI) such as unicast or
multicast.

•

MBGP achieves this separation by using the BGP path attributes (PAs) MP_REACH_NLRI and
MP_UNREACH_NLRI to carry different reachability information for the different address families.

•

Every address family maintains a separate database and configuration for each protocol
(address family + sub-address family) in BGP.

•

Some network engineers refer to Multiprotocol BGP as MP-BGP, and other network engineers
use the term MBGP. Both terms refer to the same thing.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

8

[ดูภาพต้นฉบับหน้า 8 ใน PDF](Chapter_11BGP.pdf#page=8)

---

## หน้า 9

BGP Fundamentals

Inter-Router Communication
•
•
•
•
•

BGP does not use hello packets to discover neighbors, as do IGP protocols, and it
cannot discover neighbors dynamically. BGP neighbors are defined by IP address.
BGP uses TCP port 179 to communicate with other routers.
Most recent implementations of BGP set the do-not-fragment (DF) bit to prevent
fragmentation and rely on path MTU discovery.
BGP uses TCP, so unlike IGPs, it can form adjacencies with routers that are multiple
hops away.
A BGP session refers to the established adjacency between two BGP routers. Multihop sessions require that the router use an underlying route installed in the RIB
(static or from any routing protocol) to establish the TCP session with the remote
endpoint.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

9

[ดูภาพต้นฉบับหน้า 9 ใน PDF](Chapter_11BGP.pdf#page=9)

---

## หน้า 10

BGP Fundamentals

Inter-Router Communication (Cont.)
BGP can be thought of as a control plane routing protocol or as an application
because it allows for the exchange of routes with a peer that is multiple hops
away.
• A BGP session refers to the established
adjacency between two BGP routers.
• BGP neighbors connected to the same
network use the ARP table to locate the
IP address of the peer. Multi-hop BGP
sessions require routing table
information for finding the IP address of
the peer.
• A default route is not sufficient to
establish a multi-hop BGP session.
© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

10

[ดูภาพต้นฉบับหน้า 10 ใน PDF](Chapter_11BGP.pdf#page=10)

---

## หน้า 11

BGP Fundamentals

BGP Session Types
BGP sessions are categorized into two types:
Internal BGP (iBGP) - Sessions established with an iBGP router that are in the
same AS or that participate in the same BGP confederation. iBGP prefixes are
assigned an administrative distance (AD) of 200 upon installation in the router’s
RIB.
External BGP (eBGP) - Sessions established with a BGP router that are in a
different AS. eBGP prefixes are assigned an AD of 20 upon installation in the
router’s RIB.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

11

[ดูภาพต้นฉบับหน้า 11 ใน PDF](Chapter_11BGP.pdf#page=11)

---

## หน้า 12

BGP Fundamentals

BGP Session Types (Cont.)
iBGP
Service providers provide transit connectivity. Enterprises should not.
Preventing an AS from becoming a transit AS by redistributing BGP
routes into the IGP is not a viable solution for the following reasons:
•
•
•

Scalability - The internet has over 780,000 IPv4 network prefixes, IGPs
cannot scale to that level of routes.
Custom routing - IGPs use metrics as the primary method of route
selection. BGP uses multiple steps to identify the best path or to
manipulate the path for a specific network prefix.
Path attributes - All of the BGP path attributes cannot be maintained
within IGP protocols.

Establishing iBGP sessions between IGP routers in a full mesh
allows for proper forwarding between autonomous systems.
© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

12

[ดูภาพต้นฉบับหน้า 12 ใน PDF](Chapter_11BGP.pdf#page=12)

---

## หน้า 13

BGP Fundamentals

BGP Session Types (Cont.)
eBGP
eBGP is the core component of BGP on the internet. The difference in behavior
for eBGP sessions and iBGP sessions are:
■

■

■
■

iBGP allows for multi-hop sessions. eBGP packets set the TTL to
one, so packets are dropped if multi-hop connections are
attempted.
The advertising router modifies the BGP next-hop address to the
IP address sourcing the BGP connection.
The advertising router prepends its ASN to the existing AS_Path variable.
The receiving router verifies that the AS_Path variable does not
contain an ASN that matches the local routers. BGP discards
the NLRI if it fails the AS_Path loop prevention check.
© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

13

[ดูภาพต้นฉบับหน้า 13 ใน PDF](Chapter_11BGP.pdf#page=13)

---

## หน้า 14

BGP Fundamentals

BGP Messages
Table 11-2 BGP Packet Types
TYPE

NAME

FUNCTIONAL OVERVIEW

1

OPEN

Sets up and establishes BGP adjacency

2

UPDATE

Advertises, updates, or withdraws routes

3

NOTIFICATION Indicates an error condition to a BGP neighbor

4

KEEPALIVE

Ensures that BGP neighbors are still alive

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

14

[ดูภาพต้นฉบับหน้า 14 ใน PDF](Chapter_11BGP.pdf#page=14)

---

## หน้า 15

BGP Fundamentals

BGP Neighbor States
The BGP session may report the
following states:
• Idle
• Connect
• Active
• OpenSent
• OpenConfirm
• Established

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

15

[ดูภาพต้นฉบับหน้า 15 ใน PDF](Chapter_11BGP.pdf#page=15)

---

## หน้า 16

BGP Fundamentals

BGP Neighbor States (Cont.)
BGP forms a TCP session with neighbor routers called peers. BGP uses the finite-state
machine (FSM) to maintain a table of all BGP peers and their operational status.
•
•

•
•
•
•

Idle - The first stage of the BGP FSM. BGP detects a start event and attempts to
initiate a TCP session with the BGP peer.
Connect - BGP initiates the TCP connection. When the TCP handshake is completed,
the ConnectRetryTimer is reset, an Open message is sent to the neighbor, and the state
changes to OpenSent. During this stage, the router with the higher IP address manages
the connection.
Active - BGP starts another TCP three-way handshake. If the connection is established
an Open message is sent and the state moves to OpenSent.
OpenSent - If the OPEN message that is received by the originating router contains no
errors, the connection state moves to OpenConfirm
OpenConfirm - In the OpenConfirm state, BGP waits for KEEPALIVE or
NOTIFICATION messages. Upon receipt of a neighbor’s KEEPALIVE message, the
state is moved to Established.
Established - BGP neighbors exchange routes using UPDATE messages.
© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

16

[ดูภาพต้นฉบับหน้า 16 ใน PDF](Chapter_11BGP.pdf#page=16)

---

## หน้า 17

Basic BGP Configuration
When configuring BGP, it is best to think of the configuration from a modular perspective.
BGP router configuration requires the following components:
• BGP session parameters
• Address family initialization
• Activate the address family on the BGP peer

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

17

[ดูภาพต้นฉบับหน้า 17 ใน PDF](Chapter_11BGP.pdf#page=17)

---

## หน้า 18

Basic BGP Configuration

BGP Router Configuration Components
•

BGP session parameters - BGP session parameters provide settings that involve
estab- lishing communication to the remote BGP neighbor. Session settings include
the ASN of the BGP peer, authentication, and keepalive timers.

•

Address family initialization - The address family is initialized under the BGP
router configuration mode. Network advertisement and summarization occur within
the address family.

•

Activate the address family on the BGP peer - In order for a session to initiate,
one address family for a neighbor must be activated. The router’s IP address is
added to the neighbor table, and BGP attempts to establish a BGP session or
accepts a BGP session initiated from the peer router.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

18

[ดูภาพต้นฉบับหน้า 18 ใน PDF](Chapter_11BGP.pdf#page=18)

---

## หน้า 19

Basic BGP Configuration

Modular Configuration
Steps to Configure Basic BGP are as follows:
Step 1. Initialize the BGP routing process with the global command router bgp as-number.
Step 2. (Optional) Statically define the BGP router ID (RID). The dynamic RID allocation
logic uses the highest IP address of any of the up loopback interfaces.
Step 3. Identify the BGP neighbor’s IP address and autonomous system number with the
BGP router configuration command neighbor ip-address remote-as as-number.
Step 4. Initialize the address family with the BGP router configuration command addressfamily afi safi.
Step 5. Activate the address family for the BGP neighbor with the BGP address family
configuration command neighbor ip-address activate.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

19

[ดูภาพต้นฉบับหน้า 19 ใน PDF](Chapter_11BGP.pdf#page=19)

---

## หน้า 20

Basic BGP Configuration

Configuring Basic BGP on IOS
R1 (Default IPv4 Address-Family Enabled)
router bgp 65100
neighbor 10.12.1.2 remote-as 65200
R2 (Default IPv4 Address-Family Disabled)
router bgp 65200
no bgp default ipv4-unicast
neighbor 10.12.1.1 remote-as 65100
!
address-family ipv4
neighbor 10.12.1.1 activate
exit address-family

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

20

[ดูภาพต้นฉบับหน้า 20 ใน PDF](Chapter_11BGP.pdf#page=20)

---

## หน้า 21

Basic BGP Configuration

Verification of BGP Sessions
• The BGP session is verified with the command show bgp afi safi summary.
• Earlier commands, such as show ip bgp summary, came out before MBGP and
do not provide a structure for the current multiprotocol capabilities within BGP.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

21

[ดูภาพต้นฉบับหน้า 21 ใน PDF](Chapter_11BGP.pdf#page=21)

---

## หน้า 22

Basic BGP Configuration

Verification of BGP Sessions (Cont.)
Field

Description

Neighbor

IP address of the BGP peer

V

BGP version spoken by the BGP peer

AS

Autonomous system number of the BGP peer

MsgRcvd

Count of messages received from the BGP peer

MsgSent

Count of messages sent to the BGP peer

TblVer

Last version of the BGP database sent to the peer

InQ

Number of messages queued to be processed by the peer

OutQ

Number of messages queued to be sent to the peer

Up/Down

Length of time the BGP session is established or the current status if the session
is not in an established state

State/PfxRcd

Current state of the BGP peer or the number of prefixes received from the peer

Table 11-3 BGP Summary Fields

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

22

[ดูภาพต้นฉบับหน้า 22 ใน PDF](Chapter_11BGP.pdf#page=22)

---

## หน้า 23

Basic BGP Configuration

Prefix Advertisement
• BGP network statements do not enable BGP for a specific interface;

instead, they identify specific network prefixes to be installed into the BGP
table, known as the Loc-RIB table.
• As the BGP prefix is installed into the Loc-RIB table, the following BGP

PAs are set, depending on the RIB prefix type:
•

Connected network - The next-hop BGP attribute is set to 0.0.0.0, the BGP
origin attribute is set to i (IGP), and the BGP weight is set to 32,768.

•

Static route or routing protocol - The next-hop BGP attribute is set to the
next-hop IP address in the RIB, the BGP origin attribute is set to i (IGP), the
BGP weight is set to 32,768, and the MED is set to the IGP metric.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

23

[ดูภาพต้นฉบับหน้า 23 ใน PDF](Chapter_11BGP.pdf#page=23)

---

## หน้า 24

Basic BGP Configuration

Prefix Advertisement (Cont.)
All routes in the Loc-RIB table use the following process for advertisement to
BGP peers:
Step 1. Pass a validity check. Verify that the NRLI is valid and that the next-hop address is
resolvable in the global RIB. If the NRLI fails, the NLRI remains but does not process further.
Step 2. Process outbound neighbor route policies. After processing, if a route was not denied by
the outbound policies, the route is maintained in the Adj-RIB-Out table for later reference.
Step 3. Advertise the NLRI to BGP peers. If the NLRI’s next-hop BGP PA is 0.0.0.0, then the nexthop address is changed to the IP address of the BGP session.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

24

[ดูภาพต้นฉบับหน้า 24 ใน PDF](Chapter_11BGP.pdf#page=24)

---

## หน้า 25

Basic BGP Configuration

Prefix Advertisement (Cont.)
The network statement resides under the appropriate address family within the BGP
router configuration. The command network network mask subnet-mask [routemap route-map-name] is used for advertising IPv4 networks. The optional routemap provides a method of setting specific BGP PAs when the prefix installs into the
Loc-RIB table.
router bgp 65200
bgp log-neighbor-changes
no bgp default ipv4-unicast
neighbor 10.12.1.1 remote-as 65100
!
address-family ipv4
network 10.12.1.0 mask 255.255.255.0
network 192.168.2.2 mask 255.255.255.255
neighbor 10.12.1.1 activate
exit-address-family
© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

25

[ดูภาพต้นฉบับหน้า 25 ใน PDF](Chapter_11BGP.pdf#page=25)

---

## หน้า 26

Basic BGP Configuration

Receiving and Viewing Routes
BGP uses three tables for maintaining the network prefix and PAs for a route:
•
•
•

Adj-RIB-In - Contains the NLRIs in original form
Loc-RIB - Contains all the NLRIs that originated locally or were received from other BGP
peers.
Adj-RIB-Out - Contains the NLRIs after outbound route policies have been processed.

Processing Steps are
shown in Figure 11-9.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

26

[ดูภาพต้นฉบับหน้า 26 ใน PDF](Chapter_11BGP.pdf#page=26)

---

## หน้า 27

Basic BGP Configuration

Receiving and Viewing Routes (Cont.)
The command show bgp afi safi displays the contents of the BGP database
(Loc-RIB) on the router.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

27

[ดูภาพต้นฉบับหน้า 27 ใน PDF](Chapter_11BGP.pdf#page=27)

---

## หน้า 28

Basic BGP Configuration

Receiving and Viewing Routes (Cont.)
Field

Description

Network

A list of the network prefixes installed in BGP. Valid NLRIs are indicated by the *.
The NLRI selected as the best path is indicated by an angle bracket (>).

Next Hop

A well-known mandatory BGP path attribute that defines the IP address for the next
hop for that specific NLRI.

Metric

Multiple-exit discriminator (MED): An optional non-transitive BGP path attribute
used in BGP for the specific NLRI.

LocPrf

Local Preference: A well-known discretionary BGP path attribute used in the BGP
best-path algorithm for the specific NLRI.

Weight

A locally significant Cisco-defined attribute used in the BGP best-path algorithm for
the specific NLRI.

Path and Origin

AS_Path: A well-known mandatory BGP path attribute used for loop prevention
and in the BGP best-path algorithm for the specific NLRI.
Origin: A well-known mandatory BGP path attribute used in the BGP best-path
algorithm. A value of i represents an IGP, e indicates EGP, and ? indicates a route
that was redistributed into BGP.
Table 11-4 BGP Table Fields
© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

28

[ดูภาพต้นฉบับหน้า 28 ใน PDF](Chapter_11BGP.pdf#page=28)

---

## หน้า 29

Basic BGP Configuration

Receiving and Viewing Routes (Cont.)
The command show bgp afi safi network displays all the paths for a specific
route and the BGP path attributes for that route.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

29

[ดูภาพต้นฉบับหน้า 29 ใน PDF](Chapter_11BGP.pdf#page=29)

---

## หน้า 30

Basic BGP Configuration

Receiving and Viewing Routes (Cont.)
The Adj-RIB-Out table is a unique table maintained for each BGP peer. It enables a network engineer to
view routes advertised to a specific router. The command show bgp afi safi neighbor ip-address
advertised routes displays the contents of the Adj-RIB-Out table for a neighbor.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

30

[ดูภาพต้นฉบับหน้า 30 ใน PDF](Chapter_11BGP.pdf#page=30)

---

## หน้า 31

Basic BGP Configuration

BGP Route Advertisements from Indirect Sources
BGP should be thought of as a routing application as the BGP session and route
advertisement are two separate components. BGP can install multiple routes
learned from static routes, EIGRP, and OSPF.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

31

[ดูภาพต้นฉบับหน้า 31 ใน PDF](Chapter_11BGP.pdf#page=31)

---

## หน้า 32

Basic BGP Configuration

BGP Route Advertisements from Indirect Sources (Cont.)
Redistributing routes learned from an IGP into BGP is completely safe. Redistributing routes
learned from BGP into an IGP should be done with extreme caution.
Example 11-12 Configuring Advertising Routes for Non-Connected Routes

R1
router bgp 65100
bgp log-neighbor-changes
network 10.12.1.0 mask 255.255.255.0
network 192.168.1.1 mask 255.255.255.255
network 192.168.3.3 mask 255.255.255.255
network 192.168.4.4 mask 255.255.255.255
redistribute ospf 1
neighbor 10.12.1.2 remote-as 65200
© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

32

[ดูภาพต้นฉบับหน้า 32 ใน PDF](Chapter_11BGP.pdf#page=32)

---

## หน้า 33

Route Summarization
Summarizing prefixes conserves router resources and accelerates best-path calculation
by reducing the size of the table. Summarization also provides the benefit of stability by
hiding route flaps from downstream routers, thereby reducing routing churn.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

33

[ดูภาพต้นฉบับหน้า 33 ใน PDF](Chapter_11BGP.pdf#page=33)

---

## หน้า 34

Route Summarization

Summarizing Prefixes
There are two techniques for BGP summarization:
•

Static - Create a static route to Null0 for the summary network prefix and then
advertise the prefix with a network statement. The downfall of this technique is that
the summary route is always advertised, even if the networks are not available.

•

Dynamic - Configure an aggregation network prefix. When viable component routes
that match the aggregate network prefix enter the BGP table, then the aggregate
prefix is created. The originating router sets the next hop to Null0 as a discard route
for the aggregated prefix for loop prevention.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

34

[ดูภาพต้นฉบับหน้า 34 ใน PDF](Chapter_11BGP.pdf#page=34)

---

## หน้า 35

Route Summarization

Aggregate Address
Dynamic route summarization is accomplished with the BGP address family
configuration command aggregate-address network subnet-mask [summaryonly] [as-set].

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

35

[ดูภาพต้นฉบับหน้า 35 ใน PDF](Chapter_11BGP.pdf#page=35)

---

## หน้า 36

Route Summarization

Aggregating Address (Cont.)
R1

R2

router bgp 65100
bgp log-neighbor-changes
network 10.12.1.0 mask 255.255.255.0
network 192.168.1.1 mask 255.255.255.255
network 192.168.3.3 mask 255.255.255.255
network 192.168.4.4 mask 255.255.255.255
redistribute ospf 1
neighbor 10.12.1.2 remote-as 65200

router bgp 65100
bgp log-neighbor-changes
neighbor 10.12.1.1 remote-as 65100
neighbor 10.23.1.3 remote-as 65300
!
address-family ipv4
aggregate-address 192.168.0.0 255.255.0.0
aggregate-address 172.16.0.0 255.255.240.0
redistribute connected
neighbor 10.12.1.1 activate
neighbor 10.23.1.3 activate
exit-address-family

Example 11-15 Configuring BGP Route Aggregation

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

36

[ดูภาพต้นฉบับหน้า 36 ใน PDF](Chapter_11BGP.pdf#page=36)

---

## หน้า 37

Route Summarization

Atomic Aggregate
Aggregated routes act like new BGP routes with a shorter prefix length. When a BGP router
summarizes a route, it does not advertise the AS_Path information from before the aggregation.
BGP path attributes like AS_Path, MED, and BGP communities are not included in the new BGP
advertisement.
R2
router bgp 65200
bgp log-neighbor-changes
no bgp default ipv4-unicast
neighbor 10.12.1.1 remote-as 65100
neighbor 10.23.1.3 remote-as 65300
!
address-family ipv4
aggregate-address 192.168.0.0 255.255.0.0 summary-only
aggregate-address 172.16.0.0 255.255.240.0 summary-only
redistribute connected
neighbor 10.12.1.1 activate
neighbor 10.23.1.3 activate
exit-address-family

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

37

[ดูภาพต้นฉบับหน้า 37 ใน PDF](Chapter_11BGP.pdf#page=37)

---

## หน้า 38

Route Summarization

Atomic Aggregate (Cont.)
R2#show bgp ipv4 unicast 172.16.0.0
BGP routing table entry for 172.16.0.0/20,
version 6
Paths: (1 available, best #1, table default)
Not advertised to any peer
Refresh Epoch 2
65200, (aggregated by 65200 192.168.2.2)
10.23.1.2 from 10.23.1.2 (192.168.2.2)
Origin IGP, metric 0,localpref 100, valid
32768, valid, external, atomic-aggregate, best
rx pathid: 0, tx pathid: 0x0

Example 11-23 Examining the BGP Attribute for the Atomic Aggregate Attribute
© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

38

[ดูภาพต้นฉบับหน้า 38 ใน PDF](Chapter_11BGP.pdf#page=38)

---

## หน้า 39

Route Summarization

Route Aggregation with AS_SET
To keep the BGP path information history, the optional as-set keyword may be used with the
aggregate-address command. As the router generates the aggregate route, BGP attributes from the
component aggregate routes are copied over to it.
R2#show running-config | section router bgp
router bgp 65200
bgp log-neighbor-changes
no bgp default ipv4-unicast
neighbor 10.12.1.1 remote-as 65100
neighbor 10.23.1.3 remote-as 65300
!
address-family ipv4
aggregate-address 192.168.0.0 255.255.0.0 as-set summary-only
aggregate-address 172.16.0.0 255.255.240.0 as-set summary-only
redistribute connected
neighbor 10.12.1.1 activate
neighbor 10.23.1.3 activate
exit-address-family

Example 11-24 Configuring Aggregation While Preserving BGP Attributes
© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

39

[ดูภาพต้นฉบับหน้า 39 ใน PDF](Chapter_11BGP.pdf#page=39)

---

## หน้า 40

Multiprotocol BGP for IPv6
Multiprotocol BGP (MP-BGP) enables BGP to carry NLRI for multiple protocols,
such as IPv4, IPv6, and Multiprotocol Label Switching (MPLS) Layer 3 virtual
private networks (L3VPNs).

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

40

[ดูภาพต้นฉบับหน้า 40 ใน PDF](Chapter_11BGP.pdf#page=40)

---

## หน้า 41

Multiprotocol BGP for IPv6

MP-BGP

RFC 4760 defines the following new features:
•

A new address family identifier (AFI) model

•

New BGPv4 optional and nontransitive attributes:
•

Multiprotocol reachable NLRI

•

Multiprotocol unreachable NLRI

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

41

[ดูภาพต้นฉบับหน้า 41 ใน PDF](Chapter_11BGP.pdf#page=41)

---

## หน้า 42

Multiprotocol BGP for IPv6

MP-BGP (Cont.)

• All the same underlying IPv4 path vector routing protocol features and rules also

apply to MP-BGP for IPv6.
• MP-BGP for IPv6 continues to use the same well-known TCP port 179 for session

peering as BGP uses for IPv4.
• The MP-BGP extensions include an address family identifier (AFI) that describes the

supported protocols, along with subsequent address family identifier (SAFI) attribute
fields that describe whether the prefix applies to the unicast or multicast routing table:
• IPv4 unicast: AFI: 1, SAFI: 1
• IPv6 unicast: AFI: 2, SAFI: 1

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

42

[ดูภาพต้นฉบับหน้า 42 ใน PDF](Chapter_11BGP.pdf#page=42)

---

## หน้า 43

Multiprotocol BGP for IPv6

Configuring IPv6 BGP

All the BGP configuration rules demonstrated earlier apply with IPv6, except that
the IPv6 address family must be initialized, and the neighbor is activated.
R1
router bgp 65100
bgp router-id 192.168.1.1
bgp log-neighbor-changes
no bgp default ipv4-unicast
neighbor 2001:DB8:0:12::2 remote-as 65200
!
address-family ipv6
redistribute connected
neighbor 2001:DB8:0:12::2 activate
exit-address-family

R2
router bgp 65200
bgp router-id 192.168.2.2
bgp log-neighbor-changes
no bgp default ipv4-unicast
neighbor 2001:DB8:0:12::1 remote-as 65100
neighbor 2001:DB8:0:23::3 remote-as 65300
!
address-family ipv6
network 2001:DB8::2/128
network 2001:DB8:0:12::/64
network 2001:db8:0:23::/64
neighbor 2001:DB8:0:12::1 activate
neighbor 2001:DB8:0:23::3 activate
exit-address-family

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

43

[ดูภาพต้นฉบับหน้า 43 ใน PDF](Chapter_11BGP.pdf#page=43)

---

## หน้า 44

Multiprotocol BGP for IPv6

Viewing BGP IPv6 Neighbors
•
•

Routers exchange AFI capabilities during the initial BGP session negotiation.
The command show bgp ipv6 unicast neighbors ip-address [detail] displays detailed
information on whether or not the IPv6 capabilities were negotiated successfully.
R1# show bgp ipv6 unicast neighbors 2001:DB8:0:12::2
! Output omitted for brevity
BGP neighbor is 2001:DB8:0:12::2, remote AS 65200, external link
BGP version 4, remote router ID 192.168.2.2
BGP state = Established, up for 00:28:25
Last read 00:00:54, last write 00:00:34, hold time is 180, keepalive interval is
60 seconds
Neighbor sessions:
1 active, is not multisession capable (disabled)
Neighbor capabilities:
Route refresh: advertised and received(new)
Four-octets ASN Capability: advertised and received
Address family IPv6 Unicast: advertised and received
Enhanced Refresh Capability: advertised and received

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

44

[ดูภาพต้นฉบับหน้า 44 ใน PDF](Chapter_11BGP.pdf#page=44)

---

## หน้า 45

Multiprotocol BGP for IPv6

Verifying IPv6 BGP
R2# show bgp ipv6 unicast summary
BGP router identifier 192.168.2.2, local AS number 65200
BGP table version is 19, main routing table version 19
7 network entries using 1176 bytes of memory
8 path entries using 832 bytes of memory
3/3 BGP path/bestpath attribute entries using 456 bytes of memory
2 BGP AS-PATH entries using 48 bytes of memory
0 BGP route-map cache entries using 0 bytes of memory
0 BGP filter-list cache entries using 0 bytes of memory
BGP using 2512 total bytes of memory
BGP activity 7/0 prefixes, 8/0 paths, scan interval 60 secs
Neighbor
V AS
MsgRcvd MsgSent TblVer InQ OutQ Up/Down State/PfxRcd
2001:DB8:0:12::1 4 65100
35
37
19
0
0 00:25:08
3
2001:DB8:0:23::3 4 65300
32
37
19
0
0 00:25:11
3

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

45

[ดูภาพต้นฉบับหน้า 45 ใน PDF](Chapter_11BGP.pdf#page=45)

---

## หน้า 46

Multiprotocol BGP for IPv6

Viewing the IPv6 BGP Tables
The unspecified address (::) indicates that the local router is generating the prefix for the BGP table.
R2# show bgp ipv6 unicast | begin Network
Network
Next Hop
Metric LocPrf Weight Path
*> 2001:DB8::1/128
2001:DB8:0:12::1
0
0 65100 ?
*> 2001:DB8::2/128
::
0
32768 i
*> 2001:DB8::3/128
2001:DB8:0:23::3
0
0 65300 i
*> 2001:DB8:0:1::/64
2001:DB8:0:12::1
0
0 65100 ?
*> 2001:DB8:0:3::/64
2001:DB8:0:23::3
0
0 65300 i
*> 2001:DB8:0:12::/64
::
0
32768 i
*
2001:DB8:0:12::1
0
0 65100 ?
*> 2001:DB8:0:23::/64
::
0
32768 i
2001:DB8:0:23::3
0
0 65300 i

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

46

[ดูภาพต้นฉบับหน้า 46 ใน PDF](Chapter_11BGP.pdf#page=46)

---

## หน้า 47

Multiprotocol BGP for IPv6

IPv6 Route Summarization
The same process for summarizing or aggregating IPv4 routes occurs with IPv6
routes, and the format is identical except that the configuration is placed under the
IPv6 address family using the command aggregate-address prefix/prefix-length
[summary-only] [as-set].
Bits Needed

Summary Address

Component Networks

2

2001:db8:0:0::/62

2001:db8:0:0::/64 through 2001:db8:0:3::/64

3

2001:db8:0:0::/61

2001:db8:0:0::/64 through 2001:db8:0:7::/64

4

2001:db8:0:0::/60

2001:db8:0:0::/64 through 2001:db8:0:F::/64

5

2001:db8:0:0::/59

2001:db8:0:0::/64 through 2001:db8:0:1F::/64

6

2001:db8:0:0::/58

2001:db8:0:0::/64 through 2001:db8:0:3F::/64

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

47

[ดูภาพต้นฉบับหน้า 47 ใน PDF](Chapter_11BGP.pdf#page=47)

---

## หน้า 48

Prepare for the Exam

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

48

[ดูภาพต้นฉบับหน้า 48 ใน PDF](Chapter_11BGP.pdf#page=48)

---

## หน้า 49

Prepare for the Exam

Key Topics for Chapter 11
Description
Autonomous system numbers
Path Attributes
BGP attribute AS_Path
Address family databases and configuration
Inter-router communication
BGP Single- and Multi-Hop Sessions
BGP session types
eBGP

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

49

[ดูภาพต้นฉบับหน้า 49 ใน PDF](Chapter_11BGP.pdf#page=49)

---

## หน้า 50

Prepare for the Exam

Key Topics for Chapter 11 (Cont.)
Description
Basic BGP configuration
Verification of BGP Sessions
Prefix advertisement
BGP Database Processing
BGP Table Fields
BGP summarization techniques
Aggregate address
Aggregate address with summary-only

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

50

[ดูภาพต้นฉบับหน้า 50 ใน PDF](Chapter_11BGP.pdf#page=50)

---

## หน้า 51

Prepare for the Exam

Key Topics for Chapter 11 (Cont.)
Description
Atomic aggregate
Route aggregation with AS_SET
Multiprotocol BGP for IPv6
IPv6 configuration
IPv6 summarization

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

51

[ดูภาพต้นฉบับหน้า 51 ใน PDF](Chapter_11BGP.pdf#page=51)

---

## หน้า 52

Prepare for the Exam

Key Terms for Chapter 11
Key Terms
Address Family

Loc-RIB table

AS_Path

Optional non-transitive

Atomic aggregate

Optional transitive

Autonomous System (AS)

Path vector routing protocol

eBGP session

Well-known discretionary

iBGP session

Well-known mandatory

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

52

[ดูภาพต้นฉบับหน้า 52 ใน PDF](Chapter_11BGP.pdf#page=52)

---

## หน้า 53

Prepare for the Exam

Command Reference for Chapter 11
Task

Command Syntax

Initialize the BGP router process

router bgp as-number

Identify a BGP peer to establish a session with

neighbor ip-address remote-as as-number

Disable the automatic IPv4 address family configuration
mode

no bgp default ip4-unicast

Initialize a specific address family and sub-address
family

address-family afi safi

Activate a BGP neighbor for a specific address family

neighbor ip-address activate

Advertise a network to BGP

network network mask subnet-mask
[route-map route-map-name]

Configure a BGP aggregate IPv4 prefix

aggregate-address network subnet-mask
[summary-only] [as-set]

Configure a BGP aggregate IPv6 prefix

aggregate-address prefix/prefix-length
[summary-only] [as-set]
© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

53

[ดูภาพต้นฉบับหน้า 53 ใน PDF](Chapter_11BGP.pdf#page=53)

---

## หน้า 54

Prepare for the Exam

Command Reference for Chapter 11 (Cont.)
Task

Command Syntax

Display the contents of the BGP database

show bgp afi safi [network] [detailed]

Display a summary of the BGP table and
neighbor peering sessions

show bgp afi safi summary

Display the negotiated BGP settings with a
specific peer and the number of prefixes
exchanged with that peer

show bgp afi safi neighbors ip-address

Display the Adj-RIB-Out BGP table for a specific
BGP neighbor

Show bgp afi safi neighbor ip-address
advertised routes

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

54

[ดูภาพต้นฉบับหน้า 54 ใน PDF](Chapter_11BGP.pdf#page=54)

---

## หน้า 55

_(หน้านี้ไม่มีข้อความที่ดึงได้ — ดูภาพใน PDF)_

[ดูภาพต้นฉบับหน้า 55 ใน PDF](Chapter_11BGP.pdf#page=55)

---
