#learning/networking/fundamentals

---


> [!NOTE] Notes
> This content is extracted from [**TryHackMe | OSI Layer**](https://tryhackme.com/room/osimodelzi)

## Definition

The **OSI** model (or **O**pen **S**ystems **I**nterconnection Model) is an essential model used in networking.  This critical model provides a framework dictating how all networked devices will send, receive and interpret data.

![[OSI Layer.png]]

> **Encapsulation** : When piece of *information* is added to a **Data** 

## Networking Layers

### Layer 1 (Physical) `fas:NetworkWired`

This layer reference the physical component of the hardware used in **Networking** and is the lowest layer that we will find. This layer uses electrical signals to transfer data between each other in a **Binary Numbering System** (1's and 0's).

**Example Device** : LAN Cable / Ethernet Cable that connecting devices

![[LAN Cable.png | LAN Cable / Ethernet Cable]]


### Layer 2 (Data Link) `fas:Link`

The **Data Link Layer** focuses on the *physical addressing* of the transmission. It receives a packet from the network layer (including the IP address for the remote computer) and adds in the physical **MAC** (Media Access Control) address of the receiving endpoint. Inside every network-enabled computer is a **N**etwork **I**nterface **C**ard (**NIC**) which comes with a unique MAC address to identify it.

> It’s also the job of the data link layer to present the data in a format suitable for transmission.

