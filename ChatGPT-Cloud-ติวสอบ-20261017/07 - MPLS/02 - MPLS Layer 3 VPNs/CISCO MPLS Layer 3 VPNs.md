# CISCO MPLS Layer 3 VPNs

> ฉบับสำหรับส่งต่อ: ใช้ข้อความจาก Markdown ที่ตรวจไว้เดิม ลิงก์ภาพเปลี่ยนเป็นการอ้างหน้าใน PDF ซึ่งแนบในโฟลเดอร์เดียวกัน โปรดเปิด PDF เมื่อต้องอ่านรูป ตาราง หรือไดอะแกรม

> ต้นฉบับ: [CISCO MPLS Layer 3 VPNs.pdf](CISCO%20MPLS%20Layer%203%20VPNs.pdf)  
> จำนวน 182 หน้า — คงลำดับหน้าและภาพต้นฉบับทุกหน้า

> ข้อความที่ระบุ OCR ถอดจากภาพ; ส่วนที่อ่านไม่ชัดจะระบุไว้เพื่อเทียบกับต้นฉบับ

## หน้า 1

###### MPLS Layer 3 VPNs 

Cisco Confidential 

Presentation_ID 

© 2010 Cisco Systems, Inc. All rights reserved.

[ดูภาพต้นฉบับหน้า 1 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=1)

---

## หน้า 2

###### Agenda 

**2** 

© 2010 Cisco Systems, Inc. All rights reserved. 

Cisco Confidential 

JMB

[ดูภาพต้นฉบับหน้า 2 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=2)

---

## หน้า 3

#### Agenda 

- MPLS L3VPNs 

- Traceroute in an MPLS VPN 

- PE-CE Routing Protocols 

   - Static 

   - RIPv2 

   - BGP 

   - OSPF 

   - EIGRP 

   - Deployment Scenario with BGP 

   - Deployment Scenario with OSPF 

   - Deployment Scenario with EIGRP 

- 6vPE

[ดูภาพต้นฉบับหน้า 3 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=3)

---

## หน้า 4

#### MPLS Layer 3 VPNs 

**4** 

© 2010 Cisco Systems, Inc. All rights reserved. Cisco Confidential 

JMB

[ดูภาพต้นฉบับหน้า 4 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=4)

---

## หน้า 5

###### Driving Forces for MPLS L3-VPNs 

- Low cost and scalable WAN to replace traditional Layer 2 Technologies (ATM/FR) 

- Separate networks for security, policy and economic/political reasons - Segmentation 

- Not a Core Business activity and expectation of cost savings 

   - No need to invest in high cost equipment 

   - Pay as you go model 

   - Reduce the cost of maintaining high cost and skilled IT staff

[ดูภาพต้นฉบับหน้า 5 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=5)

---

## หน้า 6

###### Driving Forces for MPLS L3-VPNs 

- Other factors include: 

   - Limited Geographic reach (cost) 

   - Reluctance to share the routing info 

   - Limited flexibility 

- Larger enterprises with disparate business entities and economies of scale approaching that of a Tier 2 or Tier 3 ISP 

- Bandwidth, performance, or other requirements that cannot be met by public service provider networks 

- Business mandates on separation, segmentation and Virtualization of Traffic

[ดูภาพต้นฉบับหน้า 6 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=6)

---

## หน้า 7

#### Terminology 

- LSR: label switch router 

- LSP: label switched path 

   - The chain of labels that are swapped at each hop to get from one LSR to another 

- VRF: VPN routing and forwarding 

   - Mechanism in Cisco IOS<sup>®</sup> used to build per-customer RIB and FIB 

- MP-BGP: multiprotocol BGP 

- PE: provider edge router interfaces with CE routers 

- P: provider (core) router, without knowledge of VPN 

- VPNv4: address family used in BGP to carry MPLS-VPN routes 

- RD: route distinguisher 

   - Distinguish same network/mask prefix in different VRFs 

- RT: route target 

   - Extended community attribute used to control import and export policies of VPN routes 

- LFIB: label forwarding information base 

- FIB: forwarding information base

[ดูภาพต้นฉบับหน้า 7 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=7)

---

## หน้า 8

#### MPLS VPN Architecture 

- An MPLS VPN combines the best features of an overlay VPN and a peer-to-peer VPN: 

   - PE routers participate in customer routing, guaranteeing optimum routing between sites and easy provisioning. 

   - PE routers carry a separate set of routes for each customer (similar to the dedicated PE router approach). 

   - Customers can use overlapping addresses.

[ดูภาพต้นฉบับหน้า 8 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=8)

---

## หน้า 9

MPLS VPN Architecture (Cont.) Terminology

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
P-Network: PE Router POP-X — P Router — PE Router POP-Y
POP-X connects Customer A Site #1 (Site #1 CE Router plus two Remote Office routers), Customer A Site #2, Customer A Site #3, Customer B Site #1.
POP-Y connects Customer A Site #4, Customer B Site #2, Customer B Site #3, Customer B Site #4.
```

[ดูภาพต้นฉบับหน้า 9 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=9)

---

## หน้า 10

PE Router Architecture

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
PE Router:
Customer A Site #1, Site #2, Site #3 → Virtual Router for Customer A → Virtual IP Routing Table for Customer A
Customer B Site #1 → Virtual Router for Customer B → Virtual IP Routing Table for Customer B
Global IP Routing Table → P Router
The upper-right box is titled: Virtual Router for Customer A
MPLS VPN architecture is very similar to the dedicated PE router peer-to-peer model, but the dedicated per-customer routers are implemented as virtual routing tables within the PE router.
```

> หมายเหตุจากการตรวจ: กรอบ Global IP Routing Table ในภาพมีหัวข้อ Virtual Router for Customer A ตามต้นฉบับ

[ดูภาพต้นฉบับหน้า 10 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=10)

---

## หน้า 11

###### Propagation of Routing Information Across the P-Network 



Question:   How will PE routers exchange customer routing information? Answer #1: Run a dedicated Interior Gateway Protocol (IGP) for each customer across the P-network. 

This is the wrong answer for the following reasons: 

- The solution does not scale. 

- P routers carry all customer routes.

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
P-Network: PE Router X — P Router — PE Router Y
Left: Customer A, Customer B, Customer C → PE Router X
Right: PE Router Y → Customer B, Customer C, Customer A
IGP for Customer A, IGP for Customer B, IGP for Customer C: separate IGPs over each PE–P link
```

[ดูภาพต้นฉบับหน้า 11 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=11)

---

## หน้า 12

Propagation of Routing Information Across the P-Network (Cont.) 



Question:   How will PE routers exchange customer routing information? Answer #2: Run a single routing protocol that will carry all customer routes inside the provider backbone. Better answer, but still not good enough: 

- P routers carry all customer routes.

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
P-Network: PE Router X — P Router — PE Router Y
Left: Customer A, Customer B, Customer C → PE Router X
Right: PE Router Y → Customer B, Customer C, Customer A
A dedicated routing protocol used to carry customer routes
```

[ดูภาพต้นฉบับหน้า 12 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=12)

---

## หน้า 13

###### Propagation of Routing Information Across the P-Network (Cont.) 



Question:   How will PE routers exchange customer routing information? Answer #3: Run a single routing protocol that will carry all customer routes between PE routers. Use MPLS labels to exchange packets between PE routers. The best answer: 

- P routers do not carry customer routes; the solution is scalable.

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
P-Network: PE Router X — P Router — PE Router Y
Left: Customer A, Customer B, Customer C → PE Router X
Right: PE Router Y → Customer B, Customer C, Customer A
A dedicated routing protocol used to carry customer routes between PE routers
```

[ดูภาพต้นฉบับหน้า 13 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=13)

---

## หน้า 14

Propagation Routing Information Across the P-Network (Cont.) 



**Question:** Which protocol can be used to carry customer routes between PE routers?

**Answer:** The number of customer routes can be very large. BGP is the only routing protocol that can scale to a very large number of routes.

Conclusion: 

BGP is used to exchange customer routes directly between PE routers.

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
P-Network: PE Router X — P Router — PE Router Y
Left: Customer A, Customer B, Customer C → PE Router X
Right: PE Router Y → Customer B, Customer C, Customer A
A dedicated routing protocol used to carry customer routes between PE routers
```

[ดูภาพต้นฉบับหน้า 14 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=14)

---

## หน้า 15

Propagation of Routing Information Across the P-Network (Cont.) 



**Question:** How will information about the overlapping subnets of two customers be propagated via a single routing protocol?

**Answer:** Extend the customer addresses to make them unique.

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
P-Network: PE Router X — P Router — PE Router Y
Left: Customer A, Customer B, Customer C → PE Router X
Right: PE Router Y → Customer B, Customer C, Customer A
A dedicated routing protocol used to carry customer routes between PE routers
```

[ดูภาพต้นฉบับหน้า 15 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=15)

---

## หน้า 16

### Route Distinguishers

VPNv4 Address — 12 Bytes:

| RD | IPv4 |
| --- | --- |
| 100:1 | 10.10.10.0 |

RD + IPv4

- The 64-bit route distinguisher (RD) is prepended to an IPv4 address to make it globally unique.
- The resulting address is a VPNv4 address.
- VPNv4 addresses are exchanged between PE routers via BGP.
- BGP that supports address families other than IPv4 addresses is called Multiprotocol BGP (MP-BGP).

[ดูภาพต้นฉบับหน้า 16 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=16)

---

## หน้า 17

### Route Distinguishers (Cont.)

#### Route Distinguisher Format

| ส่วนที่ 1 | ส่วนที่ 2 |
| --- | --- |
| Autonomous System | VPN Identifier |
| IP Address | VPN Identifier |

8 Bytes

Service Providers can use their BGP AS along with VPN customer identifier

Service Provider who do not have BGP AS, can use an IP address

[ดูภาพต้นฉบับหน้า 17 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=17)

---

## หน้า 18

### Route Distinguishers (Cont.)

VPNv4 Addresses — MP-iBGP update:

| RD | IPv4 |
| --- | --- |
| 100:2 | 10.10.10.0 |
| 100:1 | 10.10.10.0 |

Customer A has RD of 100:1

Customer B has RD of 100:2

Route Distinguisher keeps Customer A’s update unique from Customer B in the MP-iBGP update, although they use the same IP address

[ดูภาพต้นฉบับหน้า 18 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=18)

---

## หน้า 19

Route Distinguishers (Cont.)

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
P-Network: PE-1 → PE-2; Customer A and Customer B connected at both edges.
Customer B CE → PE-1: The CE router sends an IPv4 routing update to the PE router.
PE-1: A 64-bit RD is prepended to the customer IPv4 prefix to make it globally unique, resulting in a 96-bit VPNv4 prefix.
PE-1 → PE-2: A 96-bit VPNv4 prefix is propagated via MP-BGP to the other PE router.
```

[ดูภาพต้นฉบับหน้า 19 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=19)

---

## หน้า 20

Route Distinguishers (Cont.)

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
P-Network: PE-1 → PE-2; Customer A and Customer B connected at both edges.
PE-2: The RD is removed from the VPNv4 prefix, resulting in a 32-bit IPv4 prefix.
PE-2 → Customer B CE: The PE router sends the resulting IPv4 prefix to the CE router.
```

[ดูภาพต้นฉบับหน้า 20 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=20)

---

## หน้า 21

Route Distinguishers (Cont.) Usage in an MPLS VPN 

- The RD has no special meaning. 

- Used only to make potentially overlapping IPv4 addresses globally unique. 

- The RD could serve as a VPN identifier, but this design could not support all topologies required by the customers.

[ดูภาพต้นฉบับหน้า 21 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=21)

---

## หน้า 22

Route Targets Why Are They Needed? 

- Some sites have to participate in more than one VPN. 

- The RD cannot identify participation in more than one VPN. 

- RTs were introduced in the MPLS VPN architecture to support complex VPN topologies. 

   - A different method is needed in which a set of identifiers can be attached to a route.

[ดูภาพต้นฉบับหน้า 22 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=22)

---

## หน้า 23

###### Route Targets (Cont.) What Are They? 

```text
MP-iBGP update:
VPNv4 update: [RD 100:2][IPv4 10.10.10.0]
Route-Targets: [Customer B: 2][VoIP VPN: 2]
``` 

MP-iBGP update 

- RTs are additional attributes attached to VPNv4 BGP routes to indicate VPN membership. 

- Format is same as Route Distinguisher 

- Extended BGP communities are used to encode these attributes. 

   - Extended communities carry the meaning of the attribute together with its value. 

- Any number of RTs can be attached to a single route.

[ดูภาพต้นฉบับหน้า 23 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=23)

---

## หน้า 24

Route Targets (Cont.) How Do They Work? 

- Export RTs: 

   - Identifying VPN membership 

   - Appended to the customer route when it is converted into a VPNv4 route 

- Import RTs: 

   - Associated with each virtual routing table 

   - Select routes to be inserted into the virtual routing table

[ดูภาพต้นฉบับหน้า 24 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=24)

---

## หน้า 25

#### Virtual Private Networks Redefined 

- With the introduction of complex VPN topologies, VPNs have had to be redefined: 

   - A VPN is a collection of sites sharing common routing information. 

   - A site can be part of different VPNs. 

   - A VPN can be seen as a community of interest (closed user group, or CUG). 

   - Complex VPN topologies are supported by multiple virtual routing tables on the PE routers.

[ดูภาพต้นฉบับหน้า 25 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=25)

---

## หน้า 26

###### Impact of Complex VPN Topologies on Virtual Routing Tables 

- A virtual routing table in a PE router can be used only for sites with identical connectivity requirements. 

- Complex VPN topologies require more than one virtual routing table per VPN. 

- As each virtual routing table requires a distinct RD value, the number of RDs in the MPLS VPN network increases.

[ดูภาพต้นฉบับหน้า 26 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=26)

---

## หน้า 27

###### Important points to note for RT and RD 

- Route Distinguishers (RD) are only used to make ipv4 VPN addresses unique when advertising them over MP-iBGP, by making them vpnv4 prefixes 

- We can have one RD per vrf 

- Only one vrf can be assigned to an interface 

- Route Targets (RT) are used for VPN membership, so that complex scenarios can be addressed 

- VPN is the set of rules for customer connectivity and can be very complex 

- A VPN may have several RTs

[ดูภาพต้นฉบับหน้า 27 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=27)

---

## หน้า 28

#### MP-BGP Extensions 

- BGP has been extended in the form in Multi-protocol (MP)-BGP to carry routes from multiple “address families” in the form of VPNv4-AF 

- VPNv4-AF is a 12-byte field of the form: 

   - Route-Distinguisher [RD] 8-byte 

   - IPv4-Address 4-byte 

- Route-Target Attribute 

- Label value 


MP-IBGP update with RD, RT, and label:

| Field | Value | Size |
| --- | --- | --- |
| RD | 1:1 | 8 Bytes |
| IPv4 | 10.1.1.0 | 4 Bytes |
| Route-Target | 2:2 | 8 Bytes |
| Label | 50 | 3 Bytes |

VPNv4 = RD + IPv4

[ดูภาพต้นฉบับหน้า 28 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=28)

---

## หน้า 29

#### MP-BGP Extensions 

```
PE11#show ip bgp vpnv4 vrf BGP-PE-CE 1.1.1.1
BGP routing table entry for 11:1:1.1.1.1/32, version 2
Paths: (1 available, best #1, table BGP-PE-CE)
  Advertised to update-groups:
     2
  1
    140.0.0.1 (via BGP-PE-CE) from 140.0.0.1 (1.1.1.1)
      Origin IGP, metric 0, localpref 100, valid, external, best
      Extended Community: RT:1:1
      mpls labels in/out 35/nolabel
```



Route Target for Coloring of the Prefixes 

VRF Table 

VPNv4-Address: RD 11:1; IP Address 1.1.1.1/32

[ดูภาพต้นฉบับหน้า 29 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=29)

---

## หน้า 30

#### MPLS VPN Routing Requirements 

- CE routers have to run standard IP routing software. 

- PE routers have to support MPLS VPN services and Internet routing. 

- P routers have no VPN routes.

[ดูภาพต้นฉบับหน้า 30 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=30)

---

## หน้า 31

###### MPLS VPN Routing CE Router Perspective 



- The CE routers run standard IP routing software and exchange routing updates with the PE router. 

   - PE-CE protocols can be EBGP, OSPF, RIPv2, EIGRP, and static routes. 

- The PE router appears as another router in the C-network.

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
Two CE Routers ↔ PE Router in MPLS VPN Backbone
```

[ดูภาพต้นฉบับหน้า 31 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=31)

---

## หน้า 32

###### MPLS VPN Routing (cont.) Overall Customer Perspective 



- To the customer, the PE routers appear as core routers connected via a BGP backbone. 

- The usual BGP and IGP design rules apply. 

- The P routers are hidden from the customer.

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
BGP Backbone connects two PE Routers.
Left PE Router: site containing CE Router and Site IGP.
Right PE Router: two separate Site IGP boxes.
```

[ดูภาพต้นฉบับหน้า 32 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=32)

---

## หน้า 33

###### MPLS VPN Routing (Cont.) P Router Perspective 



- P routers do not participate in MPLS VPN routing and do not carry VPN routes. 

- P routers run backbone IGP with the PE routers and exchange information about global subnets (core links and loopbacks).

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
MPLS VPN Backbone: PE Router — P Router — PE Router; two CE Routers connect to each PE edge.
```

[ดูภาพต้นฉบับหน้า 33 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=33)

---

## หน้า 34

MPLS VPN Routing (Cont.) PE Router Perspective 



###### PE routers: 

- Exchange VPN routes with CE routers via per-VPN routing protocols 

- Exchange core routes with P routers and PE routers via core IGP 

- Exchange VPNv4 routes with other PE routers via MP-IBGP sessions

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
MPLS VPN Backbone: PE Router — P Router — PE Router; two CE Routers connect to each PE edge.
CE ↔ PE: VPN Routing (each edge)
PE ↔ P ↔ PE: Core IGP (each core link)
PE ↔ PE: MP-IBGP
```

[ดูภาพต้นฉบับหน้า 34 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=34)

---

## หน้า 35

#### Support for Existing Internet Routing 



- PE routers can run standard IPv4 BGP in the global routing table: 

   - PE routers exchange Internet routes with other PE routers. 

   - CE routers do not participate in Internet routing. 

   - P routers do not need to participate in Internet routing.

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
MPLS VPN Backbone: PE Router — P Router — PE Router; two CE Routers connect to each PE edge.
PE ↔ PE: IPv4 BGP for Internet
PE ↔ P ↔ PE: Core IGP
```

[ดูภาพต้นฉบับหน้า 35 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=35)

---

## หน้า 36

#### Routing Tables on PE Routers 



- PE routers contain a number of routing tables: 

   - Global routing table, which contains core routes (filled with core IGP) and Internet routes (filled with IPv4 BGP) 

   - VRF tables for sets of sites with identical routing requirements 

   - VRFs filled with information from CE routers and MP-BGP information from other PE routers

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
MPLS VPN Backbone: PE Router — P Router — PE Router; two CE Routers connect to each PE edge.
CE ↔ PE: VPN Routing (each edge)
PE ↔ PE: MP-BGP; IPv4 BGP for Internet
PE ↔ P ↔ PE: Core IGP
```

[ดูภาพต้นฉบับหน้า 36 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=36)

---

## หน้า 37

#### End-to-End Routing Update Flow 



- PE routers receive IPv4 routing updates from CE routers and install them in the appropriate VRF table.

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
MPLS VPN Backbone: PE Router — P Router — PE Router; two CE Routers connect to each PE edge.
IPv4 Update: left CE → left PE
```

[ดูภาพต้นฉบับหน้า 37 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=37)

---

## หน้า 38

###### End-to-End Routing Update Flow (Cont.) 



- PE routers export VPN routes from VRF tables into MP-BGP and propagate them as VPNv4 routes to other PE routers.

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
MPLS VPN Backbone: PE Router — P Router — PE Router; two CE Routers connect to each PE edge.
IPv4 Update: left CE → left PE
MP-BGP Update: left PE → right PE
```

[ดูภาพต้นฉบับหน้า 38 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=38)

---

## หน้า 39

##### End-to-End Routing Update Flow (Cont.) MP-BGP Update 

- An MP-BGP update contains the following: 

   - VPNv4 address 

   - Extended communities (route targets, optionally SOO) 

   - Label used for VPN packet forwarding 

   - Any other BGP attribute (for example, AS path, local preference, MED, standard community)

[ดูภาพต้นฉบับหน้า 39 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=39)

---

## หน้า 40

###### End-to-End Routing Update Flow (Cont.) 



- Receiving PE router imports incoming VPNv4 routes into the appropriate VRF based on route targets attached to the routes. 

- Routes installed in VRF are propagated to CE routers.

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
MPLS VPN Backbone: PE Router — P Router — PE Router; two CE Routers connect to each PE edge.
MP-BGP Update: left PE → right PE
Update arrows also shown from left CE into left PE, and from right PE toward right CE.
```

[ดูภาพต้นฉบับหน้า 40 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=40)

---

## หน้า 41

###### VPN Packet Forwarding Across an MPLS VPN Backbone 



Question: How will the PE routers forward the VPN packets across the MPLS VPN backbone? Answer #1: They will label the VPN packets with an LDP label for the egress PE router and forward the labeled packets across the MPLS backbone.

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
MPLS VPN Backbone: Ingress PE Router — P Router — P Router — Egress PE Router; two CE Routers connect to each edge.
```

[ดูภาพต้นฉบับหน้า 41 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=41)

---

## หน้า 42

###### VPN Packet Forwarding Across an MPLS VPN Backbone 



Question: How will the PE routers forward the VPN packets across the MPLS VPN backbone? 

Answer #1: They will label the VPN packets with an LDP label for the egress PE router and forward the labeled packets across the MPLS backbone. 

Results: 

- The P routers perform the label switching, and the packet reaches the egress PE router. 

- However, the egress PE router does not know which VRF to use for packet switching, so the packet is dropped. 

- How about using a label stack?

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
MPLS VPN Backbone: Ingress PE Router — P Router — P Router — Egress PE Router; two CE Routers connect to each edge.
Diagram packet boxes left-to-right: [IP] → [IP][L1] → [IP][L2] → [IP][L3]
Question mark at Egress PE Router (unknown VRF).
```

[ดูภาพต้นฉบับหน้า 42 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=42)

---

## หน้า 43

VPN Packet Forwarding Across an MPLS VPN Backbone (Cont.) 



**Question:** How will the PE routers forward the VPN packets across the MPLS VPN backbone?

**Answer #2:** They will label the VPN packets with a label stack, using the LDP label for the egress PE router as the top label, and the VPN label assigned by the egress PE router as the second label in the stack.

Result: 

- The P routers perform label switching, and the packet reaches the egress PE router. 

- The egress PE router performs a lookup on the VPN label and forwards the packet toward the CE router.

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
MPLS VPN Backbone: Ingress PE Router — P Router — P Router — Egress PE Router; two CE Routers connect to each edge.
Diagram packet boxes left-to-right: [IP] → [IP][V][L1] → [IP][V][L2] → [IP][V][L3] → [IP]
```

[ดูภาพต้นฉบับหน้า 43 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=43)

---

## หน้า 44

#### VPN Label Propagation 



Question: 

How will the ingress PE router get the second label in the label stack from the egress PE router? 

Answer: 

Labels are propagated in MP-BGP VPNv4 routing updates.

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
MPLS VPN Backbone: Ingress PE Router — P Router — P Router — Egress PE Router; two CE Routers connect to each edge.
VPN-label propagation arrow: Egress PE → Ingress PE
```

[ดูภาพต้นฉบับหน้า 44 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=44)

---

## หน้า 45

#### VPN Label Propagation (Cont.) 



Step 1: A VPN label is assigned to every VPN route by the egress PE router. 

Step 2: The VPN label is advertised to all other PE routers in an MP-BGP update. 

Step 3: A label stack is built in the VRF table.

#### ข้อความในภาพ — ตรวจเทียบต้นฉบับแล้ว

```text
MPLS VPN Backbone: Ingress PE Router — P Router — P Router — Egress PE Router; two CE Routers connect to each edge.
Route 192.168.10.0: right CE → Egress PE
VPN label at Egress PE: 38
Label propagation arrow: Egress PE → Ingress PE
Label boxes at Ingress PE: [38][26]
Core LSP Label = 26
```

[ดูภาพต้นฉบับหน้า 45 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=45)

---

## หน้า 46

#### MPLS VPNs and Label Propagation 

- The VPN label must be assigned by the BGP next hop. 

- The BGP next hop should not be changed in the MP-IBGP update propagation. 

- The PE router must be the BGP next hop. 

- The label must be reoriginated if the next hop is changed.

  - A new label is assigned every time that the MP-BGP update crosses the AS boundary where the next hop is changed.

[ดูภาพต้นฉบับหน้า 46 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=46)

---

## หน้า 47

#### MPLS VPN Label Stack 

- There are at least two labels when using MPLS-VPN 

- The first label is distributed by TDP/LDP 

   - Derived from an IGP route 

   - Corresponds to a PE address (VPN egress point) 

   - PE addresses are MP-BGP next-hops of VPN routes 

- The second label is distributed by MP-BGP 

   - Corresponds to the actual VPN route 

   - Identifies the PE outgoing interface or routing table 

```text
[L2 Header][Label 1][Label 2][L3 Header][Data]
``` 

**Frame, e.g. HDLC, PPP, Ethernet**

[ดูภาพต้นฉบับหน้า 47 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=47)

---

## หน้า 48

### MPLS VPN Operation

```text
Four PE routers (upper/lower left and upper/lower right).
Three CE routers connect to each PE (twelve CE routers total).
Two P routers form the provider core; two RR routers connect to the core.
Customer-route colors: orange, green, magenta.
At upper left and upper right PE: = RT?
MP-BGP upper annotation: RD + orange; RD + green; VPN labels, RTs
MP-BGP lower annotation: RD + orange; RD + green; RD + magenta; VPN labels, RTs
```

| Symbol / color | Source legend |
| --- | --- |
| Curved arrow at PE | Import routes into VRF if route-targets match (export = import) |
| Orange, green, magenta route markers | Customer routes placed into separate VRF tables at each PE |
| Red arrows | IGP (OSPF,ISIS) used to establish reachability to destination networks. |
| Green arrows | Label Distribution Protocol establishes mappings to IGP addresses |
| Blue arrows | CE-PE dynamic routing (or static) populate the VRF routing tables |
| Gray arrows | MP-BGP between PE router to distribute routes between VPNs |

Gray MP-BGP arrows connect PE–RR and RR–RR; red/green arrows connect PE–P and P–P; blue arrows connect CE–PE.

[ดูภาพต้นฉบับหน้า 48 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=48)

---

## หน้า 49

### MPLS VPN Forwarding Example

```text
Four PE routers, two P routers; three CE routers per PE.
Highlighted forwarding path: lower-left CE → lower-left PE → left P → right P → lower-right PE → red CE.
Lower-left PE:
  Push VPN Label (Red Route)
  Push IGP Label (Green PE Router)
Left P: Swap IGP Label (From LFIB)
Right P: POP IGP Label (Pentultimate Hop)
Lower-right PE: Pop VPN Label (Red Route)
```

> หมายเหตุจากการตรวจ: ต้นฉบับสะกด Pentultimate Hop ตามที่เก็บไว้ในข้อความ

[ดูภาพต้นฉบับหน้า 49 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=49)

---

## หน้า 50

### Virtual Routing and Forwarding

- A VRF is the routing and forwarding instance for a set of sites with identical connectivity requirements. 

- Data structures associated with a VRF: 

   - IP routing table 

   - Cisco Express Forwarding (CEF) forwarding table 

   - Set of rules and routing protocol parameters (routing protocol contexts) 

   - List of interfaces that use the VRF 

- Other information associated with a VRF: 

   - Route Distinguisher (RD) 

   - Set of import and export route targets

[ดูภาพต้นฉบับหน้า 50 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=50)

---

## หน้า 51

### Provider Edge VRFs (PE VRFs)

```text
PE Router contains three VRF layers (purple, orange, green).
Left: Label Switching (MPLS) or Tunneling (L2TPv3)
  MPLS/Tunnel Labels and Route Targets
  VPN LSP/Tunnel
Right: IP Switching
  802.1q
  Logical or Physical Int (Layer 3)
Each VRF connects the left VPN LSP/Tunnel to its right Layer 3 interface.
```

[ดูภาพต้นฉบับหน้า 51 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=51)

---

## หน้า 52

#### VPN-Aware Routing Protocols 

- Routing context = routing protocol run in one VRF 

   - Supported by VPN-aware routing protocols: 

      - External BGP (EBGP), OSPF, RIP version 2 (RIPv2), EIGRP, IS-IS, Static routes 

   - Implemented as several instances of a single routing process (EBGP, RIPv2) or as several routing processes (OSPF) 

   - Independent per-instance router variables for each instance

[ดูภาพต้นฉบับหน้า 52 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=52)

---

## หน้า 53

#### VRF Routing Table 

- Contains routes that should be available to a particular set of sites 

- Analogous to standard Cisco IOS software routing table; supports same set of mechanisms 

- VPN interfaces (physical interface, subinterfaces, logical interfaces) assigned to VRFs 

   - Many interfaces per VRF 

   - Each interface assignable to only one VRF

[ดูภาพต้นฉบับหน้า 53 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=53)

---

## หน้า 54

### Routing Contexts, VRF, and MP-BGP Interaction: 1/9

| Component | Instances / tables |
| --- | --- |
| CE routers | CE-RIP-A, CE-RIP-B, CE-BGP-A, CE-BGP-B |
| RIP Routing Process | Instance for VRF-A; Instance for VRF-B |
| Routing tables | VRF-A Routing Table; VRF-B Routing Table |
| BGP Routing Process | Instance for VRF-A; Instance for VRF-B; Backbone Multiprotocol BGP |

```text
Initial layout: two VRFs with separate RIP and BGP instances.
```

- **Two VPNs attached to the same PE router** 

- **Each VPN represented by a VRF (VRF-A and VRF-B)** 

- **RIP and BGP running between PE and CE routers**

[ดูภาพต้นฉบับหน้า 54 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=54)

---

## หน้า 55

### Routing Contexts, VRF, and MP-BGP Interaction: 2/9

| Component | Instances / tables |
| --- | --- |
| CE routers | CE-RIP-A, CE-RIP-B, CE-BGP-A, CE-BGP-B |
| RIP Routing Process | Instance for VRF-A; Instance for VRF-B |
| Routing tables | VRF-A Routing Table; VRF-B Routing Table |
| BGP Routing Process | Instance for VRF-A; Instance for VRF-B; Backbone Multiprotocol BGP |

```text
Highlighted RIP arrows: CE-RIP-A → RIP Instance for VRF-A → VRF-A Routing Table; CE-RIP-B → RIP Instance for VRF-B → VRF-B Routing Table.
```

- **RIP-speaking CE routers announce their prefixes to the PE router via RIP.** 

- **Instance of RIP process associated with the VRF into which the PE-CE interface belongs collects the routes and inserts them into VRF routing table.**

[ดูภาพต้นฉบับหน้า 55 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=55)

---

## หน้า 56

### Routing Contexts, VRF, and MP-BGP Interaction: 3/9

| Component | Instances / tables |
| --- | --- |
| CE routers | CE-RIP-A, CE-RIP-B, CE-BGP-A, CE-BGP-B |
| RIP Routing Process | Instance for VRF-A; Instance for VRF-B |
| Routing tables | VRF-A Routing Table; VRF-B Routing Table |
| BGP Routing Process | Instance for VRF-A; Instance for VRF-B; Backbone Multiprotocol BGP |

```text
Highlighted BGP arrows: CE-BGP-A → BGP Instance for VRF-A → VRF-A Routing Table; CE-BGP-B → BGP Instance for VRF-B → VRF-B Routing Table.
```

- **BGP-speaking CE routers announce their prefixes to the PE router via BGP.** 

- **Instance of BGP process associated with the VRF into which the PE-CE interface belongs collects the routes and inserts them into VRF routing table.**

[ดูภาพต้นฉบับหน้า 56 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=56)

---

## หน้า 57

### Routing Contexts, VRF, and MP-BGP Interaction: 4/9

| Component | Instances / tables |
| --- | --- |
| CE routers | CE-RIP-A, CE-RIP-B, CE-BGP-A, CE-BGP-B |
| RIP Routing Process | Instance for VRF-A; Instance for VRF-B |
| Routing tables | VRF-A Routing Table; VRF-B Routing Table |
| BGP Routing Process | Instance for VRF-A; Instance for VRF-B; Backbone Multiprotocol BGP |

```text
Highlighted curved arrow: RIP / VRF routes → BGP VRF instance (redistribution).
```

- **RIP routes entered in the VRF routing table are redistributed into BGP for further propagation into the MPLS VPN backbone.** 

- **Redistribution between RIP and BGP has to be configured for proper MPLS VPN operation.**

[ดูภาพต้นฉบับหน้า 57 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=57)

---

## หน้า 58

### Routing Contexts, VRF, and MP-BGP Interaction: 5/9

| Component | Instances / tables |
| --- | --- |
| CE routers | CE-RIP-A, CE-RIP-B, CE-BGP-A, CE-BGP-B |
| RIP Routing Process | Instance for VRF-A; Instance for VRF-B |
| Routing tables | VRF-A Routing Table; VRF-B Routing Table |
| BGP Routing Process | Instance for VRF-A; Instance for VRF-B; Multiprotocol BGP |

```text
Highlighted arrow: BGP Instance for VRF-A → Multiprotocol BGP → other PE routers.
```

- **Route distinguisher is prepended during route export to the BGP routes from VRF instance of BGP process to convert them into VPNv4 prefixes. Route targets are attached to these prefixes.** 

- **VPNv4 prefixes are propagated to other PE routers.**

[ดูภาพต้นฉบับหน้า 58 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=58)

---

## หน้า 59

### Routing Contexts, VRF, and MP-BGP Interaction: 6/9

| Component | Instances / tables |
| --- | --- |
| CE routers | CE-RIP-A, CE-RIP-B, CE-BGP-A, CE-BGP-B |
| RIP Routing Process | Instance for VRF-A; Instance for VRF-B |
| Routing tables | VRF-A Routing Table; VRF-B Routing Table |
| BGP Routing Process | Instance for VRF-A; Instance for VRF-B; Multiprotocol BGP |

```text
Highlighted incoming arrows: other PE routers → Multiprotocol BGP → VRF-A Routing Table and VRF-B Routing Table.
```

- **VPNv4 prefixes are received from other PE routers.** 

- **The VPNv4 prefixes are inserted into proper VRF routing tables based on their route targets and import route targets configured in VRFs.** 

- **Route distinguisher is removed during this process.**

[ดูภาพต้นฉบับหน้า 59 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=59)

---

## หน้า 60

### Routing Contexts, VRF, and MP-BGP Interaction: 7/9

| Component | Instances / tables |
| --- | --- |
| CE routers | CE-RIP-A, CE-RIP-B, CE-BGP-A, CE-BGP-B |
| RIP Routing Process | Instance for VRF-A; Instance for VRF-B |
| Routing tables | VRF-A Routing Table; VRF-B Routing Table |
| BGP Routing Process | Instance for VRF-A; Instance for VRF-B; Backbone Multiprotocol BGP |

```text
Highlighted arrows: Backbone Multiprotocol BGP → BGP Instance for VRF-A / VRF-B → CE-BGP-A / CE-BGP-B.
```

- **Routes received from backbone MP-BGP and imported into a VRF are forwarded as IPv4 routes to EBGP CE neighbors attached to that VRF.**

[ดูภาพต้นฉบับหน้า 60 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=60)

---

## หน้า 61

### Routing Contexts, VRF, and MP-BGP Interaction: 8/9

| Component | Instances / tables |
| --- | --- |
| CE routers | CE-RIP-A, CE-RIP-B, CE-BGP-A, CE-BGP-B |
| RIP Routing Process | Instance for VRF-A; Instance for VRF-B |
| Routing tables | VRF-A Routing Table; VRF-B Routing Table |
| BGP Routing Process | Instance for VRF-A; Instance for VRF-B; Multiprotocol BGP |

```text
Highlighted curved arrow: BGP VRF instance → RIP VRF instance (redistribution).
```

- **MP-IBGP routes imported into a VRF are redistributed into the instance of RIP configured for that VRF.**

- **Redistribution between BGP and RIP has to be configured for end-to-end RIP routing between CE routers.**

[ดูภาพต้นฉบับหน้า 61 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=61)

---

## หน้า 62

### Routing Contexts, VRF, and MP-BGP Interaction: 9/9

| Component | Instances / tables |
| --- | --- |
| CE routers | CE-RIP-A, CE-RIP-B, CE-BGP-A, CE-BGP-B |
| RIP Routing Process | Instance for VRF-A; Instance for VRF-B |
| Routing tables | VRF-A Routing Table; VRF-B Routing Table |
| BGP Routing Process | Instance for VRF-A; Instance for VRF-B; Backbone Multiprotocol BGP |

```text
Highlighted arrows: RIP Instance for VRF-A → CE-RIP-A; RIP Instance for VRF-B → CE-RIP-B.
```

- **Routes redistributed from BGP into a VRF instance of RIP are sent to RIP-speaking CE routers.**

[ดูภาพต้นฉบับหน้า 62 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=62)

---

## หน้า 63

#### Traceroute in an MPLS VPN 

**63** 

© 2010 Cisco Systems, Inc. All rights reserved. Cisco Confidential 

JMB

[ดูภาพต้นฉบับหน้า 63 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=63)

---

## หน้า 64

#### TTL Field in Labels 

- Only the TTL field in the label at the top of the stack counts 

- The outgoing TTL value is only a function of the incoming TTL value 

- Outgoing TTL is one less than incoming TTL 

- If outgoing TTL = 0, packet is not forwarded (not even stripped and forwarded as an ip packet)

[ดูภาพต้นฉบับหน้า 64 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=64)

---

## หน้า 65

#### Copying of TTL field 

- When an ip packet is first labeled, the TTL field is copied from the ip header to the MPLS header (after being decremented by 1) 

- When the label stack is removed, the outgoing TTL value is copied to the TTL field in the ip header 

   - Unless MPLS TTL > IP TTL

[ดูภาพต้นฉบับหน้า 65 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=65)

---

## หน้า 66

### Traceroute in IP Network — probe 1

All routers switch ip packets.

```text
Topology (left to right): 10.1.2.1 — router — router — router — 10.1.1.1
Forward probe (left to right):
  Link 1: destination 10.1.1.1; TTL = 1; udp port = 35678
Router 2: TTL = 0
ICMP reply (right to left, from the responding router):
  Return link 1: destination 10.1.2.1; TTL = 255; icmp TTL exceeded
```

[ดูภาพต้นฉบับหน้า 66 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=66)

---

## หน้า 67

### Traceroute in IP Network — probe 2

All routers switch ip packets.

```text
Topology (left to right): 10.1.2.1 — router — router — router — 10.1.1.1
Forward probe (left to right):
  Link 1: destination 10.1.1.1; TTL = 2; udp port = 35678
  Link 2: destination 10.1.1.1; TTL = 1; udp port = 35678
Router 3: TTL = 0
ICMP reply (right to left, from the responding router):
  Return link 1: destination 10.1.2.1; TTL = 255; icmp TTL exceeded
  Return link 2: destination 10.1.2.1; TTL = 254; icmp TTL exceeded
```

[ดูภาพต้นฉบับหน้า 67 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=67)

---

## หน้า 68

### Traceroute in IP Network — probe 3

All routers switch ip packets.

```text
Topology (left to right): 10.1.2.1 — router — router — router — 10.1.1.1
Forward probe (left to right):
  Link 1: destination 10.1.1.1; TTL = 3; udp port = 35678
  Link 2: destination 10.1.1.1; TTL = 2; udp port = 35678
  Link 3: destination 10.1.1.1; TTL = 1; udp port = 35678
Router 4: TTL = 0
ICMP reply (right to left, from the responding router):
  Return link 1: destination 10.1.2.1; TTL = 255; icmp TTL exceeded
  Return link 2: destination 10.1.2.1; TTL = 254; icmp TTL exceeded
  Return link 3: destination 10.1.2.1; TTL = 253; icmp TTL exceeded
```

[ดูภาพต้นฉบับหน้า 68 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=68)

---

## หน้า 69

### Traceroute in IP Network — probe 4

All routers switch ip packets.

```text
Topology (left to right): 10.1.2.1 — router — router — router — 10.1.1.1
Forward probe (left to right):
  Link 1: destination 10.1.1.1; TTL = 4; udp port = 35678
  Link 2: destination 10.1.1.1; TTL = 3; udp port = 35678
  Link 3: destination 10.1.1.1; TTL = 2; udp port = 35678
  Link 4: destination 10.1.1.1; TTL = 1; udp port = 35678
Destination 10.1.1.1: udp port 35678?
ICMP reply (right to left, from the responding router):
  Return link 1: destination 10.1.2.1; TTL = 255; icmp port unreachable
  Return link 2: destination 10.1.2.1; TTL = 254; icmp port unreachable
  Return link 3: destination 10.1.2.1; TTL = 253; icmp port unreachable
  Return link 4: destination 10.1.2.1; TTL = 252; icmp port unreachable
```

[ดูภาพต้นฉบับหน้า 69 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=69)

---

## หน้า 70

### Traceroute in MPLS VPN Network

```text
VPN1 CE (10.1.2.1) — PE — P — PE — CE (10.1.1.1) VPN1
                         MPLS cloud
MPLS cloud contains the two PE routers and the P router.
```

[ดูภาพต้นฉบับหน้า 70 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=70)

---

## หน้า 71

### Traceroute in MPLS VPN Network

```text
VPN1 CE (10.1.2.1) — PE — P — PE — CE (10.1.1.1) VPN1
PE/P interfaces: 1 on the left; 0 on the right.
```

#### Left PE — BGP RID = 1.1.1.1 — LFIB (VRF 1)

| In label | Prefix | Out interface | Out label |
| --- | --- | --- | --- |
| - | 10.1.1.0/24 | pos 0 | 26 32 |
| 31 | 10.1.2.0/24 | pos 1 | - |

#### P — LFIB

| In label | Prefix | Out interface | Out label |
| --- | --- | --- | --- |
| 26 | 1.1.1.1/32 | pos 0 | pop |
| 29 | 1.1.1.2/32 | pos 1 | pop |

#### Right PE — BGP RID = 1.1.1.2 — LFIB (VRF 1)

| In label | Prefix | Out interface | Out label |
| --- | --- | --- | --- |
| 32 | 10.1.1.0/24 | pos 0 | - |
| - | 10.1.2.0/24 | pos 1 | 29 31 |

[ดูภาพต้นฉบับหน้า 71 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=71)

---

## หน้า 72

### Traceroute in MPLS VPN Network — probe 1

```text
10.1.2.1 CE — left PE — P — right PE — CE 10.1.1.1
CE → left PE: destination 10.1.1.1; TTL = 1; udp port = 35678
Left PE: TTL = 0
Left PE → source CE: destination 10.1.2.1; TTL = 255; icmp TTL exceeded
```

[ดูภาพต้นฉบับหน้า 72 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=72)

---

## หน้า 73

### Traceroute in MPLS VPN Network — probe 2

tag-switching ip propagate-ttl on PE routers (default behaviour)

```text
10.1.2.1 CE — left PE — P — right PE — CE 10.1.1.1
Forward probe:
  CE → left PE: IP destination 10.1.1.1; TTL = 2; udp port = 35678
  Left PE → P: IGP label 26 TTL = 1; vpn label 32;
               IP destination 10.1.1.1 TTL = 1; udp port = 35678
  P: ttl = 0
ICMP TTL exceeded reply (destination 10.1.2.1):
  P → right PE: label 32 TTL = 255; IP TTL = 255
  Right PE → right CE: IP TTL = 254
  Right CE → right PE: IP TTL = 253
  Right PE → P: label 29 TTL = 252; label 31; IP TTL = 252
  P → left PE: label 31 TTL = 251; IP TTL = 252
  Left PE → left CE: IP TTL = 250
```

> หมายเหตุจากการตรวจ: เก็บค่า label TTL และ IP TTL ตามกล่องแพ็กเก็ตในต้นฉบับแต่ละตำแหน่ง แม้บางช่วงค่าจะต่างกัน

[ดูภาพต้นฉบับหน้า 73 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=73)

---

## หน้า 74

### Traceroute: Example

#### MPLS

```text
singularity#traceroute 10.1.2.5

Type escape sequence to abort.
Tracing the route to 10.1.2.5

  1 10.1.1.26 [MPLS: Label 12310 Exp 0] 0 msec 0 msec 4 msec
  2 10.1.1.2 [MPLS: Label 12313 Exp 0] 0 msec 0 msec 0 msec
  3 10.1.1.6 [MPLS: Label 12312 Exp 0] 0 msec 4 msec 0 msec
  4 10.1.1.30 0 msec *  0 msec
```

#### MPLS VPN

```text
singularity#traceroute vrf one 10.1.4.5

Type escape sequence to abort.
Tracing the route to 10.1.4.5

  1 10.1.1.26 [MPLS: Labels 12310/29 Exp 0] 0 msec 0 msec 4 msec
  2 10.1.1.2 [MPLS: Labels 12313/29 Exp 0] 0 msec 0 msec 0 msec
  3 10.1.1.6 [MPLS: Labels 12312/29 Exp 0] 0 msec 0 msec 0 msec
  4 10.1.4.6 [MPLS: Label 29 Exp 0] 0 msec 0 msec 4 msec
  5 10.1.4.5 0 msec *  0 msec
```

[ดูภาพต้นฉบับหน้า 74 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=74)

---

## หน้า 75

### TTL Commands

- forwarding -> `tag ip propagate-ttl forwarded` (default)
  - ip ttl is copied to label ttl
- not forwarding- > `no tag ip propagate-ttl forwarded`
  - MPLS ttl is set to 255
  - MPLS Core is “invisible” in traceroutes
- forwarding locally -> `tag ip propagate-ttl local`
  - IP packets coming from the CE are imposed with a label carrying ttl = 255
  - IP packets originated on PE within the vrf get label ttl = ip ttl
  - Result:
    - a traceroute from vrf on PE to a vrf destination, will still show all the hops: provider sees all hops in the MPLS cloud
    - a traceroute from CE to a VRF destination show the MPLS cloud as one ip hop: customer does not see the number of hops in the MPLS cloud

[ดูภาพต้นฉบับหน้า 75 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=75)

---

## หน้า 76

### No Tag IP Propagate-ttl Forwarded

- Set on LSR doing ip->mpls, so on PEs

#### Traceroute CE to CE — tag ip propagate-ttl forwarded

```text
moorcock#traceroute 10.1.5.2
  1 10.1.4.2 4 msec 0 msec 4 msec
  2 10.1.1.26 [MPLS: Labels 12310/30 Exp 0] 4 msec 4 msec 8 msec
  3 10.1.1.2 [MPLS: Labels 12313/30 Exp 0] 8 msec 4 msec 4 msec
  4 10.1.1.6 [MPLS: Labels 12312/30 Exp 0] 8 msec 8 msec 4 msec
  5 10.1.4.6 [MPLS: Label 30 Exp 0] 4 msec 4 msec 4 msec
  6 10.1.4.5 4 msec *  4 msec
```

| Hop | Annotation |
| --- | --- |
| 1 | local PE |
| 2–4 | P |
| 5 | remote PE |
| 6 | remote CE |

#### no tag ip propagate-ttl forwarded

```text
moorcock#traceroute 10.1.5.2
  1 10.1.4.2 0 msec 0 msec 4 msec
  2 10.1.4.5 4 msec *  4 msec
```

| Hop | Annotation |
| --- | --- |
| 1 | local PE |
| 2 | remote CE |

> หมายเหตุจากการตรวจ: คำสั่งในต้นฉบับระบุปลายทาง 10.1.5.2 แต่ผล hop สุดท้ายแสดง 10.1.4.5 เก็บตามต้นฉบับทั้งสองส่วน

[ดูภาพต้นฉบับหน้า 76 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=76)

---

## หน้า 77

### Traceroute in MPLS VPN Network — probe 2

no tag-switching ip propagate-ttl on PE routers

```text
10.1.2.1 CE — left PE — P — right PE — CE 10.1.1.1
Forward probe (destination 10.1.1.1; udp port = 35678):
  CE → left PE: IP TTL = 2
  Left PE → P: IGP label 26 TTL = 255; vpn label 32; IP TTL = 1
  P → right PE: label 32 TTL = 254; IP TTL = 1
  Right PE → right CE: IP TTL = 1
  Destination CE: udp port 35678?
ICMP port unreachable reply (destination 10.1.2.1):
  Right CE → right PE: IP TTL = 255
  Right PE → P: label 29 TTL = 255; label 31; IP TTL = 254
  P → left PE: label 31 TTL = 254; IP TTL = 254
  Left PE → left CE: IP TTL = 253
```

[ดูภาพต้นฉบับหน้า 77 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=77)

---

## หน้า 78

##### PE-CE Routing Protocols 

**78** 

© 2010 Cisco Systems, Inc. All rights reserved. 

Cisco Confidential 

JMB

[ดูภาพต้นฉบับหน้า 78 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=78)

---

## หน้า 79

### Configuring PE-CE Routing Protocols

- PE-CE routing protocols are configured for individual VRFs.
- Per-VRF routing protocols can be configured in two ways:
  - There is only one BGP or RIP process per router; per-VRF parameters are specified in routing contexts, which are selected with the address family command.
  - A separate OSPF process has to be started for each VRF.

[ดูภาพต้นฉบับหน้า 79 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=79)

---

## หน้า 80

### 3.1 Static Routing

[ดูภาพต้นฉบับหน้า 80 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=80)

---

## หน้า 81

#### Static Routing 

- Highly scalable and secured 

- Ideal for single attached sites (one way out) 

- For multi-homed sites, static routing may not provide re-routing capabilities in case of certain failure scenarios – highly discouraged 

- For every net in a given site, static configuration is required on PE 

- For traffic leaving the site (single homed), a static default route could be used on CE 

- Can co-exist with dynamic routing protocols

[ดูภาพต้นฉบับหน้า 81 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=81)

---

## หน้า 82

###### Static PE-CE: 

```text
MPLS VPN Cloud: PE1, PE2, PE3.
Site 1: CE1 — PE1; Site 2: CE2 — PE2; Site 3: CE3 — PE3.
MP-iBGP Update: RD:11:1; Next-Hop=PE-1; RT=All-Sites; Label=100.
VPNv4-Address: 11:1:1.1.1.1/32.
PE1: Advertise this prefix across MPLS Cloud to all PEs using MP-BGP.
PE1: Static route to 1.0.0.0 pointing to CE & Redistribute Static route into MP-BGP.
CE1: Static route (default); 2.0.0.0 3.0.0.0.
```

> หมายเหตุจากการตรวจ: ต้นฉบับระบุ static route 1.0.0.0 แต่กล่อง VPNv4 Update แสดง 11:1:1.1.1.1/32 เก็บทั้งสองค่าตามภาพ

[ดูภาพต้นฉบับหน้า 82 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=82)

---

## หน้า 83

### 3.2 RIPv2 Routing

[ดูภาพต้นฉบับหน้า 83 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=83)

---

## หน้า 84

#### RIPv2 

- Provides a simple distance vector protocol to exchange routing information 

- Hop count limit of 15 

- Could be used at smaller sites where hop-count is much less than 15 

- Supports multi-homed sites with re-routing capabilities

[ดูภาพต้นฉบับหน้า 84 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=84)

---

## หน้า 85

#### RIPv2 PE-CE: 

```text
MPLS VPN Cloud: PE1, PE2, PE3.
Site 1: CE1 — PE1; Site 2: CE2 — PE2; Site 3: CE3 — PE3.
MP-iBGP Update: RD:11:1; Next-Hop=PE-1; RT=All-Sites; Label=100.
VPNv4-Address: 11:1:1.1.1.1/32.
PE1: Advertise this prefix across MPLS Cloud to all PEs using MP-BGP.
CE1 → PE1: RIPv2; Advertise RIP Prefix 1.1.1.1.
PE1: Redistribute learned route into MP-BGP.
MP-iBGP Update Metric: RIP metric copied.
PE2 — CE2: RIPv2.
PE3: MP-BGP → Redistribute BGP route into RIP → CE3 (RIPv2).
```

[ดูภาพต้นฉบับหน้า 85 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=85)

---

## หน้า 86

### 3.3 BGP Routing

[ดูภาพต้นฉบับหน้า 86 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=86)

---

## หน้า 87

#### BGP PE-CE Requirements 

- Enterprise Customers choosing BGP as PE-CE protocol to peer with the Service Provider in MPLSVPNs network should look into the following: 

   - Same AS number at all the customer locations 

   - Different AS number at the Customer Locations 

   - With Back Doors 

   - Private AS number vs. Public AS # 

   - Multi-homing and Loadbalancing options 

   - Customer sites connected to two or more Providers 

- BGP is one of the widely used PE-CE protocol in the MPLS-VPN environment

[ดูภาพต้นฉบับหน้า 87 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=87)

---

## หน้า 88

###### BGP PE-CE: Same AS at Customer Sites 

```text
MPLS VPN Cloud: PE1, PE2, PE3.
Site 1: CE1 — PE1; Site 2: CE2 — PE2; Site 3: CE3 — PE3.
MP-iBGP Update: RD:11:1; Next-Hop=PE-1; RT=All-Sites; Label=100.
VPNv4-Address: 11:1:1.1.1.1/32.
PE1: Advertise this prefix across MPLS Cloud to all PEs using MP-BGP.
Provider BGP AS # 1234.
Customer BGP AS # 1 at CE1, CE2 and CE3.
CE1 → PE1: Advertise BGP Prefix 1.1.1.1.
PE1: Redistribute learned route into MP-BGP.
PE2 and PE3: MP-BGP → BGP; AS-Path: 1234 1.
Site 2 Sees its own AS #; Site 3 sees its own AS #.
Need AS-Override option the PE2 & PE3 so that Site2 & Site 3 see the routes.
```

- Customer Site 1 sends the BGP routes to PE1 

- PE1 advertises to all the iBGP-VPNv4 peers 

- Remote PEs (PE2 & PE3) redistributes those routes into the local BGP peer at their sites 

- Site 2 & 3 CE routers will not accept the routes as they see their own AS in the AS-Path 

- MPLS-VPN routers need to be configured with the “AS-OVERRIDE” option so that remote CE Routers will not see their own AS in AS PATH

[ดูภาพต้นฉบับหน้า 88 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=88)

---

## หน้า 89

### BGP PE-CE: Same AS at Customer Sites

PE is sending the update to remote CEs for 1.1.1.1/32.

```text
BGP(4): 140.0.0.201 send UPDATE (chgflags: 0x820) 1.1.1.1/32, next 140.0.0.202, metric 0, path 1, extended community RT:1:1
```

CE receives the update and ignores the Update due to its own AS in the AS-Path.

```text
BGP(0): 140.0.0.202 rcv UPDATE about 1.1.1.1/32 -- DENIED due to: AS-PATH contains our own AS;
```

With “AS-Override” option configured on the PE Router(s), PE is now sending the update to remote CEs for 1.1.1.1/32 with “prepend” option.

```text
BGP(4): 140.0.0.201 send UPDATE (prepend, chgflags: 0x820) 1.1.1.1/32, next 140.0.0.202, metric 0, path 1, extended community RT:1:1
```

CE now receives and accepts the route.

```text
BGP(0): 140.0.0.202 rcvd 1.1.1.1/32
BGP(0): Revise route installing 1 of 1 routes for 1.1.1.1/32 -> 140.0.0.202(main) to main IP table
```

[ดูภาพต้นฉบับหน้า 89 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=89)

---

## หน้า 90

###### BGP PE-CE: Same AS at Customer Sites 

```
CE2#show ip bgp
   Network          Next Hop            Metric LocPrf Weight Path
*> 1.1.1.1/32       140.0.0.202                            0 65000 65000 i
*> 2.2.2.2/32       0.0.0.0                  0         32768 i
*> 3.3.3.3/32       140.0.0.202                            0 65000 65000 i
```

###### **AS 1 is replaced by AS 65000** 

#### PE Router Configuration

```text
!
router bgp 65000
 no bgp default ipv4-unicast
 bgp log-neighbor-changes
 neighbor 11.11.11.11 remote-as 65000
 neighbor 11.11.11.11 update-source Loopback0
 neighbor 13.13.13.13 remote-as 65000
 neighbor 13.13.13.13 update-source Loopback0
!
 address-family vpnv4
  neighbor 11.11.11.11 activate
  neighbor 11.11.11.11 send-community extended
  neighbor 13.13.13.13 activate
  neighbor 13.13.13.13 send-community extended
 exit-address-family
!
 address-family ipv4 vrf BGP-PE-CE
  redistribute connected
  neighbor 140.0.0.201 remote-as 1
  neighbor 140.0.0.201 activate
  neighbor 140.0.0.201 as-override
  no synchronization
 exit-address-family
!
```

[ดูภาพต้นฉบับหน้า 90 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=90)

---

## หน้า 91

###### BGP PE-CE: Same AS at Customer Sites 

```text
MPLS VPN Cloud: PE1, PE2, PE3.
Site 1: CE1 — PE1; Site 2: CE2 — PE2; Site 3: CE3 — PE3.
MP-iBGP Update: RD:11:1; Next-Hop=PE-1; RT=All-Sites; Label=100.
VPNv4-Address: 11:1:1.1.1.1/32.
PE1: Advertise this prefix across MPLS Cloud to all PEs using MP-BGP.
Provider BGP AS # 1234.
Customer BGP AS # 1 at CE1, CE2 and CE3.
CE1 → PE1: Advertise BGP Prefix 1.1.1.1.
PE1: Redistribute learned route into MP-BGP.
PE2 and PE3: MP-BGP → BGP; AS-Path: 1234 1.
Site 2 Sees its own AS #; Site 3 sees its own AS #.
Use “Allow-AS in” on CE2 and CE3.
```

- Alternate approach is to use “Allow-AS in” on Ces facing the PEs 

- CEs bypass the AS based loop detection mechanism 

- Acceptable number of AS occurrences within the AS-Path could be defined, to detect loops

[ดูภาพต้นฉบับหน้า 91 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=91)

---

## หน้า 92

###### BGP PE-CE: Different AS at Customer Sites 

```text
MPLS VPN Cloud: PE1, PE2, PE3.
Site 1: CE1 — PE1; Site 2: CE2 — PE2; Site 3: CE3 — PE3.
MP-iBGP Update: RD:11:1; Next-Hop=PE-1; RT=All-Sites; Label=100.
VPNv4-Address: 11:1:1.1.1.1/32.
PE1: Advertise this prefix across MPLS Cloud to all PEs using MP-BGP.
Provider BGP AS # 1234.
Customer BGP AS # 1 at CE1; AS # 2 at CE2; AS # 3 at CE3.
CE1 → PE1: Advertise BGP Prefix 1.1.1.1.
PE1: Redistribute learned route into MP-BGP.
PE2 and PE3: MP-BGP → BGP → respective CE.
```

- Customer Site 1 sends the BGP routes to PE1 

- PE1 advertises to all the iBGP-VPNv4 peers 

- Remote PEs (PE2 & PE3) redistributes those routes into the local BGP peer at their sites 

- Site 2 & 3 CE routers will receive and install the routes from the PEs in the MPLS Core

[ดูภาพต้นฉบับหน้า 92 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=92)

---

## หน้า 93

### BGP PE-CE: Different AS at Customer Sites

```text
CE2#show ip bgp
   Network       Next Hop      Metric LocPrf Weight Path
*> 1.1.1.1/32    140.0.0.202                      0 65000 1 i

CE2#show ip route
B     1.1.1.1 [20/0] via 140.0.0.202, 00:03:14

CE3#show ip bgp
   Network       Next Hop      Metric LocPrf Weight Path
*> 1.1.1.1/32    140.0.0.130                      0 65000 1 i

CE3#show ip route
B     1.1.1.1 [20/0] via 140.0.0.130, 00:00:44
```

The complete AS Path traversed by the IPv4 Prefix.

ภาพวงค่า AS Path `65000 1`, รหัส route `B` และ administrative distance `20` เพื่อชี้ข้อความอธิบายนี้

[ดูภาพต้นฉบับหน้า 93 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=93)

---

## หน้า 94

###### BGP PE-CE: With Back Door Connections 

```text
MPLS VPN Cloud: PE1, PE2, PE3.
Site 1: CE1 — PE1; Site 2: CE2 — PE2; Site 3: CE3 — PE3.
MP-iBGP Update: RD:11:1; Next-Hop=PE-1; RT=All-Sites; Label=100.
VPNv4-Address: 11:1:1.1.1.1/32.
PE1: Advertise this prefix across MPLS Cloud to all PEs using MP-BGP.
Provider BGP AS # 1234.
Customer BGP AS # 1 at CE1; AS # 2 at CE2; AS # 3 at CE3.
CE1 → PE1: Advertise BGP Prefix 1.1.1.1.
PE1: Redistribute learned route into MP-BGP.
PE2 and PE3: MP-BGP → BGP → respective CE.
Back door: CE1 — IGP (IS-IS, OSPF, EIGRP) — CE2 — IGP (IS-IS, OSPF, EIGRP) — CE3.
Highlighted IGP advertisements: CE1 → CE2 and CE3 → CE2.
```

- Mechanisms explained earlier are still valid 

- When the MP-BGP route on either PE2 or PE3 sent to CE2 or CE3 for CE1— the route will be learned as an external eBGP route with Admin. distance of 20 

- If via the back door the same route comes via either OSPF, IS-IS or EIGRP, Admin distance will come into the consideration 

- Since eBGP has Admin. Distance of 20—MPLS-Core will be used to reach the destination

[ดูภาพต้นฉบับหน้า 94 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=94)

---

## หน้า 95

#### BGP PE-CE: With Back Door Connections 

```
CE2#show ip route 1.1.1.1
Routing entry for 1.1.1.1/32
  Known via "ospf 1", distance 110, metric 11, type intra area
  Last update from 140.0.0.194 on Ethernet0/0, 00:00:09 ago
```


<mark>We see 1.1.1.1/32 being learned via the backdoor path [OSPF]</mark> 

With the BGP session being UP, we see 1.1.1.1/32 being learned via BGP and installed into the RIB as a eBGP route 

```
%BGP-5-ADJCHANGE: neighbor 140.0.0.202 Up
RT: closer admin distance for 1.1.1.1, flushing 1 route
RT: add 1.1.1.1/32 via 140.0.0.202, bgp metric [20/0]
```

[ดูภาพต้นฉบับหน้า 95 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=95)

---

## หน้า 96

###### BGP PE-CE: With Back Door Connections 

```
CE2#show ip route 1.1.1.1
Routing entry for 1.1.1.1/32
  Known via "bgp 2", distance 20, metric 0
  Tag 65000, type external
  Last update from 140.0.0.202 00:02:05 ago
```




Route Learned via MPLS-Core as expected<br>

[ดูภาพต้นฉบับหน้า 96 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=96)

---

## หน้า 97

###### BGP PE-CE: Private AS vs. Public AS 

- Enterprises that get connected to the Service Provider MPLS-VPN Network can use a BGP Private-AS number 

- The Private BGP-AS number will be hidden from the Global Internet 

- The Customer BGP AS will only be used to connect the different customer entities

[ดูภาพต้นฉบับหน้า 97 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=97)

---

## หน้า 98

#### BGP PE-CE: MCS 

- Certain customers have a mission critical site example a hub that needs to be connected to the MPLS VPN Service Provider to get maximum uptime 

- Such sites need added mechanisms to provide redundancy and at the same time avoid looping.

[ดูภาพต้นฉบับหน้า 98 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=98)

---

## หน้า 99

### BGP PE-CE: Loop in a MCS

```text
MPLS VPN Cloud: PE1, PE2, PE3; provider BGP AS # 1234.
Site 1 contains CE1 and CE2: CE1 — PE1; CE2 — PE2.
Site 3: CE3 — PE3, BGP AS # 1. Site 1 uses BGP AS # 1.
CE1: Advertise BGP Prefix 1.1.1.1.
PE1: Redistribute learned route into MP-BGP;
     Advertise this prefix across MPLS Cloud to all PEs using MP-BGP.
MP-iBGP Update: RD:11:1; Next-Hop=PE-1; RT=All-Sites; Label=100;
               11:1:1.1.1.1/32.
PE2: MP-BGP → BGP; PE2 configured With as-override → CE2.
PE3: MP-BGP → BGP → CE3.
```

- Customer Site 1 sends the BGP routes to PE1 

- PE1 advertises to all the iBGP-VPNv4 peers 

- Remote PE (PE2) redistributes those routes into the local BGP peer at their sites because it has as-override configured so it will change the AS Path. 

- CE2 will accept this route because it doesn’t see its AS in the AS-Path and hence we have created a loop in the routing. Why? Because CE2 would have the same route via an IGP and basis AD which route will win ????

[ดูภาพต้นฉบับหน้า 99 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=99)

---

## หน้า 100

#### BGP PE-CE: Site-of-Origin 

- In order to solve this loop problem, SOO was created. 

- Site-of-Origin is an extended community attribute that is attached to a route received from a CE router before being advertised into VPNv4 address family. 

- The receiving PE router matches the received SOO value with the one configured locally. 

- If the values match, receiving PE doesn’t send that route update to the connected CE. 

- SOO is configured per neighbor.

[ดูภาพต้นฉบับหน้า 100 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=100)

---

## หน้า 101

### BGP PE-CE: Site-of-Origin

| Location | Routers / ASN | SoO / update |
| --- | --- | --- |
| Site-1 | CE1; ASN 65001; connects to PE1 | SoO:100:65001; eBGP4 update N3; AS_PATH:100 100 |
| Site-2 | CE2; ASN 65001; connects to PE2 | SoO:100:65002; eBGP4 update N3; AS_PATH:100 100 |
| Provider | PE1, PE2, PE3, PE4; ASN 100 | PE3 → PE4 |
| Site-3 | CE3, CE4; ASN 65001; N3 10.1.1.0/24 | CE4 → PE3; SoO:100:65003; eBGP4 update N3; AS_PATH:65001 |
| PE4 → CE3 | Update marked with a red cross | SoO:100:65003; update blocked |

CE3 ↔ CE4 within Site-3. PE1 → CE1 and PE2 → CE2 carry the N3 advertisements shown.

#### ข้อความที่อ่านได้ในกล่อง debug

```text
BGP(2): 192.168.2.3 soo loop detected for [ช่วง address/status ทับซ้อนและอ่านไม่ชัด] / unreachable
```

#### PE4 output

```text
PE4#show ip bgp vpnv4 vrf sit3 10.1.1.0/24
!
192.168.1.1 (metric 20) from 192.168.1.1 (192.168.1.1)
 Origin incomplete, metric 0, localpref 100, valid, internal
 Extended Community: SoO:100:65003 RT:1:2
```

#### PE3 output

```text
PE3#sh ip bgp vpnv4 vrf Site3 10.1.1.0/24

[snip]
192.168.2.3 from 192.168.2.3 (10.1.1.1)
 Origin incomplete, metric 100600, localpref 100, valid
 Extended Community: SoO:100:65003 RT:100:1
```

> หมายเหตุจากการตรวจ: ภาพที่ฝังใน PDF มีความละเอียดต่ำและวงเส้นทับบางตัวอักษร โดยเฉพาะ debug บรรทัดบน จึงระบุส่วนที่อ่านไม่ได้แทนการเดา; ชื่อ vrf `sit3`/`Site3` เก็บตามกล่องต้นฉบับ

[ดูภาพต้นฉบับหน้า 101 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=101)

---

## หน้า 102

### 3.4 OSPF Routing

[ดูภาพต้นฉบับหน้า 102 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=102)

---

## หน้า 103

#### OSPF PE-CE Requirements 

- In MPLS-VPN environment, PE Routers are part of the OSPF AREA 0 (SuperBackbone) 

- If OSPF Domain has Area 0 routers, then at least one of those MUST be a CE router and MUST have an Area 0 link to at least one PE Router 

- PE MUST support one OSPF instance for each OSPF domain to which it attaches 

- If PE is running OSPF as its IGP, the instance of OSPF running must be separate and independent from OSPF as PE-CE

[ดูภาพต้นฉบับหน้า 103 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=103)

---

## หน้า 104

### OSPF PE-CE—MP-BGP Extensions 

Extensions to MP-BGP to Carry OSPF Routes: 

- OSPF Router-ID 

   - Each OSPF Instance has a Unique Rtr-ID 

- Domain-Identifier 

   - 8-Byte value that is a valid BGP EXT Community attribute 

   - Identifies the how the prefix originated 

- Route-Type 

   - 8-Byte value includes Area number, OSPF Route-Type (Intra-Inter-External-NSSA) 

- DN Bit 

   - Used for Loop prevention for Type 3 LSAs 

   - MUST be set when it is sent by PE to CE 

- Route-Tags 

   - MUST be included in the Type 5 LSAs that PE originates as a result of receiving external routes

[ดูภาพต้นฉบับหน้า 104 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=104)

---

## หน้า 105

### OSPF PE-CE—MP-BGP Extensions

```text
PE12# show ip bgp vpnv4 all 22.22.22.22
BGP routing table entry for 12:1:22.22.22.22/32, version 88
   140.0.0.201 (via OSPF-Sham) from 0.0.0.0 (12.12.12.12)
      Origin incomplete, metric 10, localpref 100, weight 32768,
 valid, sourced, best
      Extended Community: RT:1:1 OSPF DOMAINID:0x0005:0x000000010200
        OSPF RT:0.0.0.0:5:1 OSPF ROUTER ID:12.12.12.12:512
```

| OSPF Route Type Extended Community value | Caption |
| --- | --- |
| 5 | External Route |
| 1 | Extern Type 2 |
| 2 | Inter-Area |

Other diagram captions: **OSPF Router ID**, **OSPF Domain ID**.

```text
PE11# show ip bgp vpnv4 all 2.2.2.2
OSPF RT:0.0.0.0:2:0 OSPF ROUTER
ID:12.12.12.12:512
```

> หมายเหตุจากการตรวจ: ในภาพลูกศรของกล่อง OSPF Router ID และ OSPF Domain ID ดูสลับตำแหน่งกับชื่อ field; เก็บข้อความ field และ caption ตามต้นฉบับ โดยไม่สลับค่าเอง

[ดูภาพต้นฉบับหน้า 105 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=105)

---

## หน้า 106

### OSPF PE-CE Operation

```text
MPLS VPN Cloud: PE1, PE2, PE3.
Site 1: CE1 — PE1; Site 2: CE2 — PE2; Site 3: CE3 — PE3.
CE1: Advertise OSPF Prefix → PE1.
PE1: Redistribute OSPF learned route into MP-BGP;
     Advertise this prefix across MPLS Cloud to all PEs using MP-BGP.
PE2: BGP → OSPF → CE2.
PE3: BGP → OSPF → CE3.
```

[ดูภาพต้นฉบับหน้า 106 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=106)

---

## หน้า 107

###### OSPF PE-CE Operation : Down BIT and Tag 

- The MPLS VPN model has 3 levels of hierarchy and this poses some challenges during redistribution and flooding which did not exit in the 2 level model of OSPF. 

- In the normal OSPF the area prefixes are advertised in the backbone and vice-versa using summary type 3 LSAs 

- The fact that only backbone summary LSA are considered or that LSA generation is suppressed in some cases we never have flooding loops. 

- These techniques are not sufficient in this model.

[ดูภาพต้นฉบับหน้า 107 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=107)

---

## หน้า 108

### OSPF - Routing Loop

```text
MPLS-VPN Backbone: PE-1, PE-2, PE-3.
Left customer Area 0: PE-1 — CE-1; Network = 110.1.1.1.
Right customer Area 0: CE-2 connected to both PE-2 and PE-3.
VPN-IPv4 Update from PE-1:
  RD:110.1.1.1, Next-hop=PE-1; RT=xxx:xxx
VPN-IPv4 Update from PE-3:
  RD:110.1.1.1, Next-hop=PE-3; RT=xxx:xxx
Two Type-3 (Summary-LSA) boxes on the right:
  Link-State-ID: 110.1.1.1; Adv. Router: PE-2
```

ภาพแสดงการส่ง update จาก PE-1 ไป PE-2/PE-3 และลูกศรย้อนจาก CE-2 ไป PE-3 เข้าสู่ backbone ทำให้เกิด loop

[ดูภาพต้นฉบับหน้า 108 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=108)

---

## หน้า 109

#### OSPF Down Bit and Tag 

- Down bit and Tag are used to prevent looping and on by default. 

- The Down bit is bit 7 in the option field of an LSA

- The Down bit is set by the PE on the LSAs describing routes coming from the BGP redistribution and need to get propagated. 

- When a PE receives a route from the CE, it will generate a summary LSA into the MPLS-VPN BB if and only if the Down-bit is not set on that LSA 

- Down bit processing is only done on PE 

- Down-bit check can be disabled by configuration

[ดูภาพต้นฉบับหน้า 109 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=109)

---

## หน้า 110

### OSPF - Routing Loop avoidance

```text
MPLS-VPN Backbone: PE-1, PE-2, PE-3.
Left customer Area 1: PE-1 — CE-1; Network = Net-1.
Right customer Area 2: CE-2 connected to both PE-2 and PE-3.
VPN-IPv4 Update from PE-1:
  RD:110.1.1.1, Next-hop=PE-1; RT=xxx:xxx
VPN-IPv4 Update from PE-3:
  RD:110.1.1.1, Next-hop=PE-3; RT=xxx:xxx
Two Type-3 (Summary-LSA) boxes on the right:
  Link-State-ID: 110.1.1.1; Adv. Router: PE-2
```

Both VPN-IPv4 update boxes also show `OSPF-Route-Type= 1:2:0` and `OSPF-Domain: xxx`. Both Type-3 boxes show **Down bit is set**. Red crosses mark the returning paths at PE-2/PE-3; the VPN-IPv4 update from PE-3 is crossed out.

[ดูภาพต้นฉบับหน้า 110 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=110)

---

## หน้า 111

### OSPF - Down bit example

```text
MPLS-VPN Backbone: PE-1 — PE-2.
Customer Area 1: CE-1 — CE-2 — C-2 — C-1 — CE-1.
PE-1 — CE-1; PE-2 — CE-2.
```

1. Type-1 Router-LSAs **or** Type-2 Network-LSAs: LSID:140.1.1.1; Adv. Router:x.x.x.x. Advertisement toward PE-1.
2. VPN-IPv4 Update: RD:140.1.1.1, Next-hop=PE-1; RT=xxx:xxx; OSPF-Route-Type=0.0.0.1:3:0; OSPF-Domain:xxx.
3. Same VPN-IPv4 Update at PE-2: RD:140.1.1.1, Next-hop=PE-1; RT=xxx:xxx; OSPF-Route-Type=0.0.0.1:3:0; OSPF-Domain:xxx.
4. PE-2 → CE-2: Type-3 (Summary-LSA); Down bit is set; LSID:140.1.1.1; Adv. Router:PE-2.
5. Return toward PE-1: Type-3 (Summary-LSA); Down bit is set; LSID:140.1.1.1; Adv. Router:PE-2.
6. PE-1 will ignore any LSA with the Down-bit set since they refers to a route which has already be injected from the MPLS-VPN backbone into customer site.

[ดูภาพต้นฉบับหน้า 111 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=111)

---

## หน้า 112

#### OSPF - VPN Route Tag 

- The TAG is the equivalent of the down bit for type 5 and used to prevent looping 

- The Tag value may be configured or computed automatically for a VPN and is the same across the same OSPF domain. 

- Each OSPF domain should have a unique TAG value 

- The Tag is a 32 bit field in the type 5 LSA. 

- The Tag is set on the Type 5  LSA by the PE to indicate the flooding from a higher to a lower level 

- If a tag match is found on a Type 5 LSA, this LSA will not be considered for route computation on a PE.

[ดูภาพต้นฉบับหน้า 112 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=112)

---

## หน้า 113

### OSPF - Routing loop avoidance

```text
AS 1; MPLS-VPN Backbone: PE-1, PE-2, PE-3.
Left Area 1: PE-1 — CE-1; Network = Net-1.
Right Area 2: CE-2 connects to PE-2 and PE-3.
CE-1 → PE-1: Type-5 external LSA; Link-ID:175.1.1.1;
             Adv. Router:CE-1; Metric:20.
VPN-IPv4 Update from PE-1:
  RD:175.1.1.1; Next-hop=PE-1; RT=xxx:xxx; MED=20;
  OSPF-Route-Type=0:5:1; OSPF-Router-ID=PE-1; OSPF-Domain:xxx.
Crossed-out VPN-IPv4 Update from PE-3:
  RD:175.1.1.1; Next-hop=PE-3; RT=xxx:xxx; MED=20;
  OSPF-Route-Type=0:5:1; OSPF-Router-ID=PE-3; OSPF-Domain:xxx.
Both right-side Type-5 (External-LSA) boxes:
  Link-State-ID:175.1.1.1; Adv. Router:PE-2; Metric:20;
  External Route Tag:3489660929;
  TAG Complete, Path Length == 1, AS 1.
```

Red crosses mark the returning paths at PE-2/PE-3; the update from PE-3 into the backbone is crossed out.

[ดูภาพต้นฉบับหน้า 113 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=113)

---

## หน้า 114

### OSPF - Tag example

```text
MPLS-VPN Backbone: PE-1 — PE-2.
Area 1: PE-1 — CE-1 — C-1; Network = 150.1.1.1.
Area 2: PE-2 — CE-2.
```

1. Type-5 External-LSAs: LSID:150.1.1.1; Adv. Router:C-1 → PE-1.
2. VPN-IPv4 Update from PE-1: RD:150.1.1.1, Next-hop=PE-1; RT=xxx:xxx; OSPF-Domain:100; OSPF-Route-Type=0.0.0.1:5:1.
3. Same VPN-IPv4 Update at PE-2: RD:150.1.1.1, Next-hop=PE-1; RT=xxx:xxx; OSPF-Domain:100; OSPF-Route-Type=0.0.0.1:5:1.
4. PE-2 → CE-2: Type-5 (External-LSA), OSPF TAG:100, LSID:150.1.1.1, Adv. Router:PE-2; and Type-4 (ASBR-LSA), Link-State-ID:PE-2, Adv. Router:PE-2.
5. Return toward PE-1: Type-5 (External-LSA), OSPF TAG:100, LSID:150.1.1.1, Adv. Router:PE-2; and Type-4 (ASBR-LSA), Link-State-ID:PE-2, Adv. Router:PE-2.
6. PE-1 will ignore any External LSA (Type-5) with OSPF TAG having provider ASN (i.e.: OSPF domain TAG). Type-4 LSAs are never propagated into MP-BGP anyway.

[ดูภาพต้นฉบับหน้า 114 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=114)

---

## หน้า 115

#### Customer Sites Are All in Area 0 

```text
MPLS VPN Cloud: PE1, PE2, PE3.
Site 1: CE1 — PE1 (Area 0).
Site 2: CE2 — PE2 (Area 0).
Site 3: CE3 — PE3 (Area 0).
Colored route advertisement arrows from each site reach the other CE routers.
```

- MPLS VPN Cloud is OSPF area 0 (Super Backbone) 

- PE Routers act as a ABR (Area Border Routers) 

- PE Routers redistribute OSPF routes into MPLSVPN cloud as a Summary 3 LSA

[ดูภาพต้นฉบับหน้า 115 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=115)

---

## หน้า 116

### Customer Sites Are All in Area 0

#### Left configuration block

```text
interface Loopback0
 ip address 12.12.12.12 255.255.255.255
!
ip vrf OSPF-PECE
 rd 12:1
 route-target export 1:1
 route-target import 1:1
!
mpls label protocol ldp
!
router ospf 1 vrf OSPF-PECE
 router-id 12.12.12.12
 redistribute bgp 65000 subnets
 network 140.0.0.200 0.0.0.3 area 0
```

#### Right configuration block

```text
router bgp 65000
 no bgp default ipv4-unicast
 neighbor 11.11.11.11 remote-as 65000
 neighbor 11.11.11.11 update-source Loopback0
!
 address-family vpnv4
  neighbor 11.11.11.11 activate
  neighbor 11.11.11.11 send-community extended
 exit-address-family
!
 address-family ipv4 vrf OSPF-PECE
  redistribute connected
  redistribute ospf 1 vrf OSPF-PECE
  no synchronization
 exit-address-family
```

[ดูภาพต้นฉบับหน้า 116 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=116)

---

## หน้า 117

#### Customer Sites Are All in Area 0 

```
CE1#show ip route ospf
O IA  2.2.2.2 [110/97] via 140.0.0.2, 00:18:26, Serial2/0
O IA  3.3.3.3 [110/97] via 140.0.0.2, 00:18:11, Serial2/0
```



```
CE1#show ip route 2.2.2.2
Known via "ospf 1", distance 110, metric 97, type inter area
  Last update from 140.0.0.2 on Serial2/0, 00:20:50 ago
CE1#show ip route 3.3.3.3
Known via "ospf 1", distance 110, metric 97, type inter area
  Last update from 140.0.0.2 on Serial2/0, 00:22:55 ago
```

<mark>Summary LSA from the MPLS VPN Backbone</mark>

[ดูภาพต้นฉบับหน้า 117 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=117)

---

## หน้า 118

###### Customer Sites Are in Different Areas 

```text
MPLS VPN Cloud: PE1, PE2, PE3.
Site 1: CE1 — PE1 (Area 1).
Site 2: CE2 — PE2 (Area 2).
Site 3: CE3 — PE3 (Area 3).
Colored route advertisement arrows from each site reach the other CE routers.
```

- Customer Sites are in different areas 

- MPLS-VPN backbone is a Super Backbone

[ดูภาพต้นฉบับหน้า 118 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=118)

---

## หน้า 119

#### Customer Sites Are in Different Areas 

###### `CE1#` **`show ip route ospf`** 

```
O IA   2.2.2.2 [110/97] via 140.0.0.2, 00:01:02, Serial2/0
O IA   3.3.3.3 [110/97] via 140.0.0.2, 00:01:02, Serial2/0
CE1#show ip route 2.2.2.2
Known via "ospf 1", distance 110, metric 97, type inter area
  Last update from 140.0.0.2 on Serial2/0, 00:04:02 ago
CE1#show ip route 3.3.3.3
Known via "ospf 1", distance 110, metric 97, type inter area
  Last update from 140.0.0.2 on Serial2/0, 00:04:08 ago
```

<mark>Summary LSA from the MPLS VPN Backbone</mark>

[ดูภาพต้นฉบับหน้า 119 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=119)

---

## หน้า 120

###### Customer Sites With Back Door Links 

```text
MPLS VPN Cloud: PE1, PE2, PE3.
Site 1: CE1 — PE1 (Area 0).
Site 2: CE2 — PE2 (Area 2).
Site 3: CE3 — PE3 (Area 3).
Colored route advertisement arrows from each site reach the other CE routers.
Back door links: CE1 — CE2 — CE3; both links labelled Area 0.
```

- Customer Sites have the Back Door links 

- If the backdoor links are in the same area as the PE-CE link(s), then the backdoor links will be preferred over the MPLS-Core 

- This is due to PE routers will advertise the Summary-route to CEs causing the Intra-Area routes preferred over the Inter-Area routes

[ดูภาพต้นฉบับหน้า 120 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=120)

---

## หน้า 121

#### Customer Sites With Back Door Links 

```
CE1#show ip route ospf
O  2.2.2.2 [110/101] via 140.0.0.193, 00:00:52, Ethernet0/0
O  3.3.3.3 [110/201] via 140.0.0.193, 00:00:52, Ethernet0/0
CE1#show ip route 2.2.2.2
Known via "ospf 1", distance 110, metric 101, type intra area
  Last update from 140.0.0.193 on Ethernet0/0, 00:08:55 ago
CE1#show ip route 3.3.3.3
Known via "ospf 1", distance 110, metric 201, type intra area
  Last update from 140.0.0.193 on Ethernet0/0, 00:09:00 ago
```

Remote Customer site routes are learned via the Back Door links rather than through the MPLS-VPNs network

[ดูภาพต้นฉบับหน้า 121 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=121)

---

## หน้า 122

###### Sham-Link Support for the Back Door Links 

```text
MPLS VPN Cloud: PE1, PE2, PE3.
Site 1: CE1 — PE1 (Area 0).
Site 2: CE2 — PE2 (Area 2).
Site 3: CE3 — PE3 (Area 3).
Colored route advertisement arrows from each site reach the other CE routers.
Back door links: CE1 — CE2 — CE3; both links labelled Area X.
Dashed Sham-Link: PE1 — PE2 and PE2 — PE3 across MPLS VPN Cloud.
```

- If Customer sites over Backdoor links belong to same OSPF area, the path over a backdoor link will always be selected because OSPF prefers INTRA Area paths 

- PE routers advertise OSPF Routes learned over the VPN backbone as INTER Area paths 

- With Sham-Link, we can create additional OSPF Intra-Area (logical) link between  ingress and egress VRFs on the relevant PE routers. 

- Sham-Link seen as an INTRA-Area link between PE routers, an OSPF Adjacency is created and DB Exchange occurs across the link. 

- With Metric manipulation MPLS VPN backbone can be made preferable

[ดูภาพต้นฉบับหน้า 122 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=122)

---

## หน้า 123

###### Requirements for Creating ShamLinks 

- Before you create a sham-link between PE routers in an MPLS VPN, you must: 

- Configure a separate /32 address on the remote PE so that OSPF packets can be sent over the VPN backbone to the remote end of the sham-link 

- The /32 address must meet the following criteria: 

   - Belong to a VRF 

   - Not be advertised by OSPF 

   - Be advertised by BGP

[ดูภาพต้นฉบับหน้า 123 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=123)

---

## หน้า 124

#### Checking the Status of Sham-Links 

```
PE11# show ip ospf sham-links
Sham Link OSPF_SL0 to address 12.12.12.122 is up
Area 0 source address 11.11.11.111
  Run as demand circuit
  DoNotAge LSA allowed. Cost of using 1 State POINT_TO_POINT,
  Timer intervals configured, Hello 10, Dead 40, Wait 40,
    Hello due in 00:00:05
    Adjacency State FULL (Hello suppressed)
```



<mark>We see that the Sham-Link is UP with Area 0</mark>

[ดูภาพต้นฉบับหน้า 124 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=124)

---

## หน้า 125

#### Checking the Status of Sham-Links 

```
CE1#show ip route ospf
O   2.2.2.2 [110/98] via 140.0.0.2, 00:12:41, Serial2/0
O   3.3.3.3 [110/99] via 140.0.0.2, 00:12:41, Serial2/0
```



```
CE1#show ip route 2.2.2.2
Known via "ospf 1", distance 110, metric 98, type intra area
Last update from 140.0.0.2 on Serial2/0, 00:11:26 ago
CE1#show ip route 3.3.3.3
Known via "ospf 1", distance 110, metric 99, type intra area
Last update from 140.0.0.2 on Serial2/0, 00:14:31 ago
```

With Sham-links in place, the CE routes are being learned via the MPLS-VPN Backbone network.

[ดูภาพต้นฉบับหน้า 125 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=125)

---

## หน้า 126

### Sham-Links Configuration Example

#### Left PE configuration

```text
!
interface Loopback1
 ip vrf forwarding OSPF-Sham
 ip address 11.11.11.111 255.255.255.255
!
router ospf 1 vrf OSPF-Sham
 router-id 11.11.11.11
 log-adjacency-changes
 area 0 sham-link 11.11.11.111 12.12.12.122
 redistribute bgp 65000 subnets
 network 140.0.0.0 0.0.0.3 area 0
!
```

#### Right PE configuration

```text
!
interface Loopback1
 ip vrf forwarding OSPF-Sham
 ip address 12.12.12.122 255.255.255.255
!
router ospf 1 vrf OSPF-Sham
 router-id 12.12.12.12
 log-adjacency-changes
 area 0 sham-link 12.12.12.122 11.11.11.111
 redistribute bgp 65000 subnets
 network 140.0.0.200 0.0.0.3 area 0
!
```

#### PE11 output

```text
PE11#show ip ospf sham-links
Sham Link OSPF_SL0 to address 12.12.12.122 is up
Area 0 source address 11.11.11.111
  Run as demand circuit
  DoNotAge LSA allowed. Cost of using 1 State POINT_TO_POINT,
  Timer intervals configured, Hello 10, Dead 40, Wait 40,
    Hello due in 00:00:00
    Adjacency State FULL (Hello suppressed)
```

#### PE12 output

```text
PE12#show ip ospf sham-links
Sham Link OSPF_SL0 to address 11.11.11.111 is up
Area 0 source address 12.12.12.122
  Run as demand circuit
  DoNotAge LSA allowed. Cost of using 1 State POINT_TO_POINT,
  Timer intervals configured, Hello 10, Dead 40, Wait 40,
    Hello due in 00:00:09
    Adjacency State FULL (Hello suppressed)
```

> หมายเหตุจากการตรวจ: กรอบ output ของต้นฉบับซ้อนกันเล็กน้อย; แยกสอง router และซ่อมลำดับบรรทัดตามภาพ

[ดูภาพต้นฉบับหน้า 126 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=126)

---

## หน้า 127

### 3.5 EIGRP Routing

[ดูภาพต้นฉบับหน้า 127 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=127)

---

## หน้า 128

#### EIGRP PE-CE Goals 

- Impose little requirements or no restrictions on customer networks 

   - CE and C routers are NOT required to run newer code (CE/C upgrades recommended for full SoO functionality)

   - Customer sites may be same or different Autonomous Systems 

   - Customer sites may consist of several connections to the MPLS VPN backbone 

   - Customer sites may consist of one or more connections not part of the MPLS VPN backbone **(“backdoor” links)**

[ดูภาพต้นฉบับหน้า 128 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=128)

---

## หน้า 129

#### EIGRP PE-CE: Operation 

- CE runs EIGRP as before where as PE runs EIGRP-VRF process per VRF/AS 

- EIGRP routes are distributed to customer sites via MP-iBGP on the MPLS-VPN backbone 

- There are no EIGRP adjacencies or EIGRP updates in MPLS/VPN backbone 

- EIGRP information is carried across MPLS/VPN backbone by MP-BGP in new extended communities (set and used by PEs)

[ดูภาพต้นฉบับหน้า 129 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=129)

---

## หน้า 130

###### EIGRP PE-CE: New Extended Communities 

- Cost Community attribute can be applied at various points in the MP-BGP best-path calculation 

- An Opaque Extended Community Type: 0x43 

|Type|Usage|Value|
|---|---|---|
|8800|EIGRP General Route Information|Flags + Tag|
|8801|EIGRP Route Metric Information + AS|AS + Delay|
|8802|EIGRP Route Metric Information|Reliability + Hop + BW|
|8803|EIGRP Route Metric Information|Reserve + Load + MTU|
|8804|EIGRP Ext. Route Information|Remote AS + Remote ID|
|8805|EIGRP Ext. Route Information|Remote Protocol+ Remote Metric|

[ดูภาพต้นฉบับหน้า 130 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=130)

---

## หน้า 131

### EIGRP PE-CE: Looking for Cost Communities

```text
PE11#show ip bgp vpnv4 all 1.1.1.1
BGP routing table entry for 11:1:1.0.0.0/8, version 7
Paths: (1 available, best #1, table EIGRP-Same-AS)
  140.0.0.1 (via EIGRP-Same-AS) from 0.0.0.0 (11.11.11.11)
    Origin incomplete, metric 1889792, localpref 100, weight 32768, valid, sourced, best
    Extended Community: RT:1:1
      Cost:pre-bestpath:128:1889792 (default-2145593855) 0x8800:32768:0
      0x8801:1:640000 0x8802:65281:1249792 0x8803:65281:1500
```

We see that EIGRP Attributes of Delay + BW + Hop Count + Reliability + MTU are carried via MP-BGP Extended Community.

Value **128** represents that route is originated internal to EIGRP domain.

[ดูภาพต้นฉบับหน้า 131 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=131)

---

## หน้า 132

### EIGRP PE-CE: Looking for Cost Communities

```text
PE11#show ip bgp vpnv4 all 111.0.0.0
BGP routing table entry for 11:1:111.0.0.0/8, version 25
Paths: (1 available, best #1, table EIGRP-Same-AS)
  12.12.12.12 (metric 10) from 12.12.12.12 (12.12.12.12)
    Origin incomplete, metric 2274048, localpref 100, valid, internal, best
    Extended Community: RT:1:1
      Cost:pre-bestpath:129:2274048 (default-2145209599) 0x8800:0:0
      0x8801:1:1024256 0x8802:65281:1249792 0x8803:65281:1500
      0x8804:0:1684300900 0x8805:4:1
```

If the route is external to EIGRP AS, we see a value of **129**. We also see two additional pieces of information in the Cost Community value:

- `0x8804` includes External-AS + External Originator ID
- `0x8805` includes External Protocol + External Metric

[ดูภาพต้นฉบับหน้า 132 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=132)

---

## หน้า 133

###### Customer Sites in the Same EIGRP AS 

```text
MPLS VPN Cloud: PE1, PE2.
Site 1: CE1 — PE1; EIGRP AS 1.
Site 2: CE2 — PE2; EIGRP AS 1.
Customer sites belonging to same EIGRP AS.
```

- As CE-Sites are in the same-AS, the routes will be learned with normal EIGRP attributes 

- MP-BGP running on the PEs will carry the EIGRP attributes natively

   - EIGRP AS # 

   - EIGRP Metrics 

   - As part of the BGP update 

- Customer sites will see the remote sites as part of their normal EIGRP domain

[ดูภาพต้นฉบับหน้า 133 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=133)

---

## หน้า 134

###### Customer Sites in the Same EIGRP AS 

```
CE1#show ip route 2.2.2.2
Routing entry for 2.2.2.2/32
  Known via "eigrp 1", distance 90, metric 2913792, type internal
  Last update from 140.0.0.2 on Serial2/0, 00:00:13 ago
      Loading 1/255, Hops 2
CE2#show ip route 1.1.1.1
Routing entry for 1.1.1.1/32
  Known via "eigrp 1", distance 90, metric 2401792, type internal
  Last update from 140.0.0.202 on Serial2/0, 00:03:43 ago
      Loading 1/255, Hops 2
```

Remote Site routes are being on the Local PE routers with <u>Internal EIGRP Admin Distance of</u> **90** and with Hop Count of **2**

[ดูภาพต้นฉบับหน้า 134 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=134)

---

## หน้า 135

###### Customer Sites in the Same EIGRP AS 

```
PE11#show ip eigrp vrf EIGRP-Same-AS topology 1.1.1.1   255.255.255.255
IP-EIGRP topology entry for 1.1.1.1/32
  State is Passive, Query origin flag is 1, 1 Successor(s), FD is 1889792
  Routing Descriptor Blocks:
  140.0.0.1 (Serial2/0), from 140.0.0.1, Send flag is 0x0
      Composite metric is (1889792/128256), Route is Internal
      Vector metric:
        Minimum bandwidth is 2048 Kbit
        Total delay is 25000 microseconds
        Reliability is 255/255
        Load is 1/255
        Minimum MTU is 1500
        Hop count is 1
PE11#show ip eigrp vrf EIGRP-Same-AS topology 2.2.2.2   255.255.255.255
IP-EIGRP topology entry for 2.2.2.2/32
  State is Passive, Query origin flag is 1, 1 Successor(s), FD is 2401792
  Routing Descriptor Blocks:
  0.0.0.0, from 0.0.0.0, Send flag is 0x0
      Composite metric is (2401792/0), Route is Internal (VPNv4 Sourced)
      Vector metric:
        Minimum bandwidth is 2048 Kbit
        Total delay is 45000 microseconds
        Reliability is 255/255
        Load is 1/255
        Minimum MTU is 1500
        Hop count is 1
```

<mark>PE Router is carrying all the EIGRP attributes in the learned via MP-BGP</mark> **<u>1.1.1.1/32</u>** is locally learned via EIGRP from CE1 **<u>2.2.2.2/32</u>** is learned via MP-BGP from remote-PE and redistributed into the EIGRP-VRF on local Router

[ดูภาพต้นฉบับหน้า 135 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=135)

---

## หน้า 136

### Customer Sites in the Same EIGRP AS — Configuration Example

#### PE 1

```text
ip vrf EIGRP-Same-AS
 rd 11:1
 route-target export 1:1
 route-target import 1:1
!
router eigrp 100
 !
 address-family ipv4 vrf EIGRP-Same-AS
  redistribute bgp 65000 metric 10000 1 255 1 1500
  network 140.0.0.0
 no auto-summary
  autonomous-system 1
 exit-address-family
!
router bgp 65000
 no bgp default ipv4-unicast
 bgp log-neighbor-changes
 neighbor 12.12.12.12 remote-as 65000
 neighbor 12.12.12.12 update-source Loopback0
 !
 address-family vpnv4
  neighbor 12.12.12.12 activate
  neighbor 12.12.12.12 send-community extended
 exit-address-family
 !
 address-family ipv4 vrf EIGRP-Same-AS
  redistribute eigrp 1
  no synchronization
 exit-address-family
!
```

#### PE 2

```text
ip vrf EIGRP-Same-AS
 rd 12:1
 route-target export 1:1
 route-target import 1:1
!
router eigrp 100
 !
 address-family ipv4 vrf EIGRP-Same-AS
  redistribute bgp 65000 metric 10000 1 255 1 1500
  network 140.0.0.0
 no auto-summary
  autonomous-system 1
 exit-address-family
!
router bgp 65000
 no bgp default ipv4-unicast
 bgp log-neighbor-changes
 neighbor 11.11.11.11 remote-as 65000
 neighbor 11.11.11.11 update-source Loopback0
 !
 address-family vpnv4
  neighbor 11.11.11.11 activate
  neighbor 11.11.11.11 send-community extended
 exit-address-family
 !
 address-family ipv4 vrf EIGRP-Same-AS
  redistribute eigrp 1
  no synchronization
 exit-address-family
!
```

> หมายเหตุจากการตรวจ: คำสั่ง redistribute metric ในต้นฉบับตัด 1500 ลงบรรทัดใหม่เพราะพื้นที่คอลัมน์; รวมกลับเป็นบรรทัดเดียว

[ดูภาพต้นฉบับหน้า 136 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=136)

---

## หน้า 137

###### Customer Sites in Different EIGRP AS 

```text
MPLS VPN Cloud: PE1, PE2.
Site 1: CE1 — PE1; EIGRP AS 1.
Site 2: CE2 — PE2; EIGRP AS 2.
Customer sites belonging to different EIGRP AS.
```

- Customer sites are in different EIGRP AS 

- CE Sites will learn the remote-CE-site routes as external routes 

- This is normal behavior due to the different EIGRP AS 

- MP-BGP on the PE routers will carry the EIGRP routes with their normal attributes

[ดูภาพต้นฉบับหน้า 137 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=137)

---

## หน้า 138

### Customer Sites in Different EIGRP AS

```text
CE1#show ip route 2.2.2.2
Routing entry for 2.2.2.2/32
  Known via "eigrp 1", distance 170, metric 1762048, type external
  Last update from 140.0.0.2 on Serial2/0, 00:00:22 ago
      Loading 1/255, Hops 1

CE2#show ip route 1.1.1.1
Routing entry for 1.1.1.1/32
  Known via "eigrp 2", distance 170, metric 1762048, type external
  Last update from 140.0.0.202 on Serial2/0, 00:00:16 ago
      Loading 1/255, Hops 1
```

Remote Site routes are being on the Local PE routers with External EIGRP Admin Distance of **170** and with Hop Count of **1**.

[ดูภาพต้นฉบับหน้า 138 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=138)

---

## หน้า 139

###### **Customer Sites in Different EIGRP AS** 

```
PE11#show ip eigrp vrf EIGRP-Diff-AS topology 1.1.1.1 255.255.255.255
IP-EIGRP topology entry for 1.1.1.1/32
  State is Passive, Query origin flag is 1, 1 Successor(s), FD is
1889792
  Routing Descriptor Blocks:
  140.0.0.1 (Serial2/0), from 140.0.0.1, Send flag is 0x0
      Composite metric is (1889792/128256), Route is Internal
      Vector metric:
        Minimum bandwidth is 2048 Kbit
        Total delay is 25000 microseconds
  Reliability is 255/255
        Load is 1/255
        Minimum MTU is 1500
        Hop count is 1
PE11# show ip eigrp vrf EIGRP-Diff-AS topology 2.2.2.2
255.255.255.255
IP-EIGRP topology entry for 2.2.2.2/32
  State is Passive, Query origin flag is 1, 1 Successor(s), FD is
256256
  Routing Descriptor Blocks:
  0.0.0.0, from Redistributed, Send flag is 0x0
      Composite metric is (256256/0), Route is External
      Vector metric:
        Minimum bandwidth is 10000 Kbit
        Total delay is 10 microseconds
        Reliability is 255/255
        Load is 1/255
        Minimum MTU is 1500
        Hop count is 0
      External data:
        Originating router is 140.0.0.2 (this system)
        AS number of route is 65000
        External protocol is BGP, external metric is 2401792
        Administrator tag is 0 (0x00000000)
```



**<u>1.1.1.1/32</u>** is locally learned via EIGRP from CE1 

**<u>2.2.2.2/32</u>** is learned via MP-BGP from remote-PE and redistributed into the EIGRP-VRF on local Router.  This is an external route from the EIGRP domain and the info. carried in the EIGRP-VRF topology. 

BRKRST-2332_c1 

© 2010 Cisco and/or its affiliates. All rights reserved. Cisco Public 

139

[ดูภาพต้นฉบับหน้า 139 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=139)

---

## หน้า 140

### Customer Sites in Different EIGRP AS — Configuration Example

#### PE 1

```text
ip vrf EIGRP-Diff-AS
 rd 11:1
 route-target export 1:1
 route-target import 1:1
!
router eigrp 100
 !
 address-family ipv4 vrf EIGRP-Diff-AS
  redistribute bgp 65000 metric 10000 1 255 1 1500
  network 140.0.0.0
  autonomous-system 1
 exit-address-family
!
router bgp 65000
 no bgp default ipv4-unicast
 bgp log-neighbor-changes
 neighbor 12.12.12.12 remote-as 65000
 neighbor 12.12.12.12 update-source Loopback0
 !
 address-family vpnv4
  neighbor 12.12.12.12 activate
  neighbor 12.12.12.12 send-community extended
 exit-address-family
 !
 address-family ipv4 vrf EIGRP-Diff-AS
  redistribute eigrp 1
  no synchronization
 exit-address-family
!
```

#### PE 2

```text
ip vrf EIGRP-Diff-AS
 rd 12:1
 route-target export 1:1
 route-target import 1:1
!
router eigrp 100
 !
 address-family ipv4 vrf EIGRP-Diff-AS
  redistribute bgp 65000 metric 10000 1 255 1 1500
  network 140.0.0.0
  autonomous-system 2
 exit-address-family
!
router bgp 65000
 no bgp default ipv4-unicast
 bgp log-neighbor-changes
 neighbor 11.11.11.11 remote-as 65000
 neighbor 11.11.11.11 update-source Loopback0
 !
 address-family vpnv4
  neighbor 11.11.11.11 activate
  neighbor 11.11.11.11 send-community extended
 exit-address-family
 !
 address-family ipv4 vrf EIGRP-Diff-AS
  redistribute eigrp 2
  no synchronization
 exit-address-family
!
```

[ดูภาพต้นฉบับหน้า 140 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=140)

---

## หน้า 141

###### Customer Sites With Backdoor Links 

```text
MPLS VPN Cloud: PE1, PE2.
Site 1 EIGRP AS 1: PE1 — CE1 — C3 — C4.
Site 2 EIGRP AS 1: PE2 — CE2.
C4 — Backdoor Link — CE2.
Caption: Customer Sites with Backdoor Links.
```

- Customer wants to use the MPLS-VPN core for the Sites connectivity 

- Use the Back-door links in case of a failure (they usually are lowspeed links) 

- Use EIGRP attributes on the backdoor link for the Sites Connectivity (for example: delay) 

- Everything should work as expected in case of a loss of connectivity through the MPLS-VPN Core

[ดูภาพต้นฉบับหน้า 141 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=141)

---

## หน้า 142

###### Customer Sites Have One or More Non-EIGRP Site(s) 

```text
MPLS VPN Cloud: PE1, PE2, PE3.
Site 3 non-EIGRP: CE3 ↔ BGP PE-CE Session ↔ PE3.
Site 1 EIGRP AS 1: PE1 — CE1 — C4.
Site 2 EIGRP AS 1: PE2 — CE2.
C4 — Backdoor Link — CE2.
Caption: Customer Sites with Mixed PE-CE Links.
```

- In this, Site 3 is connected to a remote PE rather than to the local-PE where the EIGRP Site is connected 

- **Goal** : Remains the same—Non-EIGRP sites to have the reachability to EIGRP sites vice versa

[ดูภาพต้นฉบับหน้า 142 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=142)

---

## หน้า 143

###### Customer Sites Have One or More Non-EIGRP Site(s) 

```text
MPLS VPN Cloud: PE1, PE2.
Site 3 non-EIGRP: CE3 ↔ BGP PE-CE Session ↔ PE1.
Site 1 EIGRP AS 1: PE1 — CE1 — C4.
Site 2 EIGRP AS 1: PE2 — CE2.
C4 — Backdoor Link — CE2.
Caption: Customer Sites with Mixed PE-CE Links.
```

- If a Customer uses EIGRP and non-EIGRP as PE-CE protocol at different sites, we may see a persistent loop as the prefix originated from the Non-EIGRP site doesn’t have the Cost-Community attribute 

- The loop happens because: 

   1. Initial prefix received doesn’t have the SoO/Cost community 

   2. Leaked into the EIGRP and then to the Remote-PE 

   3. Remote-PE advertises it back to the source-PE with the SoO/Cost Community

   4. Since the SoO/Cost community route is preferred by BGP, the original route is replaced with the new one

[ดูภาพต้นฉบับหน้า 143 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=143)

---

## หน้า 144

### Customer Sites Have One or More Non-EIGRP Site(s) 

- CSCsa81039 addresses this problem 

- Since EIGRP has the maximum hop count of 100, we can decrease this so that the loop will not be sustained for long period 

```
router eigrp <AS #>
  address-family ipv4 vrf <name>
metric maximum-hops <#>
```

[ดูภาพต้นฉบับหน้า 144 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=144)

---

## หน้า 145

### Customer Sites Have One or More Non-EIGRP Site(s) 

- For the proper routing to happen immediately, it is encouraged to use the following route-map. 

- The route-map with the cost-community needs to be applied on the PE which is connected to the CE directly: (In our Example on PE3 towards CE3) 

```
router bgp <X>
 address-family ipv4 vrf loop-with-non-EIGRP-PE-CE
 neighbor <ip-addr> route-map COST1 in
!
route-map COST1 permit 10
set extcommunity cost pre-bestpath 1 100
```

[ดูภาพต้นฉบับหน้า 145 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=145)

---

## หน้า 146

### 3.6 Deployment Scenarios with BGP

[ดูภาพต้นฉบับหน้า 146 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=146)

---

## หน้า 147

###### Multi-Homing and Load Balancing Options 

- Customers may require as part of their SLAs to have their CE devices to be either dual-homed and/or do some form loadbalancing across the Service Provider Network for lower latency etc. 

- Couple of Examples: 

```text
Example 1: Customer Site contains CE1 and CE2, both attached to one PE in MPLS Core.
Example 2: Customer Site contains CE1 and CE2, each attached to both PEs in MPLS Core.
```

Customer Site is multi-homed via two different CE routers 

Used for the redundancy and Fail-over scenarios 

Customer Site is multi-homed via single CE to two different PEs or Two CEs meshed in with the two PEs 

Used for the redundancy and Fail-over scenarios for Sites that are very Critical

[ดูภาพต้นฉบับหน้า 147 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=147)

---

## หน้า 148

###### Multi-Homing and Load Balancing Options eiBGP Load Balancing: 

```text
CE2 attaches to PE1; CE1 is dual-homed to PE1 and PE2 in MPLS Core.
Highlighted traffic CE2 → PE1 splits:
  eBGP Path: PE1 → CE1
  iBGP Path: PE1 → PE2 → CE1
```

- Customer wants their traffic to be loadbalanced across the MPLS Core 

- Customer Site CE Router(s) is/are multi-homed and they want the traffic from remote sites to be load-balanced across the MPLS core both on the iBGP and eBGP paths 

- This is called eiBGP Multipath and all the configuration is done on the PE Routers 

[ดูภาพต้นฉบับหน้า 148 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=148)

---

## หน้า 149

###### Multi-Homing and Load Balancing Options 

```text
Figure 1: Site 1 CE1 attached to PE1 and PE2; Site 2 CE2 attached to PE1.
  eBGP Path PE1 → CE1; iBGP Path PE1 → PE2 → CE1.
Figure 2: Site 1 CE1 and CE2 each attached to PE1 and PE2; Site 2 CE3 attached to PE1.
  eBGP Path via PE1; iBGP Path via PE2.
```

- **Figure 1** : CE1 is Dual-homed to PE1 and PE2. Traffic coming from CE2 will be loadbalanced by PE1 both on the iBGP path to PE2 and on the directly connected eBGP link to CE1 

- **Figure 2** : Similar to Site 1 in Figure 1 but Site 1 has redundancy at the customer site routers 

- In both the above cases, Site 1 and Site 2 are connected to the same PE router in the MPLS core

[ดูภาพต้นฉบับหน้า 149 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=149)

---

## หน้า 150

###### Multi-Homing and Load Balancing Options 

```text
Figure 3: Site 1 CE1 and CE2 attached to PE1 and PE2; Site 2 CE3 attached to PE3.
  MPLS Core contains PE1, PE2, PE3; eBGP Path via PE1 and iBGP Path via PE2.
Figure 4: Site 1 CE1 attached to PE1 and PE2; Site 2 CE3 attached to PE3; Site 3 CE4 attached to PE4.
  MPLS Core contains PE1–PE4; eBGP Path via PE1/PE2; iBGP Path inside the core.
```

- Here are couple of additional topologies depicting eiBGP load balancing examples 

- **Figure 3** : Site 1 is locally connected to PE1 and PE2 where as Site 2 is connected to PE3 

- **Figure 4** : Multiple Customer remote Sites (Site 2, Site 3) trying to reach Site 1. Loadbalancing should happened with in the MPLS-VPN Core

[ดูภาพต้นฉบับหน้า 150 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=150)

---

## หน้า 151

### eiBGP: At the PE Router

```text
PE11#show ip bgp vpnv4 all 1.1.1.1
BGP routing table entry for 11:1:1.1.1.1/32, version 11
Paths: (2 available, best #2, table eiBGP-multipath)
Multipath: eiBGP
  1, imported path from 12:1:1.1.1.1/32
    12.12.12.12 (metric 10) from 12.12.12.12 (12.12.12.12)
      Origin IGP, metric 0, localpref 100, valid, internal, multipath
      Extended Community: RT:1:1
  1
    140.0.0.2 (via eiBGP-multipath) from 140.0.0.2 (1.1.1.1)
      Origin IGP, metric 0, localpref 100, valid, external, multipath, best
      Extended Community: RT:1:1
```

PE is doing a loadbalancing for the prefix 1.1.1.1/32 both on the eBGP and iBPG path.

> หมายเหตุจากการตรวจ: caption ของต้นฉบับสะกด iBPG; เก็บตามภาพ

[ดูภาพต้นฉบับหน้า 151 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=151)

---

## หน้า 152

###### **eiBGP: At the PE Router** 

```
PE11# show ip route vrf eiBGP-multipath 1.1.1.1
Routing entry for 1.1.1.1/32
  Known via "bgp 65000", distance 20, metric 0
  * 140.0.0.2, from 140.0.0.2, 00:20:14 ago
      AS Hops 1, BGP network version 0
    12.12.12.12 (Default-IP-Routing-Table), from 12.12.12.12, 00:20:01 ago
     AS Hops 1, BGP network version 0
```

```
PE11#show ip cef vrf eiBGP-multipath 1.1.1.1
1.1.1.1/32, version 13, epoch 0, per-destination sharing
  via 140.0.0.2, 0 dependencies, recursive
    next hop 140.0.0.2, Serial2/0 via 140.0.0.0/30 (eiBGP-multipath)
    valid adjacency
    tag rewrite with Se2/0, point2point, tags imposed {}
  via 12.12.12.12, 0 dependencies, recursive
    next hop 130.0.0.2, Ethernet0/0 via 12.12.12.12/32 (Default)
    valid adjacency
    tag rewrite with Et0/0, 130.0.0.2, tags imposed {35}
```

We see both the IP-VRF RIB and VRF-CEF are doing the loadbalancing for the prefix 1.1.1.1/32 reflecting the BGP-VPNv4-RIB. 

BRKRST-2332_c1 

© 2010 Cisco and/or its affiliates. All rights reserved. Cisco Public 

152

[ดูภาพต้นฉบับหน้า 152 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=152)

---

## หน้า 153

### eiBGP: PE Router Configuration

```text
router bgp 65000
 neighbor 12.12.12.12 remote-as 65000
 neighbor 12.12.12.12 update-source Loopback0
 neighbor 13.13.13.13 remote-as 65000
 neighbor 13.13.13.13 update-source Loopback0
!
 address-family vpnv4
  neighbor 12.12.12.12 activate
  neighbor 12.12.12.12 send-community extended
  neighbor 13.13.13.13 activate
  neighbor 13.13.13.13 send-community extended
 exit-address-family
!
 address-family ipv4 vrf eiBGP-multipath
  redistribute connected
  neighbor 140.0.0.2 remote-as 1
  neighbor 140.0.0.2 activate
  neighbor 140.0.0.2 as-override
  maximum-paths eibgp 2
  no synchronization
 exit-address-family
```

eiBGP Multipath is configured under the AF IPv4-VRF 



There is no any additional configuration is needed on the Customer routers (CE) 

A specific case where the customer wants their return traffic to be load balanced across the MPLS core using iBGP and eBGP paths 

BRKRST-2332_c1 

© 2010 Cisco and/or its affiliates. All rights reserved. 

Cisco Public 

153

[ดูภาพต้นฉบับหน้า 153 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=153)

---

## หน้า 154

###### Loadbalancing Across Dual Providers 

```text
Customer Server Farms and/or Applications connect Customer XYZ HUB Site 1 (Hub1) and HUB Site 2 (Hub2).
MPLS-VPN Service Provider 1: PE2SP1 toward both Hub1/Hub2; PE1SP1 toward CE1/CE2/CE3.
MPLS-VPN Service Provider 2: PE2SP2 toward both Hub1/Hub2; PE1SP2 toward CE1/CE2/CE3.
Customer XYZ Site 1: CE1; Site 2: CE2; Site 3: CE3.
All three CE routers connect to both providers.
Small labels partly hidden behind the three CE icons repeat “Customer XYZ Site 1” in the source.
```

- Customer sites are connected to two Service Providers 

- Customer wants to do some form of load balancing across the dual SP Providers 

- This is for all the traffic originating both from the Spoke Sites to Hub sites vice versa

[ดูภาพต้นฉบับหน้า 154 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=154)

---

## หน้า 155

### Loadbalancing Across Dual Providers

```text
CE2#show ip bgp 1.1.1.1
BGP routing table entry for 1.1.1.1/32, version 17
Paths: (2 available, best #1)
Multipath: eBGP
  65535 65535
    130.0.32.23 from 130.0.32.23 (23.23.23.23)
      Origin IGP, localpref 100, valid, external, multipath, best
  65535 65535
    130.0.2.13 from 130.0.2.13 (13.13.13.13)
      Origin IGP, localpref 100, valid, external, multipath

CE2#show ip route
B    1.1.1.1 [20/0] via 130.0.2.13, 00:28:21
            [20/0] via 130.0.32.23, 00:22:11
```

We see that the Remote site prefix is learned via eBGP using multipath at the Site 2.   Both the AS Path Lengths have to match and have to be the same in order for the eBGP Multipath to work. 

<mark>This require SPs to agree on the AS Path Policy for the given customer</mark> 

BRKRST-2332_c1 

© 2010 Cisco and/or its affiliates. All rights reserved. Cisco Public 

155

[ดูภาพต้นฉบับหน้า 155 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=155)

---

## หน้า 156

### Loadbalancing Across Dual Providers

A Typical Configuration on the SP PE Router Will Look Like: 

```
router bgp 12345
address-family ipv4 vrf TEST
 redistribute connected
 neighbor 130.0.32.2 remote-as 65200
 neighbor 130.0.32.2 local-as 65535 no-prepend replace-as
 neighbor 130.0.32.2 activate
 neighbor 130.0.32.2 as-override
 no synchronization
 exit-address-family
!
```

With **Local-AS** option, the Customer Dual-SP will use the same AS number to peer with the customer CE routers 

With **No-Prepend** option, local-as is not going to be prepended to update from eBGP peers 

With **Replace-AS** option, replace real AS with local AS in the eBGP Updates

**AS-Override** option is used to replace the customer AS # with SP AS # when they use the Same AS at different customer Sites 

BRKRST-2332_c1 

© 2010 Cisco and/or its affiliates. All rights reserved. Cisco Public 

156

[ดูภาพต้นฉบับหน้า 156 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=156)

---

## หน้า 157

###### **Loadbalancing Across Dual Providers** 

```
PE1# show ip bgp vpnv4 all 8.8.8.8
BGP routing table entry for 65000:65000:8.8.8.8/32, version 11
Paths: (1 available, best #1, table TEST)
65200 65000
    130.0.11.1 (via boa) from 130.0.11.1 (1.1.1.1)
      Origin IGP, localpref 100, valid, external, best
      Extended Community: RT:65000:65000
```

```
BGP(0): 130.0.11.1 rcv UPDATE about 8.8.8.8/32 -- DENIED due to: AS-PATH contains our own AS
```

PE accepts the route matching with its own AS # due to the knob of **allowas-in** option 

In the debug we see that the prefix is DENIED if the allowas-in option is not turned on. 

BRKRST-2332_c1 

© 2010 Cisco and/or its affiliates. All rights reserved. 

Cisco Public 

157

[ดูภาพต้นฉบับหน้า 157 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=157)

---

## หน้า 158

###### **Loadbalancing Across Dual Providers** 

```text
CE2# show ip bgp 8.8.8.8
BGP routing table entry for 8.8.8.8/32, version 11
Multipath: eBGP
65535 65535 65000
    130.0.32.23 from 130.0.32.23 (23.23.23.23)
      Origin IGP, localpref 100, valid, external,  multipath ,  best
65535 65535 65000
    130.0.2.13 from 130.0.2.13 (13.13.13.13)
      Origin IGP, localpref 100, valid, external,  multipath
CE2# show ip route 8.8.8.8
Routing entry for 8.8.8.8/32
  Known via "bgp 65200", distance 20, metric 0
  *  130.0.2.13 , from 130.0.2.13, 00:00:17 ago
      AS Hops 3, BGP network version 0
      Route tag 65535
130.0.32.23 , from 130.0.32.23, 00:00:16 ago
      AS Hops 3, BGP network version 0
      Route tag 65535
```

###### <mark>The prefix 8.8.8.8/32 is being Load balanced using the eBGP Multipath</mark> 

BRKRST-2332_c1 

© 2010 Cisco and/or its affiliates. All rights reserved. 

Cisco Public 

158

[ดูภาพต้นฉบับหน้า 158 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=158)

---

## หน้า 159

### 3.6 



##### Deployment Scenarios with OSPF 

BRKRST-2332_c1 

© 2010 Cisco and/or its affiliates. All rights reserved. 

Cisco Public 

159

[ดูภาพต้นฉบับหน้า 159 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=159)

---

## หน้า 160

###### **OSPF Area 0 Placement** 

```text
OSPF Super Backbone / MPLS VPN Cloud: PE1 ↔ VPNv4 Update ↔ PE2.
Site 1: PE1 — Area 0 — CE1 — Area 2.
Site 2: PE2 — Area 1 — CE2.
CE2 → PE2: Type 1 or 2 LSA.
CE1 → Area 2: Type 3 LSA.
```

- Placing of the Customer OSPF Area 0 is very important 

- If a Customer Site has area 0, it MUST touch the MPLS-VPN PE Router 

- In the above example, some site(s) consist of non-OSPF area 0 as well as area 0 Sites 

- A type 1 or 2 LSA coming from non-OSPF area 0 will be flooded as a type 3 LSA 

[ดูภาพต้นฉบับหน้า 160 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=160)

---

## หน้า 161

###### **OSPF Area 0 Placement** 

```text
OSPF Super Backbone / MPLS VPN Cloud: PE1 ↔ VPNv4 Update ↔ PE2.
Site 1: PE1 — Area 2 — CE1 — Area 0.
Site 2: PE2 — Area 1 — CE2.
CE2 → PE2: Type 1 or 2 LSA.
PE1 → CE1: Type 3 LSA; CE1 → Area 0: Type 3 LSA.
Caption: Summary routes are not advertised into OSPF Area 0.
Virtual Link connects customer Area 0 to PE1.
```

- In the above topology, the customer OSPF area 0 is not directly connected to the PE 

- A type 1 or 2 LSA, coming from MPLS-VPN superbackbone will be summarized and be sent as a Type 3 LSA into area 2. 

- Then area 2 will send this type 3 LSA into  AREA 0 below AND 

- Summary routes are not advertised (back) into  Area 0 

- In this case, you need a Virtual-link to connect the Area 0 

- Recommended to: Have the OSPF AREA 0 connected to the MPLS-VPN Core 

[ดูภาพต้นฉบับหน้า 161 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=161)

---

## หน้า 162

###### **OSPF Area 0 Placement—Sham Link** 

```text
OSPF Super Backbone / MPLS VPN Cloud: PE1 ↔ VPNv4 Update ↔ PE2.
Site 1: PE1 — Area 0 — CE1; Site 2: PE2 — Area 1 — CE2.
CE1 — Backdoor Link — CE2.
Customer traffic using Sham-link: CE1 → PE1 → PE2 → CE2.
```

- When Customer sites are connected via backdoor links – sham-links are recommended so that the MPLS-VPN core will be preferred rather than through the backdoor link 

- The sham link is treated as a virtual-link: unnumbered, ptp, DC link 

- The sham link is reported in the router LSA’s type 1 originated by the two routers connecting to the sham link 

- The MPLS VPN backbone or the backdoor link can be made preferred path by tweaking the metrics 

[ดูภาพต้นฉบับหน้า 162 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=162)

---

## หน้า 163

### 3.6 



##### Deployment Scenarios with EIGRP 

BRKRST-2332_c1 

© 2010 Cisco and/or its affiliates. All rights reserved. 

Cisco Public 

163

[ดูภาพต้นฉบับหน้า 163 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=163)

---

## หน้า 164

###### **Default-Gateway Using EIGRP PE-CE** 

```text
MPLS-VPN Service Provider 1 contains PE1, PE2, PE3.
Site 1 (Internet Site): Int Rtr 1 — CE1 — PE1.
Site 2 (Internet Site): Int Rtr 2 — CE2 — PE2.
Site 3 (Non-Internet Site): CE3 — PE3.
```

- A typical deployment scenario with the Self-Managed MPLS network where big enterprises manage their own MPLS core 

- Customer has peering to two ISPs at two different locations 

- They want the default-route to get propagated into the non-Internet sites 

- In the above example: Site 1 and Site 2 are Internet Connected Sites and Site 3 is not 

[ดูภาพต้นฉบับหน้า 164 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=164)

---

## หน้า 165

### Default-Gateway Using EIGRP PE-CE

**Note:** 

- PE needs the “ **default-information originate** ” under the IPv4-VRF-AF for the default-route to get propagated across the MPLS-Core which was learned via EIGRP 

- By default, if a PE receives the same prefix from Customer site and also from MPLS-VPN backbone, then the metrics components which are carried in the BGP Extended communities are compared to the EIGRP metrics from the customer site 

- In our Ex.: 0.0.0.0/0 is learned by PE2 from MPLSVPN cloud via CE1-(Site 1)→ PE1 and also from the CE2 at Site 2 

- Metric of the path determines which path is better 

BRKRST-2332_c1 

© 2010 Cisco and/or its affiliates. All rights reserved. 

Cisco Public 

165

[ดูภาพต้นฉบับหน้า 165 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=165)

---

## หน้า 166

###### **Default-Gateway Using EIGRP PE-CE** 



```
PE2#show ip bgp vpnv4 all 0.0.0.0
BGP routing table entry for 1234:2:0.0.0.0/0, version 124
Paths: (1 available, best #1, table intranet)
  Local, imported path from 1234:1:0.0.0.0/0
    11.11.11.11 (metric 30) from 22.22.22.22 (22.22.22.22)
      Origin incomplete, metric 281856, localpref 100, valid, internal, best
      Extended Community: RT:1234:123 Cost:pre-bestpath:129:281856 0x8800:0:5
        0x8801:1:25856 0x8802:65281:256000 0x8803:65281:1500
        0x8804:1:2802450433 0x8805:9:0
      Originator: 11.11.11.11, Cluster list: 22.22.22.22, 21.21.21.21
```

PE2 prefers the DEFAULT from PE1 as the metric received in the Pre-Bestpath is better than the metric received via EIGRP.

| Path | Metric |
| --- | --- |
| via MPLS-Core | 281856 |
| via EIGRP | 1762048 |

```text
PE2#show ip eigrp vrf intranet topology
P 0.0.0.0/0, 1 successors, FD is 281856, tag is 5
    via VPNv4 Sourced (281856/0)
    via 167.51.51.1 (1762048/256256), Serial2/0
```

Metric Determines which path is better.

[ดูภาพต้นฉบับหน้า 166 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=166)

---

## หน้า 167

###### **Default-Gateway Using EIGRP PE-CE** 

```
PE2#show ip eigrp vrf intranet topology 0.0.0.0 0.0.0.0
IP-EIGRP topology entry for 0.0.0.0/0
  State is Passive, Query origin flag is 1, 1 Successor(s), FD is 281856
0.0.0.0, from 0.0.0.0, Send flag is 0x0
Composite metric is (281856/0), Route is External (VPNv4 Sourced)
      External data:
        Originating router is 167.10.0.1
        AS number of route is 1
        External protocol is BGP, external metric is 0
        Administrator tag is 5 (0x00000005)
167.51.51.1 (Serial2/0), from 167.51.51.1, Send flag is 0x0
Composite metric is (1762048/256256), Route is External
      External data:
        Originating router is 2.2.2.2
        AS number of route is 2
        External protocol is BGP, external metric is 0
        Administrator tag is 6 (0x00000006)
        Exterior flag is set
```

The EIGRP-VRF topology shows the metrics received via the EIGRP Path and via MP-BGP path.    The Composite-metric received from the MPLS-VPN core (281856) is better than the one received from the EIGRP-neighbor (1762048) 

BRKRST-2332_c1 

© 2010 Cisco and/or its affiliates. All rights reserved. 

Cisco Public 

167

[ดูภาพต้นฉบับหน้า 167 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=167)

---

## หน้า 168

### Default-Gateway Using EIGRP PE-CE

```text
PE2#show ip bgp vpnv4 all 0.0.0.0
BGP routing table entry for 1234:2:0.0.0.0/0, version 105
Paths: (2 available, best #2, table intranet)
  Local, imported path from 1234:1:0.0.0.0/0
    11.11.11.11 (metric 30) from 22.22.22.22 (22.22.22.22)
      Origin incomplete, metric 281856, localpref 100, valid, internal
      Extended Community: RT:1234:123
        Cost:pre-bestpath:129:2000000 (default-2145483647)
  Local
    167.51.51.1 (via intranet) from 0.0.0.0 (12.12.12.12)
      Origin incomplete, metric 1762048, localpref 100, weight 32768, valid, sourced, best
      Extended Community: RT:1234:123
        Cost:pre-bestpath:129:1762048 (default-2145721599)
```

We can use the Pre-Bestpath option to overwrite metric that will be used in the best path calculation.

The Pre-Bestpath metric from 11.11.11.11 is compared with from 167.51.51.1.

**2000000 vs. 1762048** — Lower Metric wins.

[ดูภาพต้นฉบับหน้า 168 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=168)

---

## หน้า 169

###### **Default-Gateway Using EIGRP PE-CE** 

Configuration Example 

PE3 also now prefers it via PE2

Customer at NON-Internet Site may prefer for their Internet traffic to go via PE1 

```
router bgp 65000
 !
 address-family vpnv4
 neighbor 21.21.21.21 activate
 neighbor 21.21.21.21 send-community extended
 neighbor 21.21.21.21 route-map COST out
 exit-address-family
!
route-map COST permit 1
set extcommunity cost pre-bestpath 129 2000000
!
PE3#show ip bgp vpnv4 all 0.0.0.0
BGP routing table entry for 1234:3:0.0.0.0/0, version 88
Paths: (2 available, best #2, table intranet)
  Local, imported path from 1234:1:0.0.0.0/0
    11.11.11.11 (metric 30) from 23.23.23.23 (23.23.23.23)
      Origin incomplete, metric 281856, localpref 100, valid, internal
      Extended Community: RT:1234:123
Cost:pre-bestpath:129:2000000 (default-2145483647)
  Local, imported path from 1234:2:0.0.0.0/0
12.12.12.12 (metric 30) from 23.23.23.23 (23.23.23.23)
      Origin incomplete, metric 1762048, localpref 100, valid, internal, best
      Extended Community: RT:1234:123
Cost:pre-bestpath:129:1762048 (default-2145721599)
```

BRKRST-2332_c1 © 2010 Cisco and/or its affiliates. All rights reserved. Cisco Public 

169

[ดูภาพต้นฉบับหน้า 169 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=169)

---

## หน้า 170

###### **Default-Gateway Using EIGRP PE-CE** 

```text
MPLS-VPN Service Provider 1 contains PE1, PE2, PE3.
Site 1 (Internet Site): Int Rtr 1 — CE1 — PE1.
Site 2 (Internet Site): Int Rtr 2 — CE2 — PE2.
Site 3 (Non-Internet Site): CE3 — PE3.
Additional Non-Internet Sites: Site N-1 (CE N-1), Site N (CE N), attached toward PE3.
Orange, blue and green arrows: all Non-Internet Sites → PE3 → PE2 → CE2 → Int Rtr 2.
```

- As seen, Non-Internet-Site may start preferring the Site 2 for Internet Connection via PE2 

- All other Non-Internet-Sites will also prefer via PE2 

- This may not be Optimal as All Other Non-Internet Sites may prefer Deterministically via Site 2 using PE2 

[ดูภาพต้นฉบับหน้า 170 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=170)

---

## หน้า 171

###### **Using RT for the Default Gateway** 

```text
MPLS-VPN Service Provider 1 contains PE1, PE2, PE3.
Site 1 (Internet Site): Int Rtr 1 — CE1 — PE1.
Site 2 (Internet Site): Int Rtr 2 — CE2 — PE2.
Site 3 (Non-Internet Site): CE3 — PE3.
PE1: RT:1234:1; PE2: RT:1234:2; PE3: RT:1234:3.
Black route advertisement arrows: PE1 → PE3; PE2 → PE3.
```

- Assign an Unique RT value at each PE router 

- Non-Internet Connected site PE router can use an in-bound policy using a pre-bestpath or weight to change the best path that is received. 

- PE3, in the above example uses: RT with 1234.1 with preferred pre-bestpath than one with the 1234:2 

> หมายเหตุจากการตรวจ: bullet ต้นฉบับพิมพ์ 1234.1 แต่ค่า RT ในภาพคือ 1234:1; เก็บข้อความต้นฉบับทั้งสองส่วน

[ดูภาพต้นฉบับหน้า 171 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=171)

---

## หน้า 172

### Using RT for the Default Gateway

```text
PE3#show ip bgp vpnv4 all 0.0.0.0
BGP routing table entry for 1234:3:0.0.0.0/0, version 103
Paths: (2 available, best #2, table intranet)
  Local, imported path from 1234:2:0.0.0.0/0
    12.12.12.12 (metric 30) from 23.23.23.23 (23.23.23.23)
      Origin incomplete, metric 1762048, localpref 100, valid, internal
      Extended Community: RT:1234:2 Cost:pre-bestpath:1:2
        Cost:pre-bestpath:129:1762048 (default-2145721599)
  Local, imported path from 1234:1:0.0.0.0/0
    11.11.11.11 (metric 30) from 23.23.23.23 (23.23.23.23)
      Origin incomplete, metric 281856, localpref 100, valid, internal, best
      Extended Community: RT:1234:1 Cost:pre-bestpath:1:1
        Cost:pre-bestpath:129:2000000 (default-2145483647)
```

Even though Cost:pre-bestpath:129:2000000 is worse than 129:1762048, PE3 picks route from the 11.11.11.11 than from the 12.12.12.12.

[ดูภาพต้นฉบับหน้า 172 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=172)

---

## หน้า 173

###### **Using RT for the Default Gateway**

#### Configuration on the PE3 Router 

```
router bgp 65000
 no bgp default ipv4-unicast
 bgp log-neighbor-changes
 neighbor 23.23.23.23 remote-as 65000
 neighbor 23.23.23.23 update-source Loopback0
 !
 address-family vpnv4
 neighbor 23.23.23.23 activate
 neighbor 23.23.23.23 send-community extended
neighbor 23.23.23.23 route-map choose-internet-pop in
 exit-address-family
 !
 address-family ipv4 vrf intranet
 redistribute eigrp 1
 no synchronization
 exit-address-family
!
ip extcommunity-list 1 permit rt 1234:1
ip extcommunity-list 2 permit rt 1234:2
!
route-map choose-internet-pop permit 10
 match extcommunity 1
 set extcommunity cost pre-bestpath 1 1
!
route-map choose-internet-pop permit 20
 match extcommunity 2
 set extcommunity cost pre-bestpath 1 2
!
```

BRKRST-2332_c1 

© 2010 Cisco and/or its affiliates. All rights reserved. 

Cisco Public 

173

[ดูภาพต้นฉบับหน้า 173 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=173)

---

## หน้า 174

##### 6vPE 

**174** 

© 2010 Cisco Systems, Inc. All rights reserved. Cisco Confidential 

JMB

[ดูภาพต้นฉบับหน้า 174 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=174)

---

## หน้า 175

### IPv6 VPN 6VPE (RFC 4659)

```text
IPv6/IPv4 Network — MPLS IPv4 Backbone — IPv6/IPv4 Network.
CE1 — 6VPE1 (VRF) — four P routers, IPv4 MPLS — 6VPE2 (VRF) — CE2.
Both customer networks support IPv4 and IPv6.
6VPE1: 200.10.10.1; 6VPE2: 200.11.11.1.
Left customer prefix: 2001:db8:beef:1::/64; right customer prefix: 2001:db8:beef:2::/64.
CE1—6VPE1: 172.16.1.0.0/30; 2001:db8:cafe:1::/64.
6VPE2—CE2: 172.16.3.1/30; 2001:db8:cafe:3::/64.
Left customer IPv4:10.1.1.0/24; right customer IPv4:10.1.2.0/24.
Customer packet: IPv6 Packet; backbone packet: IPv6 Packet + VPN Label + LDP Label.
```

- 6VPE uses existing IPv4 MPLS infrastructure to provide IPv6 VPN
  - Core uses IPv4 control plane (LDPv4, TEv4, IGPv4)
- PEs must support dual stack IPv4+IPv6
- Offers same architectural features as MPLS-VPN for IPv4
  - RTs, VRFs, RDs are appended to IPv6 to form VPNv6 address
  - MP-BGP distributed both VPN address families
  - BGP NH uses IPv4 to IPv6 mapped address format `::ffff:A.B.C.D`
- VRF can contain both VPNv4 and VPNv6 routes

> หมายเหตุจากการตรวจ: diagram ต้นฉบับมี IPv4 ที่พิมพ์เกินเป็น 172.16.1.0.0/30; เก็บตามภาพ

[ดูภาพต้นฉบับหน้า 175 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=175)

---

## หน้า 176

### 6vPE Control Plane

```text
IPv6/IPv4 Network — MPLS IPv4 Backbone — IPv6/IPv4 Network.
CE1 — 6VPE1 (VRF) — four P routers, IPv4 MPLS — 6VPE2 (VRF) — CE2.
Both customer networks support IPv4 and IPv6.
6VPE1: 200.10.10.1; 6VPE2: 200.11.11.1.
Left customer prefix: 2001:beef:1::/64; right customer prefix: 2001:beef:2::/64.
CE1—6VPE1: 172.16.1.0.0/30; 2001:db8:cafe:1::/64.
6VPE2—CE2: 172.16.3.1/30; 2001:db8:cafe:3::/64.
Core router names: P3/P4 upper path; P1/P2 lower path.
CE1 ↔ 6VPE1: eBGP; 6VPE1 ↔ 6VPE2: iBGP (AFI=2/SAFI=128); 6VPE2 ↔ CE2: eBGP.
```

| Control-plane row | Left core segment | Middle core segment | Right core segment |
| --- | --- | --- | --- |
| IGPv4 | 20.10.10.1 reachable | 20.10.10.1 reachable | 20.10.10.1 reachable |
| LDPv4 | Binds label {Pop} to 20.10.10.1 | Binds label {27} to 20.10.10.1 | Binds label {48} to 20.10.10.1 |

- MP-eBGP: Advertises to 6vPE1 `2001:beef:1::`.
- IPv6 MP-iBGP: Advertises to 6vPE2 `RD:2001:beef:1::`; BGP Next Hop `::ffff:200.10.10.1`; Label Binding `{76}`; Extended Communities = RT values.
- MP-eBGP: Advertises to CE2 `2001:beef:1::`.

> หมายเหตุจากการตรวจ: IGP/LDP กล่องล่างแสดง 20.10.10.1 ขณะที่ loopback/BGP NH แสดง 200.10.10.1; เก็บตามต้นฉบับ เช่นเดียวกับ 172.16.1.0.0/30

[ดูภาพต้นฉบับหน้า 176 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=176)

---

## หน้า 177

### 6vPE Data Plane

```text
IPv6/IPv4 Network — MPLS IPv4 Backbone — IPv6/IPv4 Network.
CE1 — 6VPE1 (VRF) — four P routers, IPv4 MPLS — 6VPE2 (VRF) — CE2.
Both customer networks support IPv4 and IPv6.
6VPE1: 200.10.10.1; 6VPE2: 200.11.11.1.
Left customer prefix: 2001:beef:1::/64; right customer prefix: 2001:beef:2::/64.
CE1—6VPE1: 172.16.1.0/30; 2001:db8:cafe:1::/64.
6VPE2—CE2: 172.16.3.1/30; 2001:db8:cafe:3::/64.
Core router names: P3/P4 upper path; P1/P2 lower path.
```

| Item | Value |
| --- | --- |
| IPv6 Prefix | 2001:beef:1:: |
| VPN Label | {76} |
| BGP NH | ::ffff:200.10.10.1 |
| IPv4 NH | 200.10.10.1 |
| LDP Label | {48} |

#### Packet stacks, left to right as displayed

| Segment | Encapsulation | LDP IPv4 Label | VPN IPv6 Label | IPv6 Prefix |
| --- | --- | --- | --- | --- |
| CE1—6VPE1 | IPv6 | — | — | 2001:beef:1:: |
| 6VPE1—P1 | MPLS | — | {76} | 2001:beef:1:: |
| P1—P2 | MPLS | {27} | {76} | 2001:beef:1:: |
| P2—6VPE2 | MPLS | {48} | {76} | 2001:beef:1:: |
| 6VPE2—CE2 | IPv6 | — | — | 2001:beef:1:: |

> หมายเหตุจากการตรวจ: ตารางเรียงตามตำแหน่งซ้ายไปขวาในสไลด์; ค่ากล่อง packet แสดง 2001:beef:1:: ทุกตำแหน่งตามต้นฉบับ

[ดูภาพต้นฉบับหน้า 177 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=177)

---

## หน้า 178

### CE1 Configuration

```text
IPv6/IPv4 Network — MPLS IPv4 Backbone — IPv6/IPv4 Network.
CE1 — 6VPE1 (VRF) — four P routers, IPv4 MPLS — 6VPE2 (VRF) — CE2.
Both customer networks support IPv4 and IPv6.
6VPE1: 200.10.10.1; 6VPE2: 200.11.11.1.
Left customer prefix: 2001:db8:beef:1::/64; right customer prefix: 2001:db8:beef:2::/64.
CE1—6VPE1: 172.16.1.0/30; 2001:db8:cafe:1::/64.
6VPE2—CE2: 172.16.3.1/30; 2001:db8:cafe:3::/64.
Left customer IPv4:10.1.1.0/24; right customer IPv4:10.1.2.0/24.
Customer packet: IPv6 Packet; backbone packet: IPv6 Packet + VPN Label + LDP Label.
```

#### Interface configuration

```text
ipv6 unicast-routing
ipv6 cef
!
interface Ethernet0/0
 description Link to PE1
 ip address 172.16.1.1 255.255.255.0
 ipv6 address 2001:db8:cafe:1::1/64
!
interface Ethernet1/0
 description to GREEN LAN
 ip address 10.1.1.1 255.255.255.0
 ipv6 address 2001:db8:beef:1::1/64
 ipv6 rip GREEN enable
```

#### BGP configuration

```text
router bgp 500
 neighbor 2001:db8:cafe:1::2 remote-as 100
 neighbor 172.16.1.2 remote-as 100
 !
 address-family ipv4
  redistribute eigrp 100
  neighbor 172.16.1.2 activate
 exit-address-family
 !
 address-family ipv6
  neighbor 2001:db8:cafe:1::2 activate
  redistribute rip GREEN
 exit-address-family
```

Both activate commands have the annotation **← 6VPE1**.

> หมายเหตุจากการตรวจ: diagram แสดง CE–PE /30 แต่ interface ip address ใช้ 255.255.255.0; เก็บ mask ตามคำสั่งต้นฉบับ

[ดูภาพต้นฉบับหน้า 178 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=178)

---

## หน้า 179

### New Multi-AF VRF Configuration

```text
IPv6/IPv4 Network — MPLS IPv4 Backbone — IPv6/IPv4 Network.
CE1 — 6VPE1 (VRF) — four P routers, IPv4 MPLS — 6VPE2 (VRF) — CE2.
Both customer networks support IPv4 and IPv6.
6VPE1: 200.10.10.1; 6VPE2: 200.11.11.1.
Left customer prefix: 2001:db8:beef:1::/64; right customer prefix: 2001:db8:beef:2::/64.
CE1—6VPE1: 172.16.1.0/30; 2001:db8:cafe:1::/64.
6VPE2—CE2: 172.16.3.1/30; 2001:db8:cafe:3::/64.
Left customer IPv4:10.1.1.0/24; right customer IPv4:10.1.2.0/24.
Customer packet: IPv6 Packet; backbone packet: IPv6 Packet + VPN Label + LDP Label.
```

```text
vrf definition GREEN
 rd 200:1
 ! Common RT policies go here
 address-family ipv4
  route-target export 200:1
  route-target import 200:1
 exit-address-family
 !
 address-family ipv6
  route-target export 200:1
  route-target import 200:1
 exit-address-family
```

- New VRF AF definition
  - Allows address-families
  - Each with unique or common policies
- `vrf upgrade-cli multi-af-mode {common-policies | non-common-policies} [vrf <name>]`
  - This command can update existing VRF definitions

[ดูภาพต้นฉบับหน้า 179 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=179)

---

## หน้า 180

### 6VPE1 General Configuration

```text
IPv6/IPv4 Network — MPLS IPv4 Backbone — IPv6/IPv4 Network.
CE1 — 6VPE1 (VRF) — four P routers, IPv4 MPLS — 6VPE2 (VRF) — CE2.
Both customer networks support IPv4 and IPv6.
6VPE1: 200.10.10.1; 6VPE2: 200.11.11.1.
Left customer prefix: 2001:db8:beef:1::/64; right customer prefix: 2001:db8:beef:2::/64.
CE1—6VPE1: 172.16.1.0/30; 2001:db8:cafe:1::/64.
6VPE2—CE2: 172.16.3.1/30; 2001:db8:cafe:3::/64.
Left customer IPv4:10.1.1.0/24; right customer IPv4:10.1.2.0/24.
Customer packet: IPv6 Packet; backbone packet: IPv6 Packet + VPN Label + LDP Label.
```

```text
ipv6 unicast-routing
ipv6 cef
!
interface Loopback0
 ip address 200.10.10.1 255.255.255.255
!
interface Ethernet0/0
 Description Link to CE1
 vrf forwarding GREEN
 ip address 172.16.1.2 255.255.255.0
 ipv6 address 2001:db8:cafe:1::2/64
!
interface Ethernet2/0
 description Link to Core Network
 ip address 192.168.1.1 255.255.255.252
 mpls ip
!
router ospf 1
 log-adjacency-changes
 redistribute connected subnets
 passive-interface Loopback0
 network 192.168.1.0 0.0.0.255 area 0
```

> หมายเหตุจากการตรวจ: diagram แสดง CE–PE /30 แต่ interface ใช้ 255.255.255.0; เก็บตามคำสั่งต้นฉบับ

[ดูภาพต้นฉบับหน้า 180 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=180)

---

## หน้า 181

### 6VPE1 BGP Configuration

```text
IPv6/IPv4 Network — MPLS IPv4 Backbone — IPv6/IPv4 Network.
CE1 — 6VPE1 (VRF) — four P routers, IPv4 MPLS — 6VPE2 (VRF) — CE2.
Both customer networks support IPv4 and IPv6.
6VPE1: 200.10.10.1; 6VPE2: 200.11.11.1.
Left customer prefix: 2001:db8:beef:1::/64; right customer prefix: 2001:db8:beef:2::/64.
CE1—6VPE1: 172.16.1.0/30; 2001:db8:cafe:1::/64.
6VPE2—CE2: 172.16.3.1.0/30; 2001:db8:cafe:3::/64.
Left customer IPv4:10.1.1.0/24; right customer IPv4:10.1.2.0/24.
Customer packet: IPv6 Packet; backbone packet: IPv6 Packet + VPN Label + LDP Label.
```

```text
router bgp 100
 neighbor 200.11.11.1 remote-as 100
 neighbor 200.11.11.1 update-source lo0
 !
 address-family ipv4
  neighbor 200.11.11.1 activate
  no auto-summary
  no synchronization
 exit-address-family
 !
 address-family vpnv4
  neighbor 200.11.11.1 activate
  neighbor 200.11.11.1 send-community ext
 exit-address-family
 address-family vpnv6
  neighbor 200.11.11.1 activate
  neighbor 200.11.11.1 send-community ext
 exit-address-family
 !
 address-family ipv4 vrf GREEN
  redistribute connected
  neighbor 172.16.1.1 remote-as 500
  neighbor 172.16.1.1 activate
 exit-address-family
 !
 address-family ipv6 vrf GREEN
  neighbor 2001:db8:cafe:1::1 remote-as 500
  neighbor 2001:db8:cafe:1::1 activate
 exit-address-family
```

| Address family | Arrow annotation |
| --- | --- |
| ipv4 | Internet Routes |
| vpnv4 | To 6VPE2 |
| vpnv6 | To 6VPE2 |
| ipv4 vrf GREEN | To CE1 |
| ipv6 vrf GREEN | To CE1 |

> หมายเหตุจากการตรวจ: diagram ของหน้านี้พิมพ์ 172.16.3.1.0/30 เกินหนึ่ง octet; เก็บตามภาพ

[ดูภาพต้นฉบับหน้า 181 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=181)

---

## หน้า 182

### CISCO

หน้าปิดท้ายเป็นโลโก้ Cisco

[ดูภาพต้นฉบับหน้า 182 ใน PDF](CISCO%20MPLS%20Layer%203%20VPNs.pdf#page=182)

---
