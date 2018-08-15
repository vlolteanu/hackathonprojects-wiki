# IPv6 Segment Routing

IPv6 Segment Routing (SRv6) [1] is a modern version of source routing that is being standardized within the IETF to address a variety of use cases in ISP, datacenter and enterprise networks. Its inclusion in recent versions of the Linux kernel [2] enables researchers to explore and extend this new protocol. Some papers on SRv6 can be found at this [link](https://segment-routing.org/index.php/References/ScientificPapers).

The goal of this hackathon challenge is to learn what IPv6 Segment Routing
is and also to experiment with two of its use cases.
- SRN [3] are a variant of the Software Defined Network (SDN) architecture based on SRv6 instead of OpenFlow.
- SRv6Pipes [4] enable network architects to design bytestream in-network functions for Service Function Chaining (SFC).

This challenge is suitable to any student, industrial and researcher in networking.
A basic background in TCP/IP stack is required.
We encourage participants to have prior experience with IPv6 but this is not required.

We will make available a Vagrant box running a kernel with SRv6 enabled and all the needed tools.
Participants should install [Virtualbox with its extension pack](https://www.virtualbox.org/wiki/Downloads) and [Vagrant](https://www.vagrantup.com/downloads.html) prior to the hackathon.

Contact : Mathieu Jadin (email: mathieu.jadin@uclouvain.be) <br />
Website : https://segment-routing.org <br />
Github : https://github.com/segment-routing

## Discovering IPv6 Segment Routing

We propose several challenges to discover IPv6 Segment Routing:
- Rerouting pings to a specific path
- Rerouting traffic to go through a specific middlebox: firewall,...
- Making SRv6 work with IPv4 through encapsulation
- [...]

## SRN: Software Defined Networks with SRv6

SRN [3] are an SDN-like architecture based on SRv6.
SRN enable clients to send their policies (e.g., desired latency or bandwidth) to a network controller through DNS.
The controller computes a path matching the client requirements.
After that, it sends back an SRv6 Header in the DNS reply.
Finally, the client inserts the SRv6 Header in all its packets causing the traffic to follow a path respecting its policies.
The demo [5] during the main conference will demonstrate this use case.

This interaction with the controller requires a modification of the applications.
The goal of this challenge is to modify an existing open-source application to benefit from this SDN architecture. Some examples of such applications could be [curl](https://curl.haxx.se/), [iperf](https://software.es.net/iperf/), [openssh](https://www.openssh.com/) or any other application using the network.

For this challenge, basic knowledge of the DNS protocol is encouraged.

## SRv6Pipes: Service Function Chaining with SRv6

SRv6Pipes [4] enable to combine TCP proxies with SRv6 to provide in-network functions that operate on bytestreams.
The demo [5] during the main conference will demonstrate this use case.

The goal of this challenge is to implement a custom network function.
A first example of such a function could be an encryption and decryption service.
A second one could be a function logging the conversation to a file.

For this challenge, basic knowledge of C language is encouraged.

## References

[1] S. Previdi, et al. IPv6 Segment Routing Header (SRH). draft-ietf-6man-segment-routing-header-14 (work in progress), June 2018.<br />
[2] David Lebrun and Olivier Bonaventure. Implementing IPv6 Segment Routing in the Linux Kernel. Applied Networking Research Workshop 2017, July 2017. <br />
[3] David Lebrun, Mathieu Jadin, François Clad, Clarence Filsfils and Olivier Bonaventure. Software Resolved Networks: Rethinking Enterprise Networks with IPv6 Segment Routing. Symposium on SDN Research 2018. <br />
[4] Fabien Duchêne, David Lebrun and Olivier Bonaventure. SRv6Pipes: enabling in-network bytestream functions. IFIP Networking 2018. <br />
[5] F. Duchêne, M. Jadin and O. Bonaventure. Exploring various use cases for IPv6 Segment Routing. SIGCOMM Posters and Demos, 2018.
