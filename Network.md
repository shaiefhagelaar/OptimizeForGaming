# Network

-----

## Tweaks

-----

    * Disable Automatic TCP Adjustment                   = -

This refers to TCP Receive Window Auto-Tuning. Windows monitors bandwidth and latency to dynamically scale the receive window size for maximum throughput

Disabling this (netsh int tcp set global autotuninglevel=disabled) fixes compatibility with legacy routers that don't support RFC 1323, but it can severely limit speeds on modern high-speed networks

Known as Receive Window Auto-Tuning. Windows automatically adjusts the TCP receive buffer size based on bandwidth and latency. Disabling it (netsh int tcp set global autotuninglevel=disabled) limits the window to a fixed 64KB, which can prevent "throttling" in specific legacy environments but usually degrades performance on high-speed fiber connections

https://learn.microsoft.com/en-us/troubleshoot/windows-server/networking/receive-window-auto-tuning-for-http

https://windowsforum.com/threads/mastering-tcp-ip-settings-in-windows-11-a-complete-guide-for-optimal-network-management.364234/

-----

    * Disable IPv6                                       = -

The Internet Protocol version 6. Microsoft officially recommends not disabling IPv6. Many Windows components (like DirectAccess or HomeGroup) rely on it. Disabling it can cause slight delays in name resolution if the OS keeps trying to use a disabled stack

https://learn.microsoft.com/en-us/answers/questions/5722909/how-to-disable-ipv6-in-windows-11-home

https://learn.microsoft.com/en-us/troubleshoot/windows-server/networking/configure-ipv6-in-windows

-----


    * Disable Ipv6 Transistion Services                  = -

Refers to technologies like 6to4, ISATAP, and Teredo. These encapsulate IPv6 packets inside IPv4. Disabling these is common when you have a native IPv4 or IPv6 connection to reduce the CPU overhead of packet tunneling

https://learn.microsoft.com/en-us/troubleshoot/windows-server/networking/configure-ipv6-in-windows

-----

!!! CAUTION !!!

Disabling the Windows Firewall Profiles (Domain, Private, Public) to stop the inspection of every incoming/outgoing packet

    * Disable Security Profiles                          = -

Usually refers to Windows Firewall Profiles (Domain, Private, Public). Disabling these reduces the processing time per packet (filtering), but it removes the primary layer of OS network defense

There are safer ways to go on about this for example:

1. Exclusions
2. Sandboxing
3. VM's
4. Trusted-vendor installers

https://windowsforum.com/threads/turning-off-windows-security-safe-temporary-use-and-permanent-change-guide.394249/

-----

    * Enable Weak Host Send/Recieve                      = -

A "Weak Host" model allows a host to send or receive packets on an interface even if the IP address isn't strictly assigned to that specific physical port

In a Weak Host Model, a host can send/receive packets on an interface even if the destination/source IP address is assigned to a different interface on that same host. Enabling this can improve multi-homed connectivity but is often disabled for security to prevent spoofing


https://learn.microsoft.com/en-us/previous-versions/technet-magazine/cc137807(v%3Dmsdn.10)

-----

    * Enhance Connection Stability                       = +

Typically involves configuring TCP Keep-Alive intervals. By ensuring the "heartbeat" of a connection is frequent and consistent, the system prevents dead gateways or intermediate routers from dropping "idle" sessions

https://learn.microsoft.com/en-us/troubleshoot/windows-client/networking/tcpip-and-nbt-configuration-parameters

-----

    * Improve Network Packet Acknowlegdement             = +

Adjusting the TcpAckFrequency (the "Delayed ACK" timer)

Setting this to 1 sends an acknowledgement for every packet immediately, significantly reducing latency in games at the cost of slightly higher bandwidth overhead

https://learn.microsoft.com/en-us/troubleshoot/windows-server/networking/registry-entry-control-tcp-acknowledgment-behavior

-----

    * Optimize IPv6 Address Handeling                    = -

Disabling IPv6 Privacy Extensions (Temporary Addresses) to maintain a static interface ID

https://learn.microsoft.com/en-us/troubleshoot/windows-server/networking/configure-ipv6-in-windows

-----

    * Optimize MTU Size                                  = +

Tuning the Maximum Transmission Unit to ensure packets are as large as possible without triggering fragmentation

https://learn.microsoft.com/en-us/troubleshoot/windows-server/networking/default-maximum-transfer-unit-network-topologies

-----

    * Optimize Neighbor Cache                            = +

Increasing the Neighbor Cache Limit (ARP/NDP) to prevent the system from constantly needing to re-resolve MAC addresses for local devices

https://learn.microsoft.com/en-us/troubleshoot/windows-server/networking/default-maximum-transfer-unit-network-topologies

-----

    * Optimize Offloading Features                       = -

Disabling Receive Segment Coalescing (RSC) and Large Send Offload (LSO)

https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh997024(v=ws.11)

-----

    * Optimize Packet Coalescing                         = -

Disabling Packet Coalescing (and related DMA coalescing) which forces the NIC to process every packet immediately rather than waiting to batch them

https://learn.microsoft.com/en-us/windows-hardware/drivers/network/overview-of-packet-coalescing

-----
    
    * Optimize Winsock Buffer Behaviour                  = +

Tuning the AFD (Ancillary Function Driver) and send/receive buffers to prevent "Bufferbloat" while ensuring the network pipe stays full

https://learn.microsoft.com/en-us/windows/win32/winsock/high-performance-windows-sockets-applications-2

-----
    
    * Reduce Network Background Interruptions            = +

Tuning Interrupt Moderation

https://learn.microsoft.com/en-us/windows-hardware/drivers/network/interrupt-moderation

-----
    
    * Set Stabilize Network Routing                      = +

https://learn.microsoft.com/en-us/windows-365/enterprise/optimization-of-rdp
-----

-----
    
    * Disable Heuristics                                 = -

TCP Window Scaling Heuristics is a Windows feature where the OS monitors connectivity and, if it "thinks" a network doesn't support scaling, it restricts the TCP window size to prevent connection drops

https://learn.microsoft.com/en-us/troubleshoot/windows-server/networking/receive-window-auto-tuning-for-http

-----
    
    * Optimize MPP                                       = -

In Windows networking, this usually refers to RSS (Receive Side Scaling). RSS allows the network load from a single network adapter to be distributed across multiple CPU cores rather than bottlenecking on Core 0

Ensuring RSS is enabled and the "Max Number of RSS Processors" is tuned to your CPU count prevents a single core from being overwhelmed by high-speed packet processing

https://learn.microsoft.com/en-us/windows-hardware/drivers/network/introduction-to-receive-side-scaling

----

## Adapter Tuner

----

Pick what applies for your system:

----

    * Optimize WiFi Adapter                              = -

Direct hardware-level tuning of the Physical (PHY) and Data Link layers of the wired connection

https://learn.microsoft.com/en-us/windows-server/networking/technologies/network-subsystem/net-sub-performance-tuning-nics?tabs=powershell

-----

    * Optimize Ethernet Adapter                          = +

Direct hardware-level tuning of the Physical (PHY) and Data Link layers of the wired connection

Flow Control: Usually disabled to prevent the NIC from sending "Pause" frames which can increase latency

Set to the maximum rated speed (e.g., 1.0 Gbps Full Duplex) to prevent "Autonegotiation" loops or downgrades

https://learn.microsoft.com/en-us/windows-server/networking/technologies/network-subsystem/net-sub-performance-tuning-nics?tabs=powershell

-----

## BufferBloat

A phenomenon where excessive buffering in network equipment (like routers or switches) causes high latency and jitter, especially during high-load periods (like downloading while gaming)

While primarily a router-side issue (fixed with SQM/FQ_Codel), on the Windows side, it is mitigated by reducing Send/Receive Buffer sizes and disabling Interrupt Moderation, which forces the system to empty the "buffers" more frequently

https://learn.microsoft.com/en-us/windows-server/networking/technologies/network-subsystem/net-sub-performance-top

https://learn.microsoft.com/en-us/windows-server/networking/technologies/network-subsystem/net-sub-performance-tuning-nics?tabs=powershell

-----

Pick what applies for your system:

    * Normal Mode                                        = -
    * Ultra Low Bufferbloat                              = +

## Network Priority

You can toggle the on/off button to add a game for a more stable network connection
