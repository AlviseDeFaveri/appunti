### COAP

A COAP client issues the request message at the right. Briefly explain the meaning of all the lines in the message and write a consistent and complete response from the COAP server assuming that the server includes the requested resource in the response message
(CLEARLY EXPRESS THE MESSAGE ID AND THE TOKEN ID IN THE
RESPONSE MESSAGE)


```
CON [1212]
GET /humidity
(Token 2323)
```

---

A COAP client issues a CONFIRMABLE message. Assuming that the packet error rate is p=0.3 and the MAX_RETRANSMIT parameter is 3, find the probability that the CONFIRMABLE message in the end goes through. Now assume that MAX_RETRANSMIT=infinity and that the initial time out is set
randomly in the interval [3s, 5s] and find the average time to the successful transmission of the CONFIRMABLE message

---

A COAP client sends the following message to a COAP server.

```
CON [08bx10]
GET /light
Token [10x5]
```


Specify the content of the response message (message ID, token ID and type of message) from the server assuming that: (i) the server responds immediately with a confirmable message, (ii) the server has the requested resource

---



### ETX

Write the expression of the average energy consumed by all the sensor nodes for sending one packet from A to C through the two-hop path at the right. The numbers below each link express the ETX for the link (energy for operating the TX/RX circuitry for one packet E c , energy for transmitting one packet E tx )

---

Find out the ETX for the two wireless links in the figure (each link is labeled with the corresponding packet error probability, p). Now find out the average number of required transmission to send a packet successfully from A to C.

---

A wireless link is characterized by a packet error rate in the two directions (left-right, right-left) of 1% and 0.5% respectively. Assuming that the packet used for delivering information from left to right have size L=128[byte], the acknowledgements in the opposite direction have size A=8[byte], and the nominal rate in both directions is R=100[kbit/s], find the average transmission time to successfully send a packet and get the corresponding acknowledgement (assume negligible propagation delay)

---



### RFID

A Dynamic Frame ALOHA system is used to arbitrate 3 tags. What is the average duration of the arbitration time if the initial frame length is r 1 =3 (assume that the frame size of the following frames may be optimally set to exact value of the current backlog)

---

A Dynamic Frame ALOHA system is used to arbitrate 4 tags. What is the average throughput after the first two frames of the arbitration process knowing that the respective frame lengths are r 1 =2, r 2 =2?

---

A RFID collision arbitration system is based on multi-frame dynamic frame ALOHA. Find out the efficiency of the collision arbitration process if the initial number o tags is N=3 and the initial frame size is r=2

---

An RFID system is composed of 3 tags and uses a Dynamic Frame ALOHA access protocol.
Assume that the initial frame size is r=4 and that after the first frame no tags have been resolved. What is the backlog predicted by Schoute’s estimate? Find out the probability that the resolved tags after the second frame is equal to i, with i=0, 1, 2, 3 if the second frame length is set according to Schoute’s estimate.

---

A Dynamic Frame ALOHA system estimates the current backlog of unresolved tags to be 2. What is the single-frame throughput assuming that the system optimally set the frame length ACCORDING TO THE BACKLOG ESTIMATE and knowing that the real number of unresolved tags is 4

---

The figure represents a possible outcome of the execution of a binary tree algorithm with three tags A, B and C to be resolved. For each node in the tree, the figure reports the slot number and the outcome of the transmission (success or collision, empty circles arte successful ones). What is the efficiency of this outcome? What is the probability for this outcome to happen?



### ZIGBEE

A ZigBee network topology is characterized by the following parameters: L m =3, R m =2, D m =2. How many addresses must be assigned to ZigBee routers at level 2?

---

Describe the structure and the usage of the Routing Table and the Routing Discovery Table in ZigBee AODV routing

---

Assign ZigBee addresses in the following tree network topology. Solid circles are ZigBee routers, empty circles are ZigBee and devices

---



### 6LOWPAN

Briefly describe the header compression standardized in 6LowPAN.

---

Briefly explain how the DODAG creation process in RPL

---



### IEEE 802.15.4

A sensor node performs channel access according to the CSMA/CA scheme of the IEEE 802.15.4 standard. Assuming that the probability of finding the channel busy is p=0.05 at each backoff period, what is the probability that the sensor node does actually access the channel within the first two tries

---

Briefly describe the process of active scanning in the context of IEEE 802.15.4 network formation