*This project has been created as part of the 42 curriculum by mgumberi.*

# Network Addressing and Routing Training

## Description

The goal of this project is to learn how IPv4 networks are built and how packets travel through them. A browser-based training interface shows a small network (hosts, switches, routers, and the Internet) in 10 levels of growing difficulty. In each level I fill in the editable fields (IP addresses, subnet masks, default gateways, and routing table entries) until every goal passes. The grey fields are fixed by the level and act as constraints.

Overview of what the levels cover:

- valid IP addresses and contiguous subnet masks
- network, broadcast and usable host addresses
- one subnet per link, with no overlaps
- default gateways and static routes (`destination network => next hop`)
- longest-prefix matching and the default route `0.0.0.0/0`
- two routers in a row, a switch, and routing to the Internet
- private address ranges, which are not routed over the Internet
- both directions of a path (forward and reverse way)

## Instructions

### Run the training interface

```bash
./run.sh
```

The script starts a local web server and prints a URL such as `http://localhost:<port>/level1.html`. Open it in a browser, then switch levels by changing the file name in the URL (`level1.html` ... `level10.html`).

### Solve a level

1. Fill in the white fields (IP, mask, gateway, route destination).
2. Read the log panel on the right. Each goal shows the forward way and the reverse way, and the first red line points to the problem.
3. Repeat until all goals are green.

### Export a configuration

When a level passes, export its configuration with the export button of the interface. [Adjust: name the exact button and the file format your interface produces.] Save the file under the level's name (for example `level1`, ..., `level10`).

### Submission requirements

- `README.md` at the root of the Git repository.
- **10 exported configuration files, one per level, placed at the repository root.**

## Resources

### Networking concepts studied

- **TCP/IP addressing:** IPv4 address structure (four octets), network part vs host part.
- **Subnet masks and CIDR:** contiguous masks (`255.255.255.192` = `/26`), network address, broadcast address, block sizes, aggregation of several networks into one route.
- **Default gateways:** the gateway must be on a directly connected network and must be the neighbour's interface.
- **Routers and routing tables:** connected networks, static routes, default route, longest-prefix match, next-hop forwarding, reverse path, routing loops.
- **Switches:** forward frames inside one network and do not change the IP addressing.
- **Private and special addresses:** RFC 1918 ranges (`10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`), loopback, link-local, multicast.
- **OSI layers:** layer 2 (switches, links) and layer 3 (IP, routers).

### References

- RFC 791 - Internet Protocol
- RFC 1918 - Address Allocation for Private Internets
- RFC 4632 - Classless Inter-domain Routing (CIDR)
- RFC 1122 - Requirements for Internet Hosts
- IPv4 subnet calculators (used to check ranges and block sizes)
- Course material of the 42 curriculum on networking

### Use of AI

AI (Claude) was used as a tutor to:

- explain concepts (subnet masks, block sizes, overlapping subnets, gateways, private addresses, longest-prefix match)
- help me read the simulator logs and understand what each error message means
- write a checklist of rules to verify an answer before submitting
- draft this README

The configurations were entered and tested by me in the interface. AI suggestions were checked against the log output and corrected when they were wrong.
