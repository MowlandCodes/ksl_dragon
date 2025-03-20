#learning/networking/fundamentals

---


> [!info] Info
> This content is extracted from [**TryHackMe | OSI Layer**](https://tryhackme.com/room/osimodelzi)

## Definition

The **OSI** model (or **O**pen **S**ystems **I**nterconnection Model) is an essential model used in networking.  This critical model provides a framework dictating how all networked devices will send, receive and interpret data.

![[OSI Layer.png]]

> **Encapsulation** : When piece of *information* is added to a **Data** 

## Networking Layers

### Layer 1 (Physical) `ris:Server`

This layer reference the physical component of the hardware used in **Networking** and is the lowest layer that we will find. This layer uses electrical signals to transfer data between each other in a **Binary Numbering System** (1's and 0's).

**Example Device** : LAN Cable / Ethernet Cable that connecting devices

![[LAN Cable.png | LAN Cable / Ethernet Cable]]


### Layer 2 (Data Link) `fas:Link`

The **Data Link Layer** focuses on the *physical addressing* of the transmission. It receives a packet from the network layer (including the IP address for the remote computer) and adds in the physical **MAC** (Media Access Control) address of the receiving endpoint. Inside every network-enabled computer is a **N**etwork **I**nterface **C**ard (**NIC**) which comes with a unique MAC address to identify it.

> It’s also the **job of the data link layer** to ==present the data in a format suitable for transmission==.


### Layer 3 (Network) `fas:NetworkWired`

The third layer of the OSI model (network layer) is where the magic of **Routing & Re-Assembly of Data** takes place (from these small chunks to the larger chunk). Firstly, routing simply determines the most optimal path in which these chunks of data should be sent.

> Devices such as **routers** ==capable of delivering packets using IP addresses== are known as **Layer 3 devices**, because they are capable of working at the third layer of the OSI model.

![[Network.png]]

### Layer 4 (Transport) `fas:Globe`

Layer 4 of the OSI model plays a vital part in **transmitting data across a network** and can be a little bit difficult to grasp. When data is sent between devices, it follows one of two different protocols that are decided based upon several factors:
- **TCP** (Transmission Control Protocol)
- **UDP** (User Datagram Protocol)

#### TCP (Transmission Control Protocol)

**TCP (Transmission Control Protocol)** is designed with **reliability** and guarantee in mind. This protocol reserves a *constant connection between the two devices for the amount of time it takes for the data to be sent and received*.

Not only this, but **TCP incorporates error checking** into its design. Error checking is how TCP can guarantee that data sent from the small chunks in the session layer (layer 5) has then been received and reassembled in the same order.

**Advantages** and **Disadvantages** of TCP:

|                                  ==**Advantages of TCP**==                                   |                                                             ==**Disadvantages of TCP**==                                                              |
| :------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------------: |
|                             Guarantees the **accuracy of data**.                             | **Requires a reliable connection between the two devices**. If one small chunk of data is not received, then the entire chunk of data cannot be used. |
| **Capable of synchronising two devices** to prevent each other from being flooded with data. |           A **slow connection can bottleneck another device** as the connection will be reserved on the receiving computer the whole time.            |
|                      Performs a lot more processes for **reliability**.                      |                     TCP is **significantly slower** than UDP because more work has to be done by the devices using this protocol.                     |

> [!important] Tips
> TCP is used for service such as **File Sharing**, **Browsing**, or **Sending Email** that requires reliable connection between 2 devices. This usage is because these services require the data to be accurate and complete

> [!example] Example
> Below is the example of TCP Protocol in Action where a *Webserver* sends an Image of a Cat that being divided into several **Tiny Packets** by the protocol and then re-constructed by the Receiving client into the correct order
> ![[TCP in Action.png]]
> 

#### UDP (User Datagram Protocol)

**UDP (User Datagram Protocol)** is the opposite of TCP where it doesn't need a reliable connection between the Client and Server, it will always transfer data to client whether it's safely arrived to the destined client or not. There is **==No Synchronization between the two devices or guarantee==**.

Whilst this sounds disadvantageous, it does have its own merits, that described as below:

|                                                 ==**Advantages of UDP**==                                                 |                              ==**Disadvantages of UDP**==                              |
| :-----------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------: |
|                                              UDP is **Much Faster** than TCP                                              |               UDP **doesn't care whether the data is received or not**.                |
| UDP leaves the application layer (user software) to decide if there is any **control over how quickly packets are sent**. |             It is **quite flexible to software developers** in this sense.             |
|                         UDP **does not reserve a continuous connection on a device** as TCP does.                         | This means that **unstable connections result in a terrible experience** for the user. |

> [!tip] Tips
> UDP is useful in situations where there are small pieces of data being sent. For example, protocols used for discovering devices (_ARP_ and _DHCP_ that we discussed in [Room 2 - Intro to LAN](https://tryhackme.com/room/introtolan)) or larger files such as video streaming (where it is okay if some part of the video is pixelated. Pixels are just lost pieces of data!)

