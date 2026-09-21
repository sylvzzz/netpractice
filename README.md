*This project has been created as part of the 42 curriculum by <a href="https://github.com/sylvzzz">dbotelho</a>.*

## Description

NetPractice is a hands-on networking project featuring 10 progressive levels that teach essential computer networking fundamentals. Through interactive problem-solving, you'll master TCP/IP addressing, subnet masks, default gateways, routing, and OSI layers by troubleshooting and configuring non-functioning network diagrams. This browser-based training provides practical experience in network administration, preparing you for real-world system administration and networking challenges.

The tool runs as a local web server and validates your configuration in real time.

## Instructions

### Running the training interface

```bash
cd net_practice
bash run.sh
```

`run.sh` starts a Python HTTP server on a free port and opens `http://localhost:<port>` in your browser (or prints the URL if it can't open one). Press `Ctrl-C` to stop the server.

### Exporting configurations

Once a level is solved, the interface lets you export your configuration as a JSON file. Save each file at the repository root with the naming convention `level<NUMBER>.conf` (for example, `level1.conf`).

### Submission

You must export and commit 10 configuration files, one per level, placed at the root of your repository:

```
level1.conf
level2.conf
...
level10.conf
```

## Resources

### Networking concepts studied

#### **OSI Model Layers**

The OSI (Open Systems Interconnection) model is a 7-layer framework that describes how data travels from one device to another across a network, from the physical cable all the way up to the application you're using. Each layer has a specific job, and understanding them helps explain *why* networks work the way they do.

| Layer | Name | Real-world example |
|-------|------|--------------------|
| 7 | Application | Your web browser requesting a page over HTTPS |
| 6 | Presentation | TLS encrypting the data before it leaves your machine |
| 5 | Session | The ongoing TCP connection between your browser and a server |
| 4 | Transport | TCP splitting your download into numbered segments with port numbers |
| 3 | Network | A router forwarding your packet toward its destination IP |
| 2 | Data Link | An Ethernet switch reading MAC addresses on your LAN |
| 1 | Physical | Your Ethernet cable plugged into your PC |

#### **TCP/IP Addressing and Subnetting**

Every device on a network needs a unique **IP address** so other devices know where to send data, similar to how a house needs a street address to receive mail.

- **IP Address**: A numeric label like `192.168.1.5` that identifies a device on a network.
- **Subnet Mask**: Splits an IP address into two parts, the *network* portion and the *host* portion. For example, with a subnet mask of `255.255.255.0`, the first three numbers (`192.168.1`) identify the network, and the last number (`.5`) identifies the specific device.
- **Subnetting**: The process of dividing one large network into smaller sub-networks. For example, an office might split `192.168.1.0/24` into separate subnets for the sales team (`192.168.1.0/25`) and the engineering team (`192.168.1.128/25`) to keep their traffic organized and isolated.
- This addressing scheme is used at **Layer 3 (Network)** of the OSI model, where routers use IP addresses to forward packets toward their destination.

#### **Default Gateways and Routing**

- **Default Gateway**: The IP address of the router that a device sends traffic to whenever the destination is *outside* its local network. Think of it as the "front door" out of your home network and onto the internet.
  - Example: Your laptop (`192.168.1.10`) wants to reach `google.com`. Since Google isn't on your local network, your laptop sends the request to its default gateway (e.g., `192.168.1.1`), which is usually your router.
- **Static Routes**: Manually configured paths that tell a router how to reach a specific network. For example, a network administrator might add a rule saying "to reach `10.0.5.0/24`, send traffic through `10.0.0.1`."
- Routing happens at **Layer 3**, working alongside IP addressing to make sure packets take the correct path across multiple networks.

#### **Routers and Switches**

- **Routers (Layer 3)**: Connect *different* networks together and use IP addresses to decide where to forward traffic. A home router connects your local network (LAN) to your internet service provider's network (WAN).
- **Switches (Layer 2)**: Connect devices *within the same* network and use MAC addresses (hardware addresses) to deliver data to the correct device. For example, when your laptop sends a print job to a printer on the same office network, the switch reads the printer's MAC address and forwards the data directly to it.
- **Putting it together**: Routers typically sit *between* subnets (directing traffic between networks), while switches sit *within* a subnet (directing traffic between devices on the same network). This mirrors the OSI model, where switches operate at Layer 2 and routers operate at Layer 3.

---

### References

- [Subnet CheatSheet](https://subnet.ninja/subnet-cheat-sheet/)

### AI usage

I used AI Claude simply to refresh my memory on networking concepts I had learned before 42 but had forgotten a bit, mainly subnetting and routing calculations and for polishing the README.md.
