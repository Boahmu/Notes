## How does ARP Work?
Each device within a network has a ledger to store information on, which is called a cache. In the context of the **ARP** protocol or **A**ddress **R**esolution **P**rotocol, this cache stores the identifiers of other devices on the network.

In order to map these two identifiers together (IP address and MAC address), the ARP protocol sends two types of messages:

1.  **ARP Request**
2.  **ARP Reply**

When an **ARP request** is sent, a message is broadcasted to every other device found on a network by the device, asking whether or not the device's MAC address matches the requested IP address. If the device does have the requested IP address, an **ARP reply** is returned to the initial device to acknowledge this. The initial device will now remember this and store it within its cache (an ARP entry).

![[ARP-protocol.png]]






Sources : https://tryhackme.com/room/introtolan
