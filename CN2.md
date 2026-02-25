
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

These are routers that are only available within a broadcast network. In the example, these are the Routers R1, R2, R3 and R4, but with the interfaces that point towards the switch. So the interface that points to the switch from an adjacent router is a broadcast network type interface.

They collect router information and send that out to all the other routers. This means that all the internal routers only have adjacencies with the DR and BDR. This reduces OSPF traffic and LSA flooding.

If the DR fails, the BDR takes over.

So basically, DR is the boss, he gets new info from a peasant router (via designated multicast address 224.0.0.6) and then sends that out to all the other peasant routers via designated multicast address 224.0.0.5

The other routers are called DROTHERS (or No-DR/BDR)

## OSPF Message Types & LSA Types

Lets imagine two villages between which boats go back and forth. They go from one village to the other one, maintaining a relationship with that village, checking up on them, or maybe even to ask them to exchange information. Sometimes the first village asks the boat to get them the new information that the other village has. So the boat goes back with a request to bring new information. It goes back, gets the information, and then goes back to the other village, giving them the information.

We can see, the boat is an analogy for the OSPF Message Types. It either checks up on the village (a "Hello" Message Type 1), asks for new information (Request Message Type 3), brings them new information (LS Update Message Type 4), or confirms that the other village got the information (LSAck Message Type 5).

LSA Types are the actual information that the villages exchange, so the content. They ALSO come in different types. It could be routing information or maybe network information. They are then carried by an LSU (Link State Update) Message Type to the other router (village).

Because there are so many different things a OSPF Message Type can tell us, there are different types to distinguish their purpose.

### Type 1: Hello

Discovers neighbors and maintains adjacencies. Basically just introduction and maintaining the connection.

### Type 2: Database Description (DBD)

Used during initialization. It summarizes ones LSDB (Link State Database), the database that contains all the routing information one has. If there is some information the other router doesn't have, then it will send a Message Type 3.

### Type 3: Link State Request (LSR)

With this, R1 requests LSA's that are missing from it's own database from R2. R2 will receive this request and then send send R1 the information via a Type 4.

### Type 4: Link State Update (LSU)

These are the actual messages that CONTAIN the LSA's. They can carry multiple LSA's.

### Type 5: Link State Acknowledgment (LSAck)

These are sent back to the sender to tell them **explicitly** that they have received the LSU. Sometimes it isn't used though and instead the receiver sends back another LSU with the same stuff that the receiver just sent. This is the **implicit** acknowledgment.


## Area Types

### Backbone Area - (Area 0)

The backbone area is, well, the backbone of the network. It connects all the sub-areas and allows for inter-area communication. 

All other areas **MUST** connect to this one, be it directly via a connected ABR (R5 to R2), or, if an area is connected to another sub-area, it must have a virtual link from its ABR to the Backbone ABR. In our example, this would be R8. It needs a virtual link from its ABR (R5) to the Backbone ABR (R2). This isn't shown in the diagram, but they are usually indicated by a dashed line.

The Backbone Area allows for all types, which is important, because it has a total overview over the whole network, which can't be said over some other areas. It always knows where to send a packet.

### Standard Area

These Standard Areas don't have any special limitations. They have an ABR, which allows all LSA Types in. Within a Standard Area, you have routes to other areas, external AS's, and obviously to the ones within your area.

### Stub Area

Stub Areas are bit more complex. They don't allow for external routing information (external meaning outside the WHOLE network, so to the internet for example). This means that LSA Type 5's are not allowed within the area. Now how do we send information out to AS's? Well there is a default route to the Stub Area's ABR. The ABR is connected to the Backbone Area, which in turn knows where to send the request.

### Not So Stubby Area (NSSA)

The Not So Stubby Area is the same as the Stubby Area, except that it allows for LSA Type 7's within it's own area. The LSA Type 7's come from ASBR's that are within the area and whose information need to be propagated to outside of that area. These LSA's are transported through the NSSA as Type 7's but are then translated to Type 5's at the ABR to then be sent to other Areas and the Backbone Area.

### Totally Stubby Area (TSA)


### Totally Not So Stubby Area (TNSSA)