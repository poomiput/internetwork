# Chapter_16ISIS-Routing

> ฉบับสำหรับส่งต่อ: ใช้ข้อความจาก Markdown ที่ตรวจไว้เดิม ลิงก์ภาพเปลี่ยนเป็นการอ้างหน้าใน PDF ซึ่งแนบในโฟลเดอร์เดียวกัน โปรดเปิด PDF เมื่อต้องอ่านรูป ตาราง หรือไดอะแกรม

> ต้นฉบับ: [Chapter_16ISIS-Routing.pdf](Chapter_16ISIS-Routing.pdf)  
> จำนวน 80 หน้า — คงลำดับหน้าและภาพต้นฉบับทุกหน้า

> ข้อความที่ระบุ OCR ถอดจากภาพ; ส่วนที่อ่านไม่ชัดจะระบุไว้เพื่อเทียบกับต้นฉบับ

## หน้า 1

### ISIS Tutorial

**Philip Smith** — `<pfs@cisco.com>`

**MENOG 4**

**5th–9th April 2009, Bahrain**

[ดูภาพต้นฉบับหน้า 1 ใน PDF](Chapter_16ISIS-Routing.pdf#page=1)

---

## หน้า 2

### Presentation Slides

- Will be available on `ftp://ftp-eng.cisco.com/pfs/seminars/MENOG4-ISIS-Tutorial.pdf`
- And on the MENOG website
- Feel free to ask questions any time

[ดูภาพต้นฉบับหน้า 2 ใน PDF](Chapter_16ISIS-Routing.pdf#page=2)

---

## หน้า 3

### **Agenda** 

- Comparing ISIS and OSPF 

- Introduction to ISIS 

- ISIS Best Practices 

3 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 3 ใน PDF](Chapter_16ISIS-Routing.pdf#page=3)

---

## หน้า 4

#### Comparing ISIS and OSPF 

**Both Link State Protocols use the Dijkstra SPF Algorithm** 

**So what’s the difference then??** 

4 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 4 ใน PDF](Chapter_16ISIS-Routing.pdf#page=4)

---

## หน้า 5

### **What Is IS-IS ?** 

- Intermediate System to Intermediate System 

- An “IS” is ISO terminology for a router 

- IS-IS was originally designed for use as a dynamic routing protocol for ISO CLNP, defined in the ISO 10589 standard 

- Later adapted to carry IP prefixes in addition to CLNP (known as Integrated or Dual IS-IS) as described in RFC 1195 

- Predominantly used in ISP environment 

5 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 5 ใน PDF](Chapter_16ISIS-Routing.pdf#page=5)

---

## หน้า 6

### IS-IS Timeline

- 1978ish “New” Arpanet Algorithm
  - Eric Rosen et al
- 1986 to 90 Decnet Phase V
  - Radia Perlman, Mike Shand
- 1987 ISO 10589 (IS-IS)
  - Dave Oran
- 1990 RFC 1195 (Integrated IS-IS)
  - Ross Callon, Chris Gunner
- 1990 to present: All sorts of enhancements
  - Everyone contributed!
- 2008 RFC5308 adds IPv6 support
  - And RFC5120 adds Multi-Topology Routing support

[ดูภาพต้นฉบับหน้า 6 ใน PDF](Chapter_16ISIS-Routing.pdf#page=6)

---

## หน้า 7

### **What Is OSPF ?** 

- Open Shortest Path First 

- Link State Protocol using the Shortest Path First algorithm (Dijkstra) to calculate loop-free routes 

- Used purely within the TCP/IP environment 

- Designed to respond quickly to topology changes but using minimal protocol traffic 

- Used in both Enterprise and ISP Environment 

7 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 7 ใน PDF](Chapter_16ISIS-Routing.pdf#page=7)

---

## หน้า 8

### **OSPF Timeline** 

- Development began in 1987 by IETF 

- OSPFv1 published in 1989 with RFC 1131 

- OSPFv2 published in 1991 with RFC 1247 

- Further enhancements to OSPFv2 in 1994 with RFC 1583 and in 1997 with RFC 2178 

- Last revision was in 1998 with RFC 2328 to fix minor problems 

- All above OSPF RFCs authored by John Moy 

- RFC2740 introduced OSPFv3 (for IPv6) in 1999, replaced by RFC5340 in 2008 

8 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 8 ใน PDF](Chapter_16ISIS-Routing.pdf#page=8)

---

## หน้า 9

### IS-IS & OSPF: Similarities

- Both are Interior Gateway Protocols (IGP)
  - They distribute routing information between routers belonging to a single Autonomous System (AS)
- With support for:
  - Classless Inter-Domain Routing (CIDR)
  - Variable Subnet Length Masking (VLSM)
  - Authentication
  - Multi-path
  - IP unnumbered links

[ดูภาพต้นฉบับหน้า 9 ใน PDF](Chapter_16ISIS-Routing.pdf#page=9)

---

## หน้า 10

### **IS-IS and OSPF Terminology** 

| OSPF | ISIS |
| --- | --- |
| Host | End System (ES) |
| Router | Intermediate System (IS) |
| Link | Circuit |
| Packet | Protocol Data Unit (PDU) |
| Designated router (DR) | Designated IS (DIS) |
| Backup DR (BDR) | N/A (no BDIS is used) |
| Link-State Advertisement (LSA) | Link-State PDU (LSP) |
| Hello packet | IIH PDU |
| Database Description (DBD) | Complete sequence number PDU (CSNP) |


[ดูภาพต้นฉบับหน้า 10 ใน PDF](Chapter_16ISIS-Routing.pdf#page=10)

---

## หน้า 11

### **IS-IS and OSPF Terminology (Cont.)** 

| OSPF | ISIS |
| --- | --- |
| Area | Sub domain (area) |
| Non-backbone area | Level-1 area |
| Backbone area | Level-2 Sub domain (backbone) |
| Area Border Router (ABR) | L1L2 router |
| Autonomous System Boundary Router (ASBR) | Any IS |


[ดูภาพต้นฉบับหน้า 11 ใน PDF](Chapter_16ISIS-Routing.pdf#page=11)

---

## หน้า 12

### Transport

- OSPF uses IP Protocol 89 as transport

```text
Data Link Header | IP Header | OSPF Header | OSPF Data
```

- IS-IS is directly encapsulated in Layer 2

```text
Data Link Header | IS-IS Header | IS-IS Data
```

[ดูภาพต้นฉบับหน้า 12 ใน PDF](Chapter_16ISIS-Routing.pdf#page=12)

---

## หน้า 13

### For Service Providers

- Which IGP should an ISP choose?
  - Both OSPF and ISIS use Dijkstra SPF algorithm
  - Exhibit same convergence properties
  - ISIS less widely implemented on router platforms
  - ISIS runs on data link layer, OSPF runs on IP layer
  - Biggest ISPs tend to use ISIS
  - Main ISIS implementations more tuneable than equivalent OSPF implementations

[ดูภาพต้นฉบับหน้า 13 ใน PDF](Chapter_16ISIS-Routing.pdf#page=13)

---

## หน้า 14

### How to choose an IGP?

#### OSPF

- Rigid area design - all networks must have area 0 core, with sub-areas distributed around
- Suits ISPs with central high speed core network linking regional PoPs
- Teaches good routing protocol design practices

#### ISIS

- Relaxed two level design - L2 routers must be linked through the backbone
- Suits ISPs with “stringy” networks, diverse infrastructure, etc, not fitting central core model of OSPF
- More flexible than OSPF, but easier to make mistakes too

[ดูภาพต้นฉบับหน้า 14 ใน PDF](Chapter_16ISIS-Routing.pdf#page=14)

---

## หน้า 15

### **Other considerations** 

- ISIS runs on link layer 

Not possible to “attack” the IGP using IP as with OSPF 

- ISIS’s NSAP addressing scheme avoids dependencies on IP as with OSPF 

- Because biggest ISPs use ISIS, it tends to get new optimisation features before OSPF does 

15 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 15 ใน PDF](Chapter_16ISIS-Routing.pdf#page=15)

---

## หน้า 16

#### Introduction to ISIS 

16 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 16 ใน PDF](Chapter_16ISIS-Routing.pdf#page=16)

---

## หน้า 17

### IS-IS Standards History

- ISO 10589 specifies OSI IS-IS routing protocol for CLNS traffic
  - Tag/Length/Value (TLV) options to enhance the protocol
  - A Link State protocol with a 2 level hierarchical architecture.
- RFC 1195 added IP support
  - I/IS-IS runs on top of the Data Link Layer
  - Requires CLNP to be configured
- RFC5308 adds IPv6 address family support to IS-IS
- RFC5120 defines Multi-Topology concept for IS-IS
  - Permits IPv4 and IPv6 topologies which are not identical

[ดูภาพต้นฉบับหน้า 17 ใน PDF](Chapter_16ISIS-Routing.pdf#page=17)

---

## หน้า 18

### ISIS Levels

- ISIS has a 2 layer hierarchy
  - Level-2 (the backbone)
  - Level-1 (the areas)
- A router can be
  - Level-1 (L1) router
  - Level-2 (L2) router
  - Level-1-2 (L1L2) router

[ดูภาพต้นฉบับหน้า 18 ใน PDF](Chapter_16ISIS-Routing.pdf#page=18)

---

## หน้า 19

### ISIS Levels

- Level-1 router
  - Has neighbours only on the same area
  - Has a level-1 LSDB with all routing information for the area
- Level-2 router
  - May have neighbours in the same or other areas
  - Has a Level-2 LSDB with all routing information about inter-area
- Level-1-2 router
  - May have neighbours on any area.
  - Has two separate LSDBs: level-1 LSDB & level-2 LSDB

[ดูภาพต้นฉบับหน้า 19 ใน PDF](Chapter_16ISIS-Routing.pdf#page=19)

---

## หน้า 20

### **Backbone & Areas** 

- ISIS does not have a backbone area as such (like OSPF) 

- Instead the backbone is the contiguous collection of Level-2 capable routers 

- ISIS area borders are on links, not routers 

- Each router is identified with Network Entity Title (NET)
  - NET is an NSAP where the n-selector is 0 

20 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 20 ใน PDF](Chapter_16ISIS-Routing.pdf#page=20)

---

## หน้า 21

### L1, L2, and L1L2 Routers

ข้อความและความสัมพันธ์ในแผนภาพ:

- Area-1: L1-only เชื่อมกับ L1L2; L1L2 เชื่อมข้าม area ไป L1L2 ด้านซ้ายของ Area-2
- Area-2: L1-only ด้านบนซ้าย, L1L2 ด้านบนขวา, L1L2 ด้านซ้าย, L1-only ด้านล่าง และ L1L2 ด้านขวา เชื่อมเป็นวงภายใน area
- L1L2 ด้านขวาของ Area-2 เชื่อมไป L2-only ใน Area-3 และ L1L2 ใน Area-4
- L2-only ใน Area-3 เชื่อมไป L1L2 ใน Area-4
- Area-4: L1L2 เชื่อมกับ L1-only

[ดูภาพต้นฉบับหน้า 21 ใน PDF](Chapter_16ISIS-Routing.pdf#page=21)

---

## หน้า 22

### NSAP and Addressing

```text
IDP: AFI | IDI
DSP: High Order DSP | System ID | NSEL
AFI + IDI + High Order DSP: Variable length Area address
System ID: 6 bytes
NSEL: 1 byte
```

- NSAP: Network Service Access Point
  - Total length between 8 and 20 bytes
  - Area Address: variable length field (up to 13 bytes)
  - System ID: defines an ES or IS in an area.
  - NSEL: N-selector. identifies a network service user (transport entity or the IS network entity itself)
- NET: the address of the network entity itself

[ดูภาพต้นฉบับหน้า 22 ใน PDF](Chapter_16ISIS-Routing.pdf#page=22)

---

## หน้า 23

### **An Addressing Example** 

| Area ในภาพ | NSAP ที่แสดง |
| --- | --- |
| Area 1 | `49.0f01.0001.1111.1111.1111.00`<br>`49.0f01.0001.2222.2222.2222.00` |
| Area 2 | `49.0f01.0002.3333.3333.3333.00`<br>`49.0f01.0002.4444.4444.4444.00` |
| Area 3 | `49.0f01.0003.6666.6666.6666.00` |
| Area 4 | `49.0f01.0004.7777.7777.7777.00`<br>`49.0f01.0004.8888.8888.8888.00` |


ภาพแสดงการเชื่อมต่อระหว่าง Area 1–2, Area 2–3, Area 2–4 และ Area 3–4; router ด้านขวาของ Area 2 ไม่มี NSAP กำกับในภาพ

[ดูภาพต้นฉบับหน้า 23 ใน PDF](Chapter_16ISIS-Routing.pdf#page=23)

---

## หน้า 24

### Addressing Common Practices

- ISPs typically choose NSAP addresses thus:
  - First 8 bits – pick a number (usually 49)
  - Next 16 bits – area
  - Next 48 bits – router loopback address
  - Final 8 bits – zero
- Example:
  - NSAP: `49.0001.1921.6800.1001.00`
  - Router: `192.168.1.1` (loopback) in Area 1

[ดูภาพต้นฉบับหน้า 24 ใน PDF](Chapter_16ISIS-Routing.pdf#page=24)

---

## หน้า 25

### **Adjacencies** 

- Hello PDU IIHs are exchanged between routers to form adjacencies 

**ISIS adjacency through IIH** 

- Area addresses are exchanged in IIH PDUs 

25 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 25 ใน PDF](Chapter_16ISIS-Routing.pdf#page=25)

---

## หน้า 26

### **Link State PDU (LSP)** 

- Each router creates an LSP and flood it to neighbours 

- A level-1 router will create level-1 LSP(s) 

- A level-2 router will create level-2 LSP(s) 

- A level-1-2 router will create 

  - level-1 LSP(s) and
  - level-2 LSP(s) 

26 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 26 ใน PDF](Chapter_16ISIS-Routing.pdf#page=26)

---

## หน้า 27

### LSP Header

- LSPs have
  - Fixed header
  - TLV coded contents
- The LSP header contains
  - LSP-id
  - Sequence number
  - Remaining Lifetime
  - Checksum
  - Type of LSP (level-1, level-2)
  - Attached bit
  - Overload bit

[ดูภาพต้นฉบับหน้า 27 ใน PDF](Chapter_16ISIS-Routing.pdf#page=27)

---

## หน้า 28

### LSP Contents

- The LSP contents are coded as TLV (Type, Length, Value)
  - Area addresses
  - IS neighbors
  - Authentication Info

[ดูภาพต้นฉบับหน้า 28 ใน PDF](Chapter_16ISIS-Routing.pdf#page=28)

---

## หน้า 29

### **LSDB content** 

- Each router maintains a separate LSDB for level-1 and level-2 LSPs 

- LSP headers and contents 

- SRM bits: set per interface when router has to flood this LSP 

- SSN bits: set per interface when router has to send a PSNP for this LSP 

29 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 29 ใน PDF](Chapter_16ISIS-Routing.pdf#page=29)

---

## หน้า 30

### **Flooding of LSPs** 

- New LSPs are flooded to all neighbors 

- It is necessary that all routers get all LSPs 

- Each LSP has a sequence number 

- 2 kinds of flooding
  - Flooding on a p2p link
  - Flooding on LAN 

30 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 30 ใน PDF](Chapter_16ISIS-Routing.pdf#page=30)

---

## หน้า 31

### **Flooding on a p2p link** 

- Once the adjacency is established both routers send CSNP packet 

- Missing LSPs are sent by both routers if not present in the received CSNP 

- Missing LSPs may be requested through PSNP 

31 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 31 ใน PDF](Chapter_16ISIS-Routing.pdf#page=31)

---

## หน้า 32

### **Flooding on a LAN** 

- There’s a Designated Router (DIS) 

- DIS election is based on priority 

Best practice is to select two routers and give them higher priority – then in case of failure one provides deterministic backup to the other 

- Tie break is by the highest MAC address 

- DIS has two tasks 

  - Conducting the flooding over the LAN
  - Creating and updating a special LSP describing the LAN topology (Pseudonode LSP) 

- Pseudonode represents LAN (created by the DIS) 

32 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 32 ใน PDF](Chapter_16ISIS-Routing.pdf#page=32)

---

## หน้า 33

### **Flooding on a LAN** 

- DIS conducts the flooding over the LAN 

- DIS multicasts CSNP every 10 seconds 

- All routers in the LAN check the CSNP against their own LSDB (and may ask specific re-transmissions with PSNPs) 

33 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 33 ใน PDF](Chapter_16ISIS-Routing.pdf#page=33)

---

## หน้า 34

### **Complete Sequence Number PDU** 

- Describes all LSPs in your LSDB (in range) 

- If LSDB is large, multiple CSNPs are sent 

- Used at 2 occasions 

  - Periodic multicast by DIS (every 10 seconds) to synchronise LSDB over LAN subnets 

  - On p2p links when link comes up 

34 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 34 ใน PDF](Chapter_16ISIS-Routing.pdf#page=34)

---

## หน้า 35

### Partial Sequence Number PDUs

- PSNPs Exchanged on p2p links (ACKs)
- Two functions
  - Acknowledge receipt of an LSP
  - Request transmission of latest LSP
- PSNPs describe LSPs by its header
  - LSP identifier
  - Sequence number
  - Remaining lifetime
  - LSP checksum

[ดูภาพต้นฉบับหน้า 35 ใน PDF](Chapter_16ISIS-Routing.pdf#page=35)

---

## หน้า 36

### Configuration

แผนภาพ: Area-2 — Rtr-A — Rtr-B — Rtr-C — Area-3 โดย Rtr-A/B/C อยู่ใน Area-1

- L1, L2, L1-L2
  - **By default cisco routers will be L1L2 routers**
  - Routers can be manually configured to behave as Level-1 only, Level-2 only, Level-1-2
    - This is what most ISPs do
  - Configuration can be done per interface or at the router level

[ดูภาพต้นฉบับหน้า 36 ใน PDF](Chapter_16ISIS-Routing.pdf#page=36)

---

## หน้า 37

### Configuration for A&B

```text
Router-B
interface Loopback0
 ip address 192.168.1.1 255.255.255.255
!
Interface Pos2/0/0
 ip address 192.168.222.1 255.255.255.0
 ip router isis
 isis circuit-type level-2
!
FastEthernet4/0/0
 ip address 192.168.120.10 255.255.255.0
 ip router isis
 isis circuit-type level-1
!
router isis
 passive-interface Loopback0
 net 49.0001.1921.6800.1001.00

Router-A
interface Loopback0
 ip address 192.168.1.5 255.255.255.255
!
interface FastEthernet0/0
 ip address 192.168.120.5 255.255.255.0
 ip router isis
!
router isis
 is-type level-1
 passive-interface Loopback0
 net 49.0001.1921.6800.1005.00
```

แผนภาพ: Rtr-A (L1) — Rtr-B (L1L2) ใน Area 49.0001; Rtr-B — Rtr-C เชื่อมข้าม area; Rtr-C (L1L2) — Rtr-D (L1) ใน Area 49.0002

> หมายเหตุจากการตรวจ: ต้นฉบับบรรทัด FastEthernet4/0/0 ไม่มีคำว่า interface จึงถอดตามที่เห็น

[ดูภาพต้นฉบับหน้า 37 ใน PDF](Chapter_16ISIS-Routing.pdf#page=37)

---

## หน้า 38

### Configuration for C&D

```text
Router-C
interface Loopback0
 ip address 192.168.2.2 255.255.255.255
!
Interface Pos1/0/0
 ip address 192.168.222.2 255.255.255.0
 ip router isis
 isis circuit-type level-2
!
interface Fddi3/0
 ip address 192.168.111.2 255.255.255.0
 ip router isis
 isis circuit-type level-1
!
router isis
 passive-interface Loopback0
 net 49.0002.1921.6800.2002.00

Router-D
interface Loopback0
 ip address 192.168.2.4 255.255.255.255
!
interface Fddi6/0
 ip address 192.168.111.4 255.255.255.0
 ip router isis
!
router isis
 is-type level-1
 passive-interface Loopback0
 net 49.0002.1921.6800.2004.00
```

แผนภาพเหมือนหน้าก่อน: Area 49.0001 (Rtr-A L1, Rtr-B L1L2) และ Area 49.0002 (Rtr-C L1L2, Rtr-D L1)

[ดูภาพต้นฉบับหน้า 38 ใน PDF](Chapter_16ISIS-Routing.pdf#page=38)

---

## หน้า 39

### Adding interfaces to ISIS

- To activate ISIS on an interface:

```text
interface HSSI 4/0
 ip route isis isp-bb
 isis circuit-type level-2
```

- To disable ISIS on an interface:

```text
router isis isp-bb
 passive-interface GigabitEthernet 0/0
```

  - Disables CLNS on that interface
  - Puts the interface subnet address into the LSDB
- No ISIS configuration on an interface
  - No CLNS run on interface, no interface subnet in the LSDB

> หมายเหตุจากการตรวจ: ต้นฉบับแสดง ip route isis isp-bb ตามนี้ (ต่างจาก ip router isis ในหน้าถัดไป)

[ดูภาพต้นฉบับหน้า 39 ใน PDF](Chapter_16ISIS-Routing.pdf#page=39)

---

## หน้า 40

### Adding interfaces to ISIS

- Scaling ISIS: `passive-interface default`
  - Disables ISIS processing on all interfaces apart from those marked as no-passive
  - Places all IP addresses of all connected interfaces into ISIS
  - Must be at least one non-passive interface:

```text
router isis isp-bb
 passive-interface default
 no passive-interface GigabitEthernet 0/0
interface GigabitEthernet 0/0
 ip router isis isp-bb
 isis metric 1 level-2
```

[ดูภาพต้นฉบับหน้า 40 ใน PDF](Chapter_16ISIS-Routing.pdf#page=40)

---

## หน้า 41

### Status Commands in ISIS — Show clns

```text
Rtr-B>show clns
Global CLNS Information:
  2 Interfaces Enabled for CLNS
  NET: 49.0001.1921.6800.1001.00
  Configuration Timer: 60, Default Holding Timer: 300, Packet
  Lifetime 64
  ERPDU's requested on locally generated packets
  Intermediate system operation enabled (forwarding allowed)
  IS-IS level-1-2 Router:
    Routing for Area: 49.0001
```

Shows the global CLNS status as seen on the router, e.g.

[ดูภาพต้นฉบับหน้า 41 ใน PDF](Chapter_16ISIS-Routing.pdf#page=41)

---

## หน้า 42

### Status Commands in ISIS — Show clns neighbors

```text
Rtr-B> show clns neighbors
System Id       SNPA           Interface State Holdtime Type Protocol
1921.6800.2002   *PPP*          PO2/0/0    Up       29    L2   IS-IS
1921.6800.1005   00e0.1492.2c00 Fa4/0/0    Up        9    L1   IS-IS
```

Shows the neighbour adjacencies as seen by the router.

More recent IOSes replace system ID with router hostname – ease of troubleshooting

[ดูภาพต้นฉบับหน้า 42 ใน PDF](Chapter_16ISIS-Routing.pdf#page=42)

---

## หน้า 43

### Status Commands in ISIS — Show clns interface

```text
Rtr-B>  show clns interface POS2/0/0
POS2/0/0 is up, line protocol is up
  Checksums enabled, MTU 4470, Encapsulation PPP
  ERPDUs enabled, min. interval 10 msec.
  RDPDUs enabled, min. interval 100 msec., Addr Mask enabled
 Congestion Experienced bit set at 4 packets
  DEC compatibility mode OFF for this interface
  Next ESH/ISH in 47 seconds
  Routing Protocol: IS-IS
    Circuit Type: level-1-2
    Interface number 0x0, local circuit ID 0x100
    Level-1 Metric: 10, Priority: 64, Circuit ID: 1921.6800.2002.00
    Number of active level-1 adjacencies: 0
    Level-2 Metric: 10, Priority: 64, Circuit ID: 1921.6800.1001.00
    Number of active level-2 adjacencies: 1
    Next IS-IS Hello in 2 seconds
```

Shows the CLNS status on a router interface.

[ดูภาพต้นฉบับหน้า 43 ใน PDF](Chapter_16ISIS-Routing.pdf#page=43)

---

## หน้า 44

### Status Commands in ISIS — Show CLNS protocol

```text
Rtr-B> show clns protocol
IS-IS Router: <Null Tag>
  System Id: 1921.6800.1001.00  IS-Type: level-1-2
  Manual area address(es):
        49.0001
  Routing for area address(es):
        49.0001
  Interfaces supported by IS-IS:
        FastEthernet4/0/0 - IP
        POS2/0/0 - IP
  Redistributing:
    static
  Distance: 110
```

Displays the status of the CLNS protocol on the router.

[ดูภาพต้นฉบับหน้า 44 ใน PDF](Chapter_16ISIS-Routing.pdf#page=44)

---

## หน้า 45

### **Other status commands** 

- “show clns traffic” 

Shows CLNS traffic statistics and activity for the network 

- “show isis database” 

Shows the ISIS link state database i.e. the “routing table” 

45 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 45 ใน PDF](Chapter_16ISIS-Routing.pdf#page=45)

---

## หน้า 46

### **Network Design Issues** 

- As in all IP network designs, the key issue is the addressing lay-out 

- ISIS supports a large number of routers in a single area 

- When using areas, use summary-addresses 

- >400 routers in the backbone is quite doable 

46 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 46 ใน PDF](Chapter_16ISIS-Routing.pdf#page=46)

---

## หน้า 47

### Network Design Issues

- Possible link cost
  - Default on all interfaces is 10
  - (Compare with OSPF which sets cost according to link bandwidth)
  - Manually configured according to routing strategy
- Summary address cost
  - Equal to the best more specific cost
  - Plus cost to reach neighbor of best specific
- Backbone has to be contiguous
  - Ensure continuity by redundancy
- Area partitioning
  - Design so that backbone can NOT be partitioned

[ดูภาพต้นฉบับหน้า 47 ใน PDF](Chapter_16ISIS-Routing.pdf#page=47)

---

## หน้า 48

### Scaling Issues

- Areas vs. single area
  - Use areas where
    - sub-optimal routing is not an issue
    - areas with one single exit point
  - Start with L2-only everywhere is a good choice
  - Future implementation of level-1 areas will be easier
  - Backbone continuity is ensured from start

[ดูภาพต้นฉบับหน้า 48 ใน PDF](Chapter_16ISIS-Routing.pdf#page=48)

---

## หน้า 49

#### ISIS for IPv6 

49 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 49 ใน PDF](Chapter_16ISIS-Routing.pdf#page=49)

---

## หน้า 50

### IS-IS for IPv6

- 2 Tag/Length/Values added to introduce IPv6 routing
- IPv6 Reachability TLV (0xEC)
  - External bit
  - Equivalent to IP Internal/External Reachability TLV’s
- IPv6 Interface Address TLV (0xE8)
  - For Hello PDUs, must contain the Link-Local address
  - For LSP, must only contain the non-Link Local address
- IPv6 NLPID (0x8E) is advertised by IPv6 enabled routers

[ดูภาพต้นฉบับหน้า 50 ใน PDF](Chapter_16ISIS-Routing.pdf#page=50)

---

## หน้า 51

### IOS IS-IS dual IP configuration

Router1 เชื่อม Ethernet-1 กับ LAN1: `2001:db8:1::/64` และ Ethernet-2 กับ LAN2: `2001:db8:2::/64`.

```text
Router1#
interface ethernet-1
 ip address 10.1.1.1 255.255.255.0
 ipv6 address 2001:db8:1::1/64
 ip router isis
 ipv6 router isis

interface ethernet-2
 ip address 10.2.1.1 255.255.255.0
 ipv6 address 2001:db8:2::1/64
 ip router isis
 ipv6 router isis

router isis
 address-family ipv6
  redistribute static
  exit-address-family
 net 49.0001.0000.0000.072c.00
 redistribute static
```

Dual IPv4/IPv6 configuration. Redistributing both IPv6 static routes and IPv4 static routes.

[ดูภาพต้นฉบับหน้า 51 ใน PDF](Chapter_16ISIS-Routing.pdf#page=51)

---

## หน้า 52

### IOS Configuration for IS-IS for IPv6 on IPv6 Tunnels over IPv4

```text
On Router1:
interface Tunnel0
 no ip address
 ipv6 address 2001:db8:1::1/64
 ipv6 address FE80::10:7BC2:ACC9:10 link-local
 ipv6 router isis
 tunnel source 10.42.1.1
 tunnel destination 10.42.2.1
!
router isis
 net 49.0001.0000.0000.0001.00

On Router2:
interface Tunnel0
 no ip address
 ipv6 address 2001:db8:1::2/64
 ipv6 address FE80::10:7BC2:B280:11 link-local
 ipv6 router isis
 tunnel source 10.42.2.1
 tunnel destination 10.42.1.1
!
router isis
 net 49.0001.0000.0000.0002.00
```

แผนภาพ: IPv6 Network สามแห่งเชื่อม router สามตัวใน IPv4 Backbone; router แต่ละคู่เชื่อมด้วย IPv6 Tunnel เป็นรูปสามเหลี่ยม.

IS-IS for IPv6 on an IPv6 Tunnel requires GRE Tunnel; it can’t work with IPv6 configured tunnel as IS-IS runs directly over the data link layer.

[ดูภาพต้นฉบับหน้า 52 ใน PDF](Chapter_16ISIS-Routing.pdf#page=52)

---

## หน้า 53

### Multi-Topology IS-IS extensions

- IS-IS for IPv6 assumes that the IPv6 topology is the same as the IPv4 topology
  - Single SPF running, multiple address families
  - Some networks may be like this, but many others are not
- Multi-Topology IS-IS solves this problem
  - New TLV attributes introduced
  - New Multi-Topology ID #2 for IPv6 Routing Topology
  - Two topologies now maintained:
    - ISO/IPv4 Routing Topology (MT ID #0)
    - IPv6 Routing Topology (MT ID #2)

[ดูภาพต้นฉบับหน้า 53 ใน PDF](Chapter_16ISIS-Routing.pdf#page=53)

---

## หน้า 54

### **Multi-Topology IS-IS extensions** 

- New TLVs attributes for Multi-Topology extensions: 
  - Multi-topology TLV: contains one or more multi-topology ID in which the router participates 
  - MT Intermediate Systems TLV: this TLV appears as many times as the number of topologies a node supports 
  - Multi-Topology Reachable IPv4 Prefixes TLV: this TLV appears as many times as the number of IPv4 announced by an IS for a given MT ID 
  - Multi-Topology Reachable IPv6 Prefixes TLV: this TLV appears as many times as the number of IPv6 announced by an IS for a given MT ID 

54 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 54 ใน PDF](Chapter_16ISIS-Routing.pdf#page=54)

---

## หน้า 55

### Multi-Topology ISIS configuration example (IOS)

แผนภาพ: Router1 ผ่าน Ethernet 1 ไป LAN1: `2001:db8:1::1/64` และ Area B; Ethernet 2 ไป LAN2: `2001:db8:2::1/64`.

```text
Router1#
interface Ethernet 1
 ip address 10.1.1.1 255.255.255.0
 ipv6 address 2001:db8:1::1/64
 ip router isis
 ipv6 router isis
 isis ipv6 metric 20

interface Ethernet 2
 ip address 10.2.1.1 255.255.255.0
 ipv6 address 2001:db8:2::1/64
 ip router isis
 ipv6 router isis
 isis ipv6 metric 20

router isis
 net 49.0001.0000.0000.072c.00
 metric-style wide
 !
 address-family ipv6
  multi-topology
 exit-address-family
```

- The optional keyword **transition** may be used for transitioning existing IS-IS IPv6 single SPF mode to MT IS-IS
- Wide metric is mandated for Multi-Topology to work

[ดูภาพต้นฉบับหน้า 55 ใน PDF](Chapter_16ISIS-Routing.pdf#page=55)

---

## หน้า 56

### Narrow to Wide Metrics Transition

- When migrating from narrow to wide metrics, care is required
  - Narrow and wide metrics are NOT compatible with each other
  - Migration is a two stage process, using the “transition” keyword
- Networks using narrow metrics should first configure across all routers:

```text
router isis isp
 metric-style transition
```

- Once the whole network is changed to transition support, the metric style can be changed to wide:

```text
router isis isp
 metric-style wide
```

[ดูภาพต้นฉบับหน้า 56 ใน PDF](Chapter_16ISIS-Routing.pdf#page=56)

---

## หน้า 57

### ISP common practices

- NSAP address construction
  - Area and loopback address
- L2
  - L1-L2 and L1 used later for scaling
- Wide metrics
  - Narrow metrics are too limiting
- Deploying IPv6 in addition to IPv4
  - Multi-topology is recommended – gives increased flexibility should there be future differences in topology

[ดูภาพต้นฉบับหน้า 57 ใน PDF](Chapter_16ISIS-Routing.pdf#page=57)

---

## หน้า 58

#### ISP Best Practices 

##### **Extra detailed information** 

58 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 58 ใน PDF](Chapter_16ISIS-Routing.pdf#page=58)

---

## หน้า 59

### **Purging the RIB on link failure** 

- For routing protocols that are capable of responding to link failures, IOS allows such routing protocols to quickly and more efficiently delete associated routes from the RIB when a link, and the interface is removed from the routing table 

- Without this command, the "less efficient" RIB process is used to delete the associated next-hop routes of the failed interface, by default 

If this process has to work through a very large routing table, it can use up a number of CPU cycles and potentially increase convergence time. 

```text
ip routing protocol purge interface
``` 

59 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 59 ใน PDF](Chapter_16ISIS-Routing.pdf#page=59)

---

## หน้า 60

### ISIS neighbour authentication

- Create key chains to be used for HMAC-MD5 authentication for both Level-1 and Level-2

```text
key chain isis-sec-l1
 key 1
   key-string xxxxx
key chain isis-sec-l2
 key 1
   key-string xxxxx
```

[ดูภาพต้นฉบับหน้า 60 ใน PDF](Chapter_16ISIS-Routing.pdf#page=60)

---

## หน้า 61

### Setting up Loopback Interface

- Create the Loopback interface/Router-ID
  - It will NOT have IS-IS running on it because it is not a transit interface
  - Disabling IS-IS on it, while announcing the IP prefixes into IS-IS, allows the IS-IS domain to scale because LSP/Hello packets are not unnecessarily generated for the Loopback interface
  - An IS-IS metric will NOT be set, which will default the Loopback interface's metric to zero (0).

```text
interface loopback0
 ip address 192.168.0.1 255.255.255.255
 ipv6 address 2001:db8:192:168:0:1/128
```

[ดูภาพต้นฉบับหน้า 61 ใน PDF](Chapter_16ISIS-Routing.pdf#page=61)

---

## หน้า 62

### Level-1 Interface Configuration

- Configure addresses and enable ISIS for IPv4 and IPv6

```text
interface gigabitethernet0/1
 ip address 192.168.1.1 255.255.255.192
 ipv6 address 2001:db8:192:168:1:1/112
 !
 ip router isis 1
 ipv6 router isis 1
```

- Ensure this interfaces runs at Level-1

```text
 isis circuit-type level-1
```

[ดูภาพต้นฉบับหน้า 62 ใน PDF](Chapter_16ISIS-Routing.pdf#page=62)

---

## หน้า 63

### Level-1 Interface: Metrics & Auth

- Set the costs for IPv4 and IPv6

```text
interface gigabitethernet0/1
 isis metric 400 level-1
 isis ipv6 metric 400 level-1
```

- Enable HMAC-MD5 for level-1

```text
 isis authentication mode md5 level-1
```

- Associate the key-chain defined earlier

```text
 isis authentication key-chain isis-sec-l1 level-1
```

[ดูภาพต้นฉบับหน้า 63 ใน PDF](Chapter_16ISIS-Routing.pdf#page=63)

---

## หน้า 64

### Level-1 Interface: DIS and BFD

- Set this IS to be the DIS in this Level-1 area
  - A DIS of 126 (higher than the default of 64) configured on another IS in this area sets it up as the backup DIS

```text
interface gigabitethernet0/1
 isis priority 127 level-1
```

- Enable BFD for fast failure detection
  - BFD helps reduce the convergence times of IS-IS because link failures will be signalled much quicker

```text
interface gigabitethernet0/1
 bfd interval 250 min_rx 250 multiplier 3
```

[ดูภาพต้นฉบับหน้า 64 ใน PDF](Chapter_16ISIS-Routing.pdf#page=64)

---

## หน้า 65

### **Level-2 interface** 

- This interface is used for a trunk link to another PoP forming part of your network-wide backbone 

As such it will be a Level-2 interface, making this router a Level1/Level-2 IS. 

Metric and authentication are all configured for Level-2 

```text
interface gigabitethernet0/2
ip address 192.168.2.1 255.255.255.252
ipv6 address 2001:db8:192:168:2:1:/126
ip router isis 1
ipv6 router isis 1
isis circuit-type level-2-only
isis metric 400 level-2
isis ipv6 metric 400 level-2
isis authentication mode md5 level-2
isis authentication key-chain isis-sec-l2 level-2
```

 

65 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

> หมายเหตุจากการตรวจ: IPv6 address ในต้นฉบับมี colon ก่อน /126 (`2001:db8:192:168:2:1:/126`) คงตามภาพไว้

[ดูภาพต้นฉบับหน้า 65 ใน PDF](Chapter_16ISIS-Routing.pdf#page=65)

---

## หน้า 66

### **Level 2 interface: more details** 

- To make this IS-IS BCP more interesting, we will assume this trunk link is a broadcast multi-access link, i.e., Ethernet. 

- As this is an Ethernet interface, IS-IS will attempt to elect a DIS when it forms an adjacency 

Because it is running as a point-to-point WAN link, with only 2 IS's on the wire, configuring IS-IS to operate in "point-to-point mode" scales the protocol by reducing the link failure detection times 

Point-to-point mode improves convergence times on Ethernet networks because it: 

Prevents the election of a DIS on the wire, Prevents the flooding process from using CSNP's for database synchronization 

Simplifies the SPF computations and reduces the IS's memory footprint due to a smaller topology database. 

```text
int gi0/2
```

 

```text
isis network point-to-point
```

 

66 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 66 ใน PDF](Chapter_16ISIS-Routing.pdf#page=66)

---

## หน้า 67

### **ISP Best Practices** 

• We now configure parameters specific to the IS-IS routing protocol This covers both IPv4 and IPv6, as IS-IS supports both IP protocols in the same implementation 

```text
router isis 1
```

 

- Create an NET 

This is made up of a private AFI (49), an area part, a System ID (taken from the padded Loopback interface IP address) and an N-SEL of zero (0). 

```text
net 49.0001.1921.6800.0001.00
```

 

- Enable HMAC-MD5 authentication 

```text
authentication mode md5
authentication key-chain isis-sec-l1 level-1
authentication key-chain isis-sec-l2 level-2
```

 

67 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 67 ใน PDF](Chapter_16ISIS-Routing.pdf#page=67)

---

## หน้า 68

### **ISP Best Practices** 

- Enable iSPF (incremental SPF). 

This, in the long run, reduces CPU demand because SPF calculations are run only on the affected changes in the SPT. 

As this is a Level-1/Level-2 router, enable iSPF at both levels 60 seconds after the command has been entered into the configuration. Note that IOS only supports iSPF for IPv4. 

```text
ispf level-1-2 60
```

 

- Enable wide/extended metric support for IS-IS. 

IOS, by default, supports narrow metrics, which means you can define cost values between 1-63. This is not scalable. 

To solve this problem, enable wide metrics, which allows you to define cost values between 1-16777214. 

```text
metric-style wide
```

 

68 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 68 ใน PDF](Chapter_16ISIS-Routing.pdf#page=68)

---

## หน้า 69

### **ISP Best Practices** 

- Increase ISIS default metric 

Default value is 10 

All interfaces in both L1 and L2 have this value 

Not useful if configured value is “accidentally” removed - a low priority interface could end up taking full load by mistake Configure a “very large” value as default 

```text
metric 100000
```

 

- Disable IIH padding because on high speed links, it may strain huge buffers; and on low speed links, it may waste bandwidth and affect other time sensitive applications, e.g., voice. 

Disabling IIH padding is safe because IOS will still pad the first 5 IIH's to the full MTU to aid in the discovery of MTU mismatches. 

```text
no hello padding
```

 

69 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 69 ใน PDF](Chapter_16ISIS-Routing.pdf#page=69)

---

## หน้า 70

### **ISP Best Practices** 

- Allow the Loopback interface IP address to be carried within IS-IS, while preventing it from being considered in the flooding process. 

```text
passive-interface Loopback0
```

 

- Log changes in the state of the adjacencies. 

```text
log-adjacency-changes
```

 

- Tell the IS to ignore LSP's with an incorrect data-link checksum, rather than purge them 

Purging LSP's with a bad checksum causes the initiating IS to regenerate that LSP, which could overload the IS if perpetuated in a cycle 

So rather than purge them, ignore them. 

```text
ignore-lsp-errors
```

 

70 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 70 ใน PDF](Chapter_16ISIS-Routing.pdf#page=70)

---

## หน้า 71

### **ISP Best Practices** 

- Reduce the amount of control traffic, conserving CPU usage for generation and refreshing of LSP's. 

Do this by increasing the LSP lifetime to its limits. 

```text
max-lsp-lifetime 65535
```

 

- Reduce the frequency of periodic LSP flooding of the topology, which reduces link utilization 

This is safe because there other mechanisms to guard against persistence of corrupted LSP's in the LSDB. 

```text
lsp-refresh-interval 65000
```

 

- Customize IS-IS throttling of SPF calculations. Good for when you also use BFD for IS-IS. These are recommended values for fast convergence. 

```text
spf-interval 5 1 20
```

 

71 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 71 ใน PDF](Chapter_16ISIS-Routing.pdf#page=71)

---

## หน้า 72

### **ISP Best Practices** 

- Customize IS-IS throttling of PRC calculations. 

PRC calculates routes without performing a full SFP calculation. This is done when a change is signaled by another IS, but without a corresponding change in the basic network topology, e.g., the need to reinstall a route in the IS-IS RIB. 

These are recommended values for fast convergence. 

```text
prc-interval 5 1 20
```

 

- Customize IS-IS throttling of LSP generation. These are recommended values for fast convergence. 

```text
lsp-gen-interval 5 1 20
```

 

72 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 72 ใน PDF](Chapter_16ISIS-Routing.pdf#page=72)

---

## หน้า 73

### **ISP Best Practices** 

- Enable IS-IS fast-flooding of LSP's. 

This tells the IS to always flood the LSP that triggered an SPF before the router actually runs the SPF computation. 

This command used to be 'ip fast-convergence' and has since been replaced from IOS 12.3(7)T. 

Below, we shall tell the IS to flood the first 10 LSP's which invoke the SPF before the SPF computation is started 

```text
fast-flood 10
```

 

- Enable IS-IS IETF Graceful Restart. 

This ensures an IS going through a control plane switchover continues to forward traffic as if nothing happened 

Software and platform support is limited, so check whether your particular platform/code supports this 

Also, deploy only if it's necessary. 

```text
nsf ietf
```

 

73 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 73 ใน PDF](Chapter_16ISIS-Routing.pdf#page=73)

---

## หน้า 74

### **ISP Best Practices** 

- Enable BFD support for IS-IS. 

With BFD running on the interface, a failure of the link would signal IS-IS immediately 

IS-IS will then converge accordingly. 

```text
bfd all-interfaces
```

 

- Tell IS-IS to ignore the attached bit 

The Attached bit is set when an L1/L2 IS learns L1 routes from other L1 routers in the same area 

The Attached bit causes the installation of an IS-IS-learned default route in the IS-IS RIB on L1 routers in the same area, as well as in the forwarding table if IS-IS is the best routing protocol from which the default route was learned – this can lead to suboptimal routing. 

```text
ignore-attached-bit
```

 

74 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 74 ใน PDF](Chapter_16ISIS-Routing.pdf#page=74)

---

## หน้า 75

### **ISP Best Practices** 

- Wait until iBGP is running before providing transit path 

```text
set-overload-bit on-startup wait-for-bgp
```

 

Avoids blackholing traffic on router restart 

Causes ISIS to announce its prefixes with highest possible metric until iBGP is up and running 

When iBGP is running, ISIS metrics return to normal, make the path valid 

- Enable the IPv6 address family for in IS-IS. 

```text
address-family ipv6
```

 

• Enable multi-topology support for IPv6 in IS-IS. Multi-topology support allows the IPv4 topology to be independent of that of IPv6 

```text
multi-topology
```

 

75 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 75 ใน PDF](Chapter_16ISIS-Routing.pdf#page=75)

---

## หน้า 76

### **ISP Best Practices** 

- Things to consider on routers operating as Level-1-only IS's: 

IS-IS BCP techniques under the IS-IS routing process In addition to the interface, tell the IS-IS routing process to operate in a Level-1 area only 

```text
router isis 1
is-type level-1
```

 

76 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 76 ใน PDF](Chapter_16ISIS-Routing.pdf#page=76)

---

## หน้า 77

### **ISP Best Practices** 

- Things to consider on routers operating as Level-1 and Level-2 IS’s: 

To prevent sub-optimal routing of traffic from L1 IS's in one area to L1 IS's in another area, configure and enable Route Leaking on L1/L2 routers that form the backbone connectivity between two or more different areas 

Route Leaking permits L1/L2 routers to install L1 routes learned from one area into L1 IS’s routing/forwarding tables in another area 

This allows for reachability between L1 routers located behind L1/L2 routers in different areas 

```text
router isis 1
redistribute isis ip level-2 into level-1 route-map FOO
!
ip prefix-list foo permit 0.0.0.0/0 le 32
!
route-map FOO permit 10
match ip address prefix-list foo
```

 

77 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 77 ใน PDF](Chapter_16ISIS-Routing.pdf#page=77)

---

## หน้า 78

### **ISP Best Practices** 

- Doing the same for IPv6: 

```text
router isis 1
address-family ipv6
redistribute isis level-2 into level-1 route-map FOO6
!
ip prefix-list foo6 permit 0.0.0.0/0 le 32
!
route-map FOO6 permit 10
match ip address prefix-list foo6
!
```

 

78 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

> หมายเหตุจากการตรวจ: แม้หัวข้อระบุ IPv6 แต่ต้นฉบับใช้ ip prefix-list กับ 0.0.0.0/0 และ match ip address; ถอดตามภาพโดยไม่เปลี่ยนเป็นคำสั่ง IPv6

[ดูภาพต้นฉบับหน้า 78 ใน PDF](Chapter_16ISIS-Routing.pdf#page=78)

---

## หน้า 79

### **ISP Best Practices** 

- Summary 
  - Best practice recommendations are commonly implemented on many ISP backbones
  - Ensures efficient and scalable operation of ISIS 

79 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 79 ใน PDF](Chapter_16ISIS-Routing.pdf#page=79)

---

## หน้า 80

#### Introduction to ISIS 

**Philip Smith pfs@cisco.com MENOG 4** 

**5th-9th April 2009 Bahrain** 

80 

MENOG 4 

© 2009 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 80 ใน PDF](Chapter_16ISIS-Routing.pdf#page=80)

---
