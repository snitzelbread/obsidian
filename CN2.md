
# OSPF

OSPF (Open Shortest Path First) is a link state protocol, It gathers information about routers by sending LSA (Link State Advertisements) to each other. It has a hierarchical structure. It uses Dijkstra's Shortest Path Algorithm to determine the shortest path, and thus the route with the lowest cost, to a destination.


![[Pasted image 20260225122914.png]]


Here we can see a network that uses OSPF. OSPF looks quite complex, but is kind of simple if you get used to it.

Its kind of like the human body, in the sense that everything goes to a central spot (like the brain) and from there on out it goes back to either another area or outside the network (via an ASBR)

## Network Types

OSPF defines four primary network types to determine how routers establish neighbor adjacencies, elect Designated Routers (DR/BDR), and exchange routing information.

- **Broadcast:** Supports multiple routers on a single segment. It uses multicast (224.0.0.5/6) for communication, requires DR/BDR election, and has 10s Hello/40s Dead timers.

- **Point-to-Point (Default for PPP/HDLC):** Connects exactly two routers, such as a serial link. It does not use DR/BDR, supports automatic neighbor discovery, and uses 10s/40s timers.

- **Non-Broadcast Multi-Access (NBMA):** Used on technologies like Frame Relay or ATM that allow multiple routers but lack broadcast/multicast capabilities. It requires manual neighbor configuration, full-mesh topology, and DR/BDR election, using 30s Hello/120s Dead timers.

- **Point-to-Multipoint (P2MP):** Ideal for hub-and-spoke topologies where the hub connects to multiple, non-direct spokes. It doesn't require DR/BDR and uses 30s Hello/120s Dead timers.

## Router Types

There's 5 different kinds of routers in OSPF. They all serve different purposes. The interfaces that connect to each other can have different kinds of network types (point-to-point, broadcast, non-broadcast multi-access (NBMA), point-to-multipoint (P2MP))

### Internal Router

These are the basic routers within a network. They don't sit on any border or fulfill any special function. They send their routing information the ABR or DR and also get their information from them.

### Backbone Router (BR)

These are routers that are within or on the border of the backbone area. In our example above, this would be R1, R2, R3 and R4. They connect to one another (in this case via `point-to-point` network type). To the switch they connect via a broadcast network type.

### Area Border Router (ABR)

These are routers that sit on the border between the two areas they connect. Backbone Routers are also sometimes ABRs (but because calling them ABRs is more precise, we call them ABRs).

In the example network, these would be R2, R3, R4 and R5 (while R2-4 are also Backbone Routers)

They also convert LSA Type 7's to LSA Type 5's if the sub-area is a NSSA or TNSSA.

### Autonomous System Border Router (ASBR)

These are routers that connect to another AS (Autonomous System). Basically just another network which isn't ours. 

They are the ones to send LSA Type 5's (or Type 7's if NSSA or TNSSA) which contain external routing information.

This would be R7 in the example.

### Designated Router (DR) & Backup Designated Router (BDR)

These are routers that are only available within a broadcast network. In the example, these are the Routers R1, R2, R3 and R4, but connected via the switch. So the interface that points to the switch from an adjacent router is a broadcast network type interface.

They collect router information and send that out to all the other routers. This means that all the internal routers only have adjacencies with the DR and BDR. This reduces OSPF traffic and LSA flooding.

If the DR fails, the BDR takes over.

So basically, DR is the boss, he gets new info from a peasant router (via designated multicast address 224.0.0.6) and then sends that out to all the other peasant routers via designated multicast address 224.0.0.5

The other routers are called DROTHERS (or No-DR/BDR)

## Areas

### Backbone Area - (Area 0)

The backbone area is, well, the backbone of the network. It connects all the sub-areas and allows for inter-area communication. 

All other areas **MUST** connect to this one, be it directly via a connected ABR (R5 to R2), or, if an area is connected to another sub-area, it must have a virtual link from its ABR to the Backbone ABR. In our example, this would be R8. It needs a virtual link from its ABR (R5) to the Backbone ABR (R2). This isn't shown in the diagram, but they are usually indicated by a dashed line.

The Backbone Area allows for all types, which is important, because it has a total overview over the whole network, which can't be said over some other areas. It always knows where to send a packet.

### Standard Area

These Standard Areas don't have any special limitations. They have an ABR, which allows all LSA Types in. Within a Standard Area, you have routes to other areas, external AS's, and obviously to the ones within your area.

## Stub Area

Stub Areas are bit more complex. They don't allow for external routing information (external meaning outside the WHOLE network, so to the internet for example). This means that LSA Type 5's are not allowed within the area. Now how do we send information out to AS's? Well there is a default route to the Stub Area's ABR. The ABR is connected to the Backbone Area, which in turn knows where to send the request.


