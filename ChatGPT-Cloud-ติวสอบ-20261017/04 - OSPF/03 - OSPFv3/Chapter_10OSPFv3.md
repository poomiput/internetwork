# Chapter_10OSPFv3

> ฉบับ Markdown แปลงจาก PDF ด้วย pdftotext (ข้อความล้วน ไม่ได้ตรวจทานด้วยมือ) — รูป ตาราง และไดอะแกรมให้เปิด PDF ตามลิงก์ของแต่ละหน้า

> ต้นฉบับ: [Chapter_10OSPFv3.pdf](Chapter_10OSPFv3.pdf)  
> จำนวน 30 หน้า — คงลำดับหน้าตามต้นฉบับ

## หน้า 1

Chapter 10: OSPFv3
Instructor Materials

CCNP Enterprise: Core Networking

[ดูภาพต้นฉบับหน้า 1 ใน PDF](Chapter_10OSPFv3.pdf#page=1)

---

## หน้า 2

Chapter 10 Content
This chapter covers the following content:
OSPFv3 Fundamentals: This section provides an overview of the OSPFv3
routing protocol and the similarities to OSPFv2.
OSPFv3 Configurations: This section demonstrates the configuration and
verification of an OSPFv3 environment.
IPv4 Support in OSPFv3: This section explains and demonstrates how
OSPFv3 can be used for exchanging IPv4 routes.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

2

[ดูภาพต้นฉบับหน้า 2 ใน PDF](Chapter_10OSPFv3.pdf#page=2)

---

## หน้า 3

OSPFv3 Fundamentals
• OSPFv3 supports IPv4 and IPv6 address families.
• New LSA types have been created to carry IPv6 prefixes.
• The IP prefix information is carried as LSA payload information, making the
protocol essentially address family independent.
• Includes a new link-state type field that is used to determine the flooding
scope of LSA, as well as the handling of unknown LSA types.
• OSPFv3 runs directly over IPv6, and the number of fields in the packet
header has been reduced.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

3

[ดูภาพต้นฉบับหน้า 3 ใน PDF](Chapter_10OSPFv3.pdf#page=3)

---

## หน้า 4

OSPFv3 Fundamentals

Features

• Router ID - The router ID is used to identify neighbors, regardless of the
network type in OSPFv3. The router ID must always be manually assigned
in the routing process.
• Authentication - Neighbor authentication has been removed from the
OSPF protocol and is now performed through IPsec extension headers in
the IPv6 packet.
• Neighbor adjacencies - OSPFv3 inter-router communication is handled by
IPv6 link-local addressing.
• Multiple subnets on an interface - Allows for neighbor adjacency to form
even if the two routers do not share a common subnet.
• Multiple instances - OSPFv3 packets include an instance ID field that may
be used to manipulate which routers on a network segment are allowed to
form adjacencies.
© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

4

[ดูภาพต้นฉบับหน้า 4 ใน PDF](Chapter_10OSPFv3.pdf#page=4)

---

## หน้า 5

OSPFv3 Fundamentals

OSPFv3 Link-State Advertisement
•
•
•
•
•
•

OSPFv3 packets use protocol ID 89.
Routers communicate with each other using the link-local address.
OSPFv3 modifies the structure of the router LSA (type 1).
It renames the network summary LSA to the interarea prefix LSA.
It renames the ASBR summary LSA to the interarea router LSA.
Router LSA is responsible for announcing interface parameters such as the interface
type and metric.
IP address information is advertised independently by two new LSA types:

•

•

•

Intra-area prefix LSA

•

Link-local LSA

Link-state database(LSDB) creates a shortest path topology tree based on links
instead of networks. Since IP address information is advertised using new LSA types
there is no longer a need to run SPF calculations every time a new address prefix is
added or changed on an interface.
© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

5

[ดูภาพต้นฉบับหน้า 5 ใน PDF](Chapter_10OSPFv3.pdf#page=5)

---

## หน้า 6

OSPFv3 Fundamentals

OSPFv3 Link-State Advertisement
LS Type

Name

Description

0x2001

Router

Every router generates router LSAs that describe the state and cost of the router’s interfaces to the
area.

0x2002

Network

A designated router generates network LSAs to announce all of the routers attached to the link,
including itself.

0x2003

Interarea Prefix

Area border routers generate interarea prefix LSAs to describe routes to IPv6 address prefixes that
belong to other areas.

0x2004

Interarea router

Area border routers generate interarea router LSAs to announce the addresses of autonomous
system boundary routers in other areas.

0x4005

AS external

Autonomous system boundary routers advertise AS external LSAs to announce default routes or
routes learned through redistribution from other protocols.

0x2007

NSSA

Autonomous system boundary routers that are located in a not-so-stubby area advertise NSSA LSAs
for routes redistributed into the area.

0x0008

Link

The link LSA maps all of the global unicast address prefixes associated with an interface to the linklocal interface IP address of the router. The link LSA is shared only between neighbors on the same
link.

0x2009

Intra-area prefix

The intra-area prefix LSA is used to advertise one or more IPv6 prefixes that are associated with a
router, stub, or transit network segment.

Table 10-2 OSPFv3 LSA Types

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

6

[ดูภาพต้นฉบับหน้า 6 ใน PDF](Chapter_10OSPFv3.pdf#page=6)

---

## หน้า 7

OSPFv3 Fundamentals

OSPFv3 Communication
Destination address is either a unicast link-local address or a multicast link-local scoped
address:
FF02::05: OSPFv3 AllSPFRouters
Every router uses AllSPFRouters multicast address to send OSPF hello messages to routers on the
same link.
Hello messages are used for neighbor discovery and detecting whether a neighbor relationship is
down.
DR and BDR routers also use this address to send link-state update and flooding acknowledgment
messages to all routers.

FF02::06: OSPFv3 AllDRouters designated router (DR)
Non-DR/BDR routers send an update or link-state acknowledgment message to the DR and BDR by
using the AllDRouters.
OSPFv3 uses the same five packet types and logic as OSPFv2.
© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

7

[ดูภาพต้นฉบับหน้า 7 ใน PDF](Chapter_10OSPFv3.pdf#page=7)

---

## หน้า 8

OSPFv3 Fundamentals

OSPFv3 Packet Types

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

8

[ดูภาพต้นฉบับหน้า 8 ใน PDF](Chapter_10OSPFv3.pdf#page=8)

---

## หน้า 9

OSPFv3 Configurations
Configuration Steps:
•
•
•
•

Step 1. Initialize the routing process with the command 'ipv6 unicast-routing'.
Step 2. Define the 32-bit router ID within the OSPFv3 router process.
Step 3. (Optional) Initialize the address family - enabled automatically when OSPFv3 is
enabled on an interface.
Step 4. Enable OSPFv3 on an interface using a process-id and area-id.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

9

[ดูภาพต้นฉบับหน้า 9 ใน PDF](Chapter_10OSPFv3.pdf#page=9)

---

## หน้า 10

OSPFv3 Configurations

OSPFv3 Topology
Figure 10-1 displays a simple four-router topology to demonstrate OSPFv3
configuration.
Area 0 consists of R1, R2, and R3, and Area 34 contains R3 and R4. R3 is the ABR.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

10

[ดูภาพต้นฉบับหน้า 10 ใน PDF](Chapter_10OSPFv3.pdf#page=10)

---

## หน้า 11

OSPFv3 Configurations

Example OSPFv3 Configuration
Earlier versions of IOS used the commands ipv6 router ospf for initialization of the OSPF
process and ipv6 ospf process-id area area-id for identification of the interface. These
commands are considered legacy and should be migrated to the current practice such as
ospfv3 process-id ipv6 area area-id in the R1 & R2 configurations, as highlighted below.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

11

[ดูภาพต้นฉบับหน้า 11 ใน PDF](Chapter_10OSPFv3.pdf#page=11)

---

## หน้า 12

OSPFv3 Configurations

Example OSPFv3 Configuration (Cont.)
R3 & R4 configurations steps are highlighted below.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

12

[ดูภาพต้นฉบับหน้า 12 ใน PDF](Chapter_10OSPFv3.pdf#page=12)

---

## หน้า 13

OSPFv3 Configurations

OSPFv3 Verification – Neighbor Adjacency
To view the R3 OSPFv3 Neighbor Adjacency the show opsfv3 ipv6 neighbor
command is used.
Neighbors router-id is displayed, OSPFv3 priority, state of the connection, and
the interface the neighbor is learned on.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

13

[ดูภาพต้นฉบับหน้า 13 ใน PDF](Chapter_10OSPFv3.pdf#page=13)

---

## หน้า 14

OSPFv3 Configurations

OSPFv3 Verification
Verifying the OSPFv3
interface information
provides the following:
•

Interface ID

•

Router ID

•

DR and Backup DR

•

Neighbor Adjacency

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

14

[ดูภาพต้นฉบับหน้า 14 ใน PDF](Chapter_10OSPFv3.pdf#page=14)

---

## หน้า 15

OSPFv3 Configurations

OSPFv3 Interface Verification
To show a brief listing of the interfaces participating in OSPFv3 Routing on R3
use the show ospfv3 interface brief command.
Important information includes the Interface, the area the interface belongs to, and the
role of the router on the link (State)

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

15

[ดูภาพต้นฉบับหน้า 15 ใน PDF](Chapter_10OSPFv3.pdf#page=15)

---

## หน้า 16

OSPFv3 Configurations

OSPFv3 Routing Verification
Output from the OSPFv3
routing table showing both
Intra-Area routes (O) and
Inter-Area routes (OI)
using the command show
ipv6 route ospf.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

16

[ดูภาพต้นฉบับหน้า 16 ใน PDF](Chapter_10OSPFv3.pdf#page=16)

---

## หน้า 17

OSPFv3 Configurations

OSPFv3 Passive Interface
OSPFv3 supports marking an interface as passive. The command is placed under
the OSPFv3 process or under the specific address family. Placing the command
under the global process cascades the setting to both address families.
•

The passive interface can be set explicitly to an interface (R1 configuration).

•

The passive interface can be set as default (R4 configuration).

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

17

[ดูภาพต้นฉบับหน้า 17 ใน PDF](Chapter_10OSPFv3.pdf#page=17)

---

## หน้า 18

OSPFv3 Configurations

OSPFv3 Route Summarization
Example 10-9 shows the summarization
commands applied to R3.
Route summarization reduces the
number of route entries on the
neighboring router as shown in
examples 10-8 and 10-10.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

18

[ดูภาพต้นฉบับหน้า 18 ใน PDF](Chapter_10OSPFv3.pdf#page=18)

---

## หน้า 19

OSPFv3 Configurations

OSPFv3 Verify Network Type
Configuration changes may be
necessary for a dynamically
learned network type. As
shown in Example 10-11 the
R2 G0/3 interface is shown as
a BROADCAST network type.
Based on the topology it
should be a point-to-point.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

19

[ดูภาพต้นฉบับหน้า 19 ใน PDF](Chapter_10OSPFv3.pdf#page=19)

---

## หน้า 20

OSPFv3 Configurations

OSPFv3 Change Network Type
When changes are made to the network type it is necessary to change both ends of the link to
match. The change is made directly on the interface.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

20

[ดูภาพต้นฉบับหน้า 20 ใน PDF](Chapter_10OSPFv3.pdf#page=20)

---

## หน้า 21

IPv4 Support in OSPFv3
Enabling IPv4 Support
• Step 1. Ensure that the IPv4 interface has an IPv6 address (global or link local)
configured.
• Step 2. Enable the OSPFv3 process for IPv4 on the interface with the command
ospfv3 process-id ipv4 area area-id.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

21

[ดูภาพต้นฉบับหน้า 21 ใน PDF](Chapter_10OSPFv3.pdf#page=21)

---

## หน้า 22

IPv4 Support in OSPFv3

Adding IPv4 support to existing interfaces
Using the command ospfv3 process-id ipv4 area area-id on an interface configured for
IPv6 adds IPv4 support. The interface must have an IPv6 global or link-local address.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

22

[ดูภาพต้นฉบับหน้า 22 ใน PDF](Chapter_10OSPFv3.pdf#page=22)

---

## หน้า 23

IPv4 Support in OSPFv3

Verifying IPv4 Routes
Verifying OSPFv3 routes for IPv4 is accomplished using the command show ip route
ospfv3.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

23

[ดูภาพต้นฉบับหน้า 23 ใน PDF](Chapter_10OSPFv3.pdf#page=23)

---

## หน้า 24

IPv4 Support in OSPFv3

Displaying OSPFv3 Interfaces
To display the interfaces configured for OSPFv3 and the respective address family use the
command show ospfv3 interface brief.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

24

[ดูภาพต้นฉบับหน้า 24 ใน PDF](Chapter_10OSPFv3.pdf#page=24)

---

## หน้า 25

IPv4 Support in OSPFv3

Verifying OSPFv3 Neighbors
To verify the OSPFv3 neighbors for both IPv4 and IPv6 use the command show ospfv3
neighbor.

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

25

[ดูภาพต้นฉบับหน้า 25 ใน PDF](Chapter_10OSPFv3.pdf#page=25)

---

## หน้า 26

Prepare for the Exam

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

26

[ดูภาพต้นฉบับหน้า 26 ใน PDF](Chapter_10OSPFv3.pdf#page=26)

---

## หน้า 27

Prepare for the Exam

Key Topics for Chapter 10

Description
OSPFv3 fundamentals
OSPFv3 Packet Types
OSPFv3 verification
OSPFv3 summarization
IPv4 support on OSPFv3

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

27

[ดูภาพต้นฉบับหน้า 27 ใน PDF](Chapter_10OSPFv3.pdf#page=27)

---

## หน้า 28

Prepare for the Exam

Command Reference for Chapter 10
Task

Command Syntax

Configure OSPFv3 on a router and enable
it on an interface

router ospfv3 [process-id]
interface interface-id
ospfv3 process-id {ipv4 | ipv6} area area-id

Configure a specific OSPFv3 interface as
passive

passive-interface interface-id

Configure all OSPFv3 interfaces as passive

passive-interface default

Summarize an IPv6 network range on an
ABR

area area-id range prefix/prefix-length

Configure an OSPFv3 interface as
point-to-point or broadcast network type

ospfv3 network {point-to-point | broadcast}

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

28

[ดูภาพต้นฉบับหน้า 28 ใน PDF](Chapter_10OSPFv3.pdf#page=28)

---

## หน้า 29

Prepare for the Exam

Command Reference for Chapter 10 (Cont.)
Task

Command Syntax

Display OSPFv3 interface settings

show ospfv3 interface [interface-id]

Display OSPFv3 IPv6 neighbors

show ospfv3 ipv6 neighbor

Display OSPFv3 router LSAs

show ospfv3 database router

Display OSPFv3 network LSAs

show ospfv3 database network

Display OSPFv3 link LSAs

show ospfv3 database link

© 2016 Cisco and/or its affiliates. All rights reserved. Cisco Confidential

29

[ดูภาพต้นฉบับหน้า 29 ใน PDF](Chapter_10OSPFv3.pdf#page=29)

---

## หน้า 30

_(หน้านี้ไม่มีข้อความที่ดึงได้ — ดูภาพใน PDF)_

[ดูภาพต้นฉบับหน้า 30 ใน PDF](Chapter_10OSPFv3.pdf#page=30)

---
