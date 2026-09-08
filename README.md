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

This project covers the following concepts, each with a real-world example for better understanding of the OSI model:

| Layer | Name | Real-world example |
|-------|------|--------------------|
| 7 | Application | Your web browser requesting a page over HTTPS |
| 6 | Presentation | TLS encrypting the data before it leaves your machine |
| 5 | Session | The ongoing TCP connection between your browser and a server |
| 4 | Transport | TCP splitting your download into numbered segments with port numbers |
| 3 | Network | A router forwarding your packet toward its destination IP |
| 2 | Data Link | An Ethernet switch reading MAC addresses on your LAN |
| 1 | Physical | Your Ethernet cable plugged into your PC |

Additional concepts covered:

- **TCP/IP addressing and subnetting:** Designing IP address schemes, calculating subnet masks, and dividing networks into subnets.
- **Default gateways and routing:** Configuring hosts to send traffic outside their local subnet through a gateway, and writing static routes on routers.
- **Routers and switches:** Placing Layer 3 devices (routers) between subnets and Layer 2 devices (switches) within subnets.

### References

- [Subnet CheatSheet](https://subnet.ninja/subnet-cheat-sheet/)

### AI usage

I used an AI assistant (Claude) to quickly refresh my memory of networking concepts I had learned before 42 but had partly forgotten, mainly subnetting and routing calculations.
