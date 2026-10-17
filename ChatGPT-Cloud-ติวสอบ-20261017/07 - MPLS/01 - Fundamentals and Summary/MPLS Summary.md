# MPLS Summary

> ฉบับสำหรับส่งต่อ: ใช้ข้อความจาก Markdown ที่ตรวจไว้เดิม ลิงก์ภาพเปลี่ยนเป็นการอ้างหน้าใน PDF ซึ่งแนบในโฟลเดอร์เดียวกัน โปรดเปิด PDF เมื่อต้องอ่านรูป ตาราง หรือไดอะแกรม

> ต้นฉบับ: [MPLS Summary.pdf](MPLS%20Summary.pdf)  
> จำนวน 36 หน้า — คงลำดับหน้าและภาพต้นฉบับทุกหน้า

> ข้อความที่ระบุ OCR ถอดจากภาพ; ส่วนที่อ่านไม่ชัดจะระบุไว้เพื่อเทียบกับต้นฉบับ

## หน้า 1

### Cisco MPLS

CP423211 • Internetworking

Multiprotocol Label Switching

เครือข่ายที่ส่งต่อข้อมูลด้วย Label

```text
MPLS Provider Core: PE1 — P1 — P2 — PE2
Customer — CE1 — PE1 — P1 — P2 — PE2 — CE2 — Customer
ตัวอย่าง Label: 160 → 240
```

Label-Switched Network

Transport • VPN Services • Traffic Engineering

SAINATEE BOONKWANG (Tone)

01 / 36

[ดูภาพต้นฉบับหน้า 1 ใน PDF](MPLS%20Summary.pdf#page=1)

---

## หน้า 2

### Learning Objectives

CP423211 • Internetworking

เป้าหมายการเรียนรู้ MPLS

| หัวข้อ | รายละเอียด |
| --- | --- |
| Label Forwarding | Push • Swap • Pop |
| Control Plane | IGP • LDP • MP-BGP |
| MPLS L3VPN | VRF • RD • RT |
| Lab & Troubleshooting | Configure • Verify • Diagnose |

ภาพ VRF: VPN A → A → 10.1.0.0/16; VPN B → B → 10.2.0.0/16; VPN C → C → 10.3.0.0/16

เข้าใจหลักการ ออกแบบ Lab และตรวจสอบการทำงานได้

Trace the packet. Explain the route. Verify the service.

02 / 36

[ดูภาพต้นฉบับหน้า 2 ใน PDF](MPLS%20Summary.pdf#page=2)

---

## หน้า 3

### Why MPLS?

CP423211 • Internetworking

โครงข่ายกลางเดียว รองรับบริการหลายรูปแบบ

Shared MPLS Core

| บริการ | คำอธิบาย |
| --- | --- |
| VPN Isolation | แยกเครือข่ายลูกค้า |
| Traffic Engineering | ควบคุมเส้นทางตามเงื่อนไข |
| Scalable Core | Core ไม่ต้องเก็บทุก Customer Route |
| QoS | จัดลำดับความสำคัญของ Traffic |

**MPLS VPN** แยกเครือข่าย แต่ไม่ได้เข้ารหัสข้อมูลโดยอัตโนมัติ

03 / 36

[ดูภาพต้นฉบับหน้า 3 ใน PDF](MPLS%20Summary.pdf#page=3)

---

## หน้า 4

### IP Forwarding vs MPLS Forwarding

CP423211 • Internetworking

เปรียบเทียบข้อมูลที่ใช้ตัดสินใจส่งต่อ Packet

```text
Traditional IP Forwarding:
R1 → R2 → R3
แต่ละ Router: Destination IP Lookup; packet [IP][Payload]

MPLS Forwarding:
Ingress: Classify + Push [MPLS 160][IP][Payload]
  → Label 160
Transit: Top Label Lookup [MPLS 160][IP][Payload]
  → Label 240
Egress: Service / IP Lookup [MPLS 240][IP][Payload]
```

IP: longest-prefix match

MPLS: top-label lookup

**Key Concept:** MPLS เปลี่ยนวิธี Lookup ภายใน Core; ประสิทธิภาพขึ้นกับแพลตฟอร์ม

04 / 36

[ดูภาพต้นฉบับหน้า 4 ใน PDF](MPLS%20Summary.pdf#page=4)

---

## หน้า 5

### MPLS Architecture

CP423211 • Internetworking

บทบาทของ CE, PE และ P Router

```text
Customer A Site ↔ CE1 ↔ PE1 ↔ P1 ↔ P2 ↔ PE2 ↔ CE2 ↔ Customer B Site
MPLS Provider Core: PE1, P1, P2, PE2
PE1 (VRF) ↔ MP-BGP VPNv4 ↔ PE2 (VRF)
Core IGP + LDP
```

| Router | คำอธิบาย |
| --- | --- |
| CE — Customer Edge | แลกเปลี่ยนเส้นทางกับ PE |
| PE — Provider Edge | VRF และบริการ VPN |
| P — Provider Core | ส่งต่อด้วย Transport Label |

**Key Concept:** P Router ไม่จำเป็นต้องเรียนรู้ Customer VPN Routes

05 / 36

[ดูภาพต้นฉบับหน้า 5 ใน PDF](MPLS%20Summary.pdf#page=5)

---

## หน้า 6

### LSR and LER

CP423211 • Internetworking

บทบาทของ Router ภายใน MPLS Domain

```text
IP Packet [IP]
 → MPLS Domain:
 Ingress LER — Classify + Push
 → [Label 160][IP]
 → Transit LSR — Label Lookup + Swap
 → [Label 240][IP]
 → Egress LER — Terminate LSP
 → IP Packet [IP]
```

Ingress: เพิ่ม Label

Transit: ส่งต่อตาม Label

Egress: ออกจาก LSP

**Key Concept:** บทบาท Ingress และ Egress เปลี่ยนตามทิศทางของ Traffic

06 / 36

[ดูภาพต้นฉบับหน้า 6 ใน PDF](MPLS%20Summary.pdf#page=6)

---

## หน้า 7

### MPLS Label Header

CP423211 • Internetworking

โครงสร้าง Label Stack Entry ขนาด 32 bits

32 bits = 4 bytes

| Field | ขนาด | ความหมาย |
| --- | --- | --- |
| Label | 20 bits | ค่า Label สำหรับ Forwarding |
| TC | 3 bits | Traffic Class / QoS |
| S | 1 bit | 1 = Bottom of Stack |
| TTL | 8 bits | จำกัดอายุ Packet |

```text
[Ethernet Header][MPLS Header][IP Packet]
```

**Key Concept:** TC เดิมเรียกว่า EXP และ S ใช้ระบุ Label ชั้นล่างสุด

07 / 36

[ดูภาพต้นฉบับหน้า 7 ใน PDF](MPLS%20Summary.pdf#page=7)

---

## หน้า 8

### Label Stack

CP423211 • Internetworking

Packet หนึ่งชุดสามารถมี MPLS Label ได้หลายชั้น

```text
Single Label:
[Label — S = 1]
[IP Packet]
4 bytes overhead

Two Labels: L3VPN — Top label first:
[Transport Label — S = 0] → ไปยัง Egress PE
[VPN Label — S = 1]       → ระบุ Service Forwarding
[Customer IP Packet]
8 bytes overhead
```

**Key Concept:** ประมวลผล Label ชั้นบนสุดก่อน และ S = 1 ระบุ Label ชั้นล่างสุด

08 / 36

[ดูภาพต้นฉบับหน้า 8 ใน PDF](MPLS%20Summary.pdf#page=8)

---

## หน้า 9

### MPLS Label Operations

CP423211 • Internetworking

การทำงานหลักของ Label: Push, Swap และ Pop

| Operation | Router | การทำงาน | Packet ก่อน → หลัง |
| --- | --- | --- | --- |
| PUSH | PE1 | เพิ่ม Label | IP Packet → [160][IP Packet] |
| SWAP | P1 | เปลี่ยน Label ชั้นบนสุด | [160][IP Packet] → [240][IP Packet] |
| POP | PE2 | นำ Label ชั้นบนสุดออก | [240][IP Packet] → IP Packet |

ตัวเลข Label เป็นตัวอย่าง

**Key Concept:** Pop อาจเผย Label ชั้นถัดไป หรือ IP Packet เมื่อไม่มี Label เหลือ

09 / 36

[ดูภาพต้นฉบับหน้า 9 ใน PDF](MPLS%20Summary.pdf#page=9)

---

## หน้า 10

### FEC and Label Switched Path

CP423211 • Internetworking

จัดกลุ่ม Packet และส่งต่อผ่านเส้นทาง LSP

Flow A, Flow B, Flow C → Same Transport FEC; Egress PE: 10.255.0.4/32

```text
Label Switched Path (LSP):
PE1 (Ingress) → P1 → P2 → PE2 (10.255.0.4, Egress)
Return direction = separate LSP
```

**FEC:** กลุ่ม Packet ที่ได้รับการส่งต่อแบบเดียวกัน

**LSP:** เส้นทาง Label Switching ในทิศทางเดียว

**Key Concept:** Traffic หลาย Flow ใช้ Transport LSP เดียวกันได้

10 / 36

[ดูภาพต้นฉบับหน้า 10 ใน PDF](MPLS%20Summary.pdf#page=10)

---

## หน้า 11

### Control Plane vs Data Plane

CP423211 • Internetworking

ข้อมูล Routing และ Label ร่วมกันกำหนดการส่งต่อ

```text
Control Plane              Data Plane
IGP / BGP → RIB ──────────→ FIB (IP Lookup)
              └─Selected next hop─┐
LDP       → LIB ─────────────────→ LFIB (Label Lookup)
```

| Table | ชื่อเต็ม |
| --- | --- |
| RIB | Routing Information Base |
| LIB | Label Information Base |
| FIB | Forwarding Information Base |
| LFIB | Label Forwarding Information Base |

**Key Concept:** LIB เก็บ Label Bindings ส่วน LFIB เก็บคำสั่ง Forwarding ที่ติดตั้งแล้ว

11 / 36

[ดูภาพต้นฉบับหน้า 11 ใน PDF](MPLS%20Summary.pdf#page=11)

---

## หน้า 12

### MPLS Label Distribution

CP423211 • Internetworking

Router ต้องทราบว่า Label ใดใช้กับ FEC ใด

```text
FEC: 10.255.0.4/32
P1 ← LDP Mapping: Label 240 ← P2
P1 → Traffic: [240][IP] → P2
```

P2 แจก Local Label ให้ P1 ใช้ส่ง Packet มายัง P2

| Protocol | การใช้งาน |
| --- | --- |
| LDP | IGP-based transport |
| RSVP-TE | TE tunnel |
| MP-BGP | VPN service label |
| SR-MPLS | SID-based transport |

**Key Concept:** MPLS คือ Data Plane ส่วนการแจก Label เป็นหน้าที่ของ Control Plane

12 / 36

[ดูภาพต้นฉบับหน้า 12 ใน PDF](MPLS%20Summary.pdf#page=12)

---

## หน้า 13

### LDP Fundamentals

CP423211 • Internetworking

Label Distribution Protocol สำหรับ MPLS Transport

```text
P1: LDP ID 10.255.0.2:0
P2: LDP ID 10.255.0.3:0
P1 ↔ Discovery: UDP 646 ↔ P2
P1 ↔ LDP Session: TCP 646 ↔ P2
FEC 10.255.0.4/32 → Label 240
```

LDP ID = Router ID + Label Space ID

Transport Address ต้องเข้าถึงกันได้

Cisco CLI:

```cisco
mpls ldp router-id Loopback0 force
```

**Key Concept:** ใช้ Router ID ที่เสถียร และตรวจ Reachability ของ Transport Address

13 / 36

[ดูภาพต้นฉบับหน้า 13 ใน PDF](MPLS%20Summary.pdf#page=13)

---

## หน้า 14

### LDP Neighbor and Session

CP423211 • Internetworking

ลำดับการค้นหาเพื่อนบ้านและสร้าง LDP Session

1. **Hello:** UDP 646 — พบ Neighbor
2. **TCP Session:** Transport reachability — สร้าง Session
3. **Initialization:** Negotiate parameters — สร้าง Session
4. **Keepalive:** Session operational — สร้าง Session
5. **Label Exchange:** Advertise bindings — แลกเปลี่ยน Label

Discovery ≠ Operational Session

Cisco CLI:

```cisco
show mpls ldp discovery
show mpls ldp neighbor
```

**Key Concept:** เห็น Hello Neighbor ยังไม่ยืนยันว่า LDP Session พร้อมใช้งาน

14 / 36

[ดูภาพต้นฉบับหน้า 14 ใน PDF](MPLS%20Summary.pdf#page=14)

---

## หน้า 15

### LDP Label Binding

CP423211 • Internetworking

จาก Prefix และ Label Bindings ไปสู่ LFIB

```text
FEC: 10.255.0.4/32
[160][IP] → P1 (Swap 160 → 240) → [240][IP] → P2 (Selected next hop)
```

| FEC | Local Label on P1 | Remote Label from P2 | Next Hop |
| --- | --- | --- | --- |
| 10.255.0.4/32 | 160 | 240 | P2 |

**Local Label:** P1 รับเข้า

**Remote Label:** P1 ใช้ส่งต่อไป P2

ตัวเลข Label เป็นตัวอย่าง

Cisco CLI:

```cisco
show mpls ldp bindings
```

**Key Concept:** LFIB ใช้ Label จาก Downstream Neighbor ที่ตรงกับ Next Hop

15 / 36

[ดูภาพต้นฉบับหน้า 15 ใน PDF](MPLS%20Summary.pdf#page=15)

---

## หน้า 16

### Penultimate Hop Popping (PHP)

CP423211 • Internetworking

นำ Transport Label ออกก่อนถึง Egress PE

```text
PE2 → P2: LDP Implicit Null = 3
P1 → [240][900][IP] → P2 (PHP: Pop 240 only)
P2 → [900][IP] → PE2 (Process VPN Label 900)
240 = Transport Label
900 = VPN Label
```

**Implicit Null 3:** ใช้ในการประกาศ Label เท่านั้น

**Explicit Null:** IPv4 = 0, IPv6 = 2

Label values are illustrative

**Key Concept:** PHP ลบเฉพาะ Transport Label ส่วน VPN Label ยังส่งถึง PE

16 / 36

[ดูภาพต้นฉบับหน้า 16 ใน PDF](MPLS%20Summary.pdf#page=16)

---

## หน้า 17

### Introduction to MPLS L3VPN

CP423211 • Internetworking

หลาย Customer VPN ใช้ Provider Core ร่วมกัน

```text
Shared MPLS Core: PE1 ↔ P1 ↔ P2 ↔ PE2
PE1 และ PE2: VRF A; VRF B
Customer A Site 1 ↔ VPN A ↔ PE1 ↔ Core ↔ PE2 ↔ VPN A ↔ Customer A Site 2
Customer B Site 1 ↔ VPN B ↔ PE1 ↔ Core ↔ PE2 ↔ VPN B ↔ Customer B Site 2
A connects to A; B connects to B
```

**PE:** แยก Routing และบริการ VPN

**P:** ส่งต่อ Transport Label

**Key Concept:** แยก Customer VPN ด้วย VRF, Route Policy และ Service Forwarding

17 / 36

[ดูภาพต้นฉบับหน้า 17 ใน PDF](MPLS%20Summary.pdf#page=17)

---

## หน้า 18

### VRF — Virtual Routing and Forwarding

CP423211 • Internetworking

แยก Routing Table และ Forwarding Table บน PE เดียวกัน

One Physical PE

| VRF | Prefix | Next Hop | Connection |
| --- | --- | --- | --- |
| VRF CUST-A | 10.1.1.0/24 | CE-A | CE-A ↔ Interface A ↔ PE |
| VRF CUST-B | 10.1.1.0/24 | CE-B | PE ↔ Interface B ↔ CE-B |

Same prefix • Separate forwarding contexts

```cisco
PE# show ip route vrf CUST-A
PE# show ip cef vrf CUST-A
```

**Key Concept:** Interface ที่รับ Packet กำหนด VRF สำหรับการค้นหาเส้นทาง

18 / 36

[ดูภาพต้นฉบับหน้า 18 ใน PDF](MPLS%20Summary.pdf#page=18)

---

## หน้า 19

### Why VRF Alone Is Not Enough

CP423211 • Internetworking

การแลกเปลี่ยน Route หลาย VPN ผ่าน MP-BGP ต้องแยก Identity

```text
Local VRF Separation:
VRF CUST-A: 10.1.1.0/24 → Shared MP-BGP: 10.1.1.0/24 ?
VRF CUST-B: 10.1.1.0/24 → Shared MP-BGP: 10.1.1.0/24 ?
Same IPv4 prefix → VPNv4 Route Identity
ต้องแยก Route ของแต่ละ VPN
```

VRF แยกเส้นทางภายใน PE ได้

RD ทำให้ VPNv4 Routes ไม่ซ้ำกัน

**Key Concept:** VRF ใช้แยก Context ภายในเครื่อง ส่วน RD แยก Route Identity ระหว่าง PE

19 / 36

[ดูภาพต้นฉบับหน้า 19 ใน PDF](MPLS%20Summary.pdf#page=19)

---

## หน้า 20

### Route Distinguisher (RD)

CP423211 • Internetworking

ทำให้ IPv4 Prefix ที่ซ้ำกันเป็น VPNv4 Routes ที่แตกต่างกัน

RD (8 bytes) + IPv4 address (4 bytes) → VPNv4 address (12 bytes)

| VRF | RD | IPv4 Prefix | VPNv4 Route Identity |
| --- | --- | --- | --- |
| CUST-A | 65000:101 | 10.1.1.0/24 | 65000:101:10.1.1.0/24 |
| CUST-B | 65000:102 | 10.1.1.0/24 | 65000:102:10.1.1.0/24 |

Cisco CLI:

```cisco
ip vrf CUST-A
 rd 65000:101
```

**Key Concept:** RD = Route Uniqueness ส่วน RT = Import / Export Policy

20 / 36

[ดูภาพต้นฉบับหน้า 20 ใน PDF](MPLS%20Summary.pdf#page=20)

---

## หน้า 21

### Route Target (RT)

CP423211 • Internetworking

กำหนดการ Import และ Export Route ของแต่ละ VPN

```text
PE1 (VRF CUST-A)
 → Export RT 65000:100
 → VPNv4 Route: RT 65000:100 (BGP Extended Community)
 → Import RT 65000:100
 → PE2 (VRF CUST-A): RT Match → Import
```

```cisco
PE1(config-vrf)# route-target export 65000:100
PE1(config-vrf)# route-target import 65000:100
```

**Key Concept:** RT ใช้ควบคุม VPN Membership และ Route Import / Export

21 / 36

[ดูภาพต้นฉบับหน้า 21 ใน PDF](MPLS%20Summary.pdf#page=21)

---

## หน้า 22

### RD vs RT

CP423211 • Internetworking

แยก Route Identity ออกจาก VPN Membership

| RD — Route Distinguisher | RT — Route Target |
| --- | --- |
| Route Uniqueness | Import / Export Policy |
| 1. Part of VPNv4 NLRI | 1. BGP Extended Community |
| 2. ทำให้ Prefix ที่ซ้ำกันแยกจากกัน | 2. กำหนดว่า VRF ใดรับ Route |
| 3. Example: 65000:101 | 3. Example: 65000:100 |

PE1 (RD 65000:101) ↔ Shared RT 65000:100 ↔ PE2 (RD 65000:201)

**Key Concept:** RD ต่างกันได้ แต่ VRF แลก Route กันได้เมื่อ RT Policy ตรงกัน

22 / 36

[ดูภาพต้นฉบับหน้า 22 ใน PDF](MPLS%20Summary.pdf#page=22)

---

## หน้า 23

### MP-BGP and VPNv4

CP423211 • Internetworking

PE แลกเปลี่ยน VPN Routes ผ่าน MP-BGP

```text
MPLS Provider Core: PE1 ↔ P1 ↔ P2 ↔ PE2
PE1: 10.255.0.1, AS 65000
PE2: 10.255.0.4, AS 65000
PE1 ↔ MP-BGP VPNv4 (AFI 1 • SAFI 128) ↔ PE2
```

VPNv4 Route Advertisement (from PE1 to PE2):

| VPNv4 Prefix | RT | VPN Label | BGP Next Hop |
| --- | --- | --- | --- |
| 10.1.1.0/24 | 65000:100 | 10101 | 10.255.0.1 |

Cisco CLI (on PE1):

```cisco
address-family vpnv4
 neighbor 10.255.0.4 send-community extended
```

**Key Concept:** BGP Next Hop ต้องเข้าถึงได้ และมี Transport LSP ไปยัง Remote PE

23 / 36

[ดูภาพต้นฉบับหน้า 23 ใน PDF](MPLS%20Summary.pdf#page=23)

---

## หน้า 24

### MPLS VPN Control Plane

CP423211 • Internetworking

ตัวอย่าง: PE2 ประกาศ Route ของ Site B ไปยัง PE1

1. **CE2:** 192.168.20.0/24 — Customer B Site B
2. **PE2 VRF:** Learn route — VRF
3. **VPNv4:** RD + Prefix — VPNv4 Route
4. **MP-BGP:** RT + VPN Label — Route Advertisement: RD + Prefix, RT (Route Target), VPN Label, Next Hop
5. **PE1 VRF:** RT Import — VRF → Customer A Site A

Route Advertised by PE2 (VPNv4):

| RD | RT | VPN Label | Next Hop |
| --- | --- | --- | --- |
| 65000:201 | 65000:100 | 900 | 10.255.0.4 |

Data traffic to Site B: PE1 → PE2

**Key Concept:** Control Plane สร้าง Route และ Label State ก่อนส่ง Customer Traffic

24 / 36

[ดูภาพต้นฉบับหน้า 24 ใน PDF](MPLS%20Summary.pdf#page=24)

---

## หน้า 25

### MPLS VPN Data Plane

CP423211 • Internetworking

Two-Label Stack เชื่อม Transport กับบริการ VPN

Top label processed first

| Packet layer | รายละเอียด | การส่งต่อ |
| --- | --- | --- |
| Transport Label | Outer • S = 0 | ผ่าน Core ไปยัง Egress PE |
| VPN Label 900 | Inner • S = 1 | PE (Egress), VRF — Service Forwarding ที่ Egress PE |
| Customer IP Packet | Destination: 192.168.20.1 | Customer destination |

VPN Label อาจผูกกับ Prefix, Next Hop หรือ VRF ตาม Allocation Mode

**Key Concept:** Outer Label พาไปหา PE ส่วน Inner Label กำหนด Service Forwarding

25 / 36

[ดูภาพต้นฉบับหน้า 25 ใน PDF](MPLS%20Summary.pdf#page=25)

---

## หน้า 26

### End-to-End MPLS L3VPN Packet Walk

CP423211 • Internetworking

Customer A: Site A ส่ง Packet ไปยัง Site B

```text
Customer A Site A → CE1 → PE1 → P1 → P2 → PE2 → CE2 → Customer A Site B
MPLS Provider Core: PE1, P1, P2, PE2
CE1 → PE1: [IP]
PE1: Push 160 + 900 → [160][900][IP]
P1: Swap 160 → 240 → [240][900][IP]
P2: PHP: Pop 240 → [900][IP]
PE2: Process VPN 900 → CE2: [IP]
```

Destination: 192.168.20.1

Label values are illustrative

**Key Concept:** Transport Label เปลี่ยนตาม Hop แต่ VPN Label ส่งถึง Egress PE

26 / 36

[ดูภาพต้นฉบับหน้า 26 ใน PDF](MPLS%20Summary.pdf#page=26)

---

## หน้า 27

### PE–CE Routing Options

CP423211 • Internetworking

PE เรียนรู้ Customer Routes ภายใน VRF

Customer → CE ↔ Customer routing ↔ PE → VRF CUST-A

| Protocol | ลักษณะ | สิ่งที่ตรวจ |
| --- | --- | --- |
| Static | Small, stable sites | ตรวจ Next Hop และ Return Route |
| OSPF | Customer IGP | ตรวจ Domain ID และ Loop Prevention |
| EIGRP | EIGRP-based sites | ตรวจ Metric และ Redistribution |
| eBGP | Routing-policy boundary | ตรวจ AS Path และ Prefix Filters |

**Key Concept:** เลือก PE–CE Protocol ให้เหมาะกับลูกค้า และกำหนด Route Policy ชัดเจน

27 / 36

[ดูภาพต้นฉบับหน้า 27 ใน PDF](MPLS%20Summary.pdf#page=27)

---

## หน้า 28

### MPLS Layer 2 VPN Overview

CP423211 • Internetworking

บริการ Ethernet ผ่าน MPLS Provider Network

| บริการ | Topology / Control Plane | รายละเอียด |
| --- | --- | --- |
| VPWS / Pseudowire | Customer Site A ↔ MPLS Provider Network ↔ Customer Site B | Point-to-Point |
| VPLS | Customer Site A, Site B, Site C เชื่อม MPLS Provider Network | Multipoint Ethernet; MAC Learning |
| EVPN over MPLS | PE1 (MAC) ↔ BGP Control Plane ↔ PE2 (MAC) | BGP Control Plane; MAC Reachability |

**L2VPN:** Ethernet Service

**L3VPN:** IP Routing Service

**Key Concept:** EVPN คือ Control Plane และ MPLS เป็นหนึ่งใน Data Plane ที่ใช้ได้

28 / 36

[ดูภาพต้นฉบับหน้า 28 ใน PDF](MPLS%20Summary.pdf#page=28)

---

## หน้า 29

### MPLS QoS

CP423211 • Internetworking

Traffic Class และแนวคิด QoS Tunnel Models

MPLS Header: Label, TC, S, TTL

TC: 3 bits • Values 0–7

Classification • Marking • Queueing

| Model | Customer Marking | Egress Treatment |
| --- | --- | --- |
| Uniform | อาจสะท้อน Provider Remarking | Propagated marking |
| Pipe | เก็บแยกจาก Provider | Provider tunnel class |
| Short Pipe | เก็บแยกจาก Provider | Customer packet marking |

TC เดิมเรียกว่า EXP

**Key Concept:** TC Marking ต้องทำงานร่วมกับ Queueing และ Congestion Policy

29 / 36

[ดูภาพต้นฉบับหน้า 29 ใน PDF](MPLS%20Summary.pdf#page=29)

---

## หน้า 30

### MPLS Traffic Engineering — RSVP-TE

CP423211 • Internetworking

สร้าง LSP ตามเงื่อนไขและความต้องการของ Traffic

```text
CSPF → Headend
IGP shortest path: Headend — P1 — Tailend
Selected TE path: Headend → P2 → Tailend
Headend → PATH → Tailend
Headend ← RESV ← Tailend
```

Explicit path • Bandwidth reservation • LSP state

Reservation ≠ Traffic Shaping

**Key Concept:** CSPF เลือกเส้นทาง ส่วน RSVP-TE ใช้ Signaling เพื่อสร้างและรักษา LSP

30 / 36

[ดูภาพต้นฉบับหน้า 30 ใน PDF](MPLS%20Summary.pdf#page=30)

---

## หน้า 31

### Evolution to SR-MPLS

CP423211 • Internetworking

พัฒนาการของ MPLS Transport

| Evolution | ลักษณะ |
| --- | --- |
| LDP | Labels follow IGP |
| RSVP-TE | Signaled TE tunnels |
| SR-MPLS | Segment list at ingress |

```text
Ingress → [SID1][SID2][SID3][Payload] → Egress
IGP advertises SIDs • MPLS forwards packets
```

**L3VPN service:** MP-BGP + VRF

**Key Concept:** SR-MPLS เปลี่ยนวิธีควบคุม Transport โดยยังใช้ MPLS Labels

31 / 36

[ดูภาพต้นฉบับหน้า 31 ใน PDF](MPLS%20Summary.pdf#page=31)

---

## หน้า 32

### SR-MPLS Concepts

CP423211 • Internetworking

กำหนดเส้นทางด้วย Segment Identifier

| Concept | คำอธิบาย |
| --- | --- |
| Prefix / Node SID | ไปยัง Prefix หรือ Node |
| Adjacency SID | ผ่านลิงก์ที่กำหนด |
| SRGB | ช่วง Label สำหรับ Global SID |

```text
Ingress builds the segment list:
[Active segment]
[Next segment]
[Payload]
```

Node SID เป็นรูปแบบหนึ่งของ Prefix SID

**Key Concept:** Segment list กำหนดลำดับคำสั่งส่งต่อแพ็กเก็ต

32 / 36

[ดูภาพต้นฉบับหน้า 32 ใน PDF](MPLS%20Summary.pdf#page=32)

---

## หน้า 33

### MPLS Troubleshooting

CP423211 • Internetworking

ตรวจสอบทีละชั้น จาก Underlay ถึง VPN

1. **Underlay:** Interfaces, MTU, IGP reachability
2. **Transport:** LDP neighbors, Labels, LFIB — MPLS
3. **VPN Control Plane:** MP-BGP, RD / RT, VRF routes — BGP
4. **Data Plane:** VRF ping, Traceroute, Return path — VPN

**แยกปัญหา:** ไม่มี Route หรือมี Route แต่ส่งข้อมูลไม่ได้

**Key Concept:** ยืนยัน Underlay และ Label Transport ก่อนตรวจสอบ VPN

33 / 36

[ดูภาพต้นฉบับหน้า 33 ใน PDF](MPLS%20Summary.pdf#page=33)

---

## หน้า 34

### Cisco Verification Commands

CP423211 • Internetworking

คำสั่งหลักสำหรับตรวจสอบ MPLS L3VPN

**CORE / TRANSPORT**

```cisco
> show ip route
> show mpls interfaces
> show mpls ldp neighbor
> show mpls forwarding-table
```

**PE / VPN**

```cisco
> show ip vrf
> show ip route vrf CUST_A
> show ip bgp vpnv4 all summary
> ping vrf CUST_A 192.168.20.1
```

ตัวอย่าง Cisco IOS / IOS XE — Syntax อาจต่างตามรุ่น

**Key Concept:** ตรวจสอบ Route, Label และ Reachability ให้ครบทั้งสองทิศทาง

34 / 36

[ดูภาพต้นฉบับหน้า 34 ใน PDF](MPLS%20Summary.pdf#page=34)

---

## หน้า 35

### CCNP MPLS Lab

CP423211 • Internetworking

ฝึกสร้างและตรวจสอบ L3VPN แบบ End-to-End

```text
Site A ↔ CE1 ↔ PE1 ↔ P1 ↔ P2 ↔ PE2 ↔ CE2 ↔ Site B
Provider AS 65000: PE1, P1, P2, PE2
```

1. **Build Underlay:** OSPF + LDP
2. **Enable VPN:** VRF CUST_A + MP-BGP
3. **Verify Service:** Routes + Labels + Ping

RT 65000:100 • Site A: 192.168.10.0/24 • Site B: 192.168.20.0/24

**Key Concept:** เป้าหมาย: Site A สื่อสารกับ Site B ผ่าน MPLS L3VPN

35 / 36

[ดูภาพต้นฉบับหน้า 35 ใน PDF](MPLS%20Summary.pdf#page=35)

---

## หน้า 36

### Key Takeaways

CP423211 • Internetworking

สรุปแนวคิดสำคัญของ MPLS

| Concept | รายละเอียด |
| --- | --- |
| Label Forwarding — MPLS | Push • Swap • Pop |
| Transport | IGP + LDP หรือ SR-MPLS |
| VRF | แยก Routing Table ของลูกค้า |
| RD & RT | RD: Route uniqueness; RT: Import / Export policy |
| L3VPN | Transport Label + VPN Label |
| Troubleshooting | Underlay → Transport → VPN |

**Key Concept:** เข้าใจ Control Plane และ Data Plane เพื่อออกแบบและแก้ปัญหา MPLS

36 / 36

[ดูภาพต้นฉบับหน้า 36 ใน PDF](MPLS%20Summary.pdf#page=36)

---
