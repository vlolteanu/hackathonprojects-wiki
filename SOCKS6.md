# SOCKS version 6

Version 6 of the SOCKS protocol brings a number of improvements to the table, including:

* Low RTT usage: the client sends as much information as possible upfront: the server's address, application data (e.g. an HTTP GET) and authentication data.
* Lightweight idempotence mechanism: replays can be avoided, making TCP Fast Open and 0-RTT TLS session resumption safe to use, regardless of the protocol running on top of SOCKS.
* Extensibility via options

Most of the SOCKS-related projects require C (and maybe some C++) skills and a Linux system to work on (a VM is ok). You will also need:

* libboost-dev(el)
* qt4-qmake

The following may come in handy depending on the project you choose:

* mininet
* MPTCP kernel

We will provide a library for generating and parsing SOCKSv6 messages ([libsocks6msg](https://github.com/45G/libsocks6msg)), as well as a proxy and a transparent proxifier ([sixtysocks](https://github.com/vlolteanu/sixtysocks)). The message library (libsocks6msg) is platform-independent, but sixtysocks only works on Linux. 

## Flow completion time probe

An FCT probe can be used to determine whether a SOCKS proxy can speed up the completion of a short flow.

Completing a small request (e.g. an HTTP GET of a small file) normally takes 2 RTTs when the server is contacted either directly or via an on-path SOCKSv6 proxy.
Using TFO between the client and the proxy shaves one client-proxy RTT off the FCT, in essence making SOCKSv6 outperform TCP.

But what if the proxy is not on path? Can SOCKS still be faster than TCP in spite of the "detour"? Given a proxy and a server, a simple tool can be used to determine whether going via the proxy can speed up an HTTP request, and by how much.

Note: You can use [mininet](http://mininet.org/) to simulate network topologies with arbitrary latencies.

## Remotely setting a socket option

This project is about extending SOCKSv6 and having the proxy call setsockopt() on one of its sockets.

SOCKSv6 features Stack options, which were envisioned as a way to manipulate *nix socket options on the proxy. We suggest adding support for setsockopt(..., SOL_IP, IP_TOS, ...). The project would consist of two steps:

* Modifiying the message library (libsocks6msg) to add a new stack option.
* Moifying the sixtysocks proxy to honor said option.

Note: Some C++ skills are required.

## LD_PRELOAD library for clients

Compiled applications can be turned into SOCKS clients by using a preloaded library to intercept network-related library calls. For example, calling connect() would instead connect to an arbitrary proxy and make a SOCKS request.

[Dante](https://www.inet.no/dante/download.html) features such a library, but it only supports versions 4 and 5. This project consists of making the library also speak version 6.

## Wireshark dissector for SOCKSv6

## Adding SOCKSv6 support to an app already using some other version of SOCKS

Open-source web browsers (e.g. Firefox or Chromium) are ideal candidates for this project.

## MPTCP Proxy bypass

Mobile network operators deploy MPTCP on mobile phones to "bond" LTE and WiFi and offer faster network speeds. Since there is very little adoption of MPTCP on the server side, a proxy is needed to terminate the MPTCP connections and communicate with the servers using regular TCP.

If a server does support MPTCP, clients would gain no extra bandwidth by using the proxy and would just end up wasting the proxy's resources. SOCKSv6 proxies can signal the availability of MPTCP on the server side.

This project entails modifying a proxifier (either sixtysocks or the one based on shadowsocks). The proxifier has to learn which servers support MPTCP and forego the use of the proxy on further connection attempts.

Note: Running a kernel with MPTCP support is definitely a plus, but it's not required. We will have a proxy running on an MPTCP box.

## Resources

* [SOCKSv6 IETF Draft](https://tools.ietf.org/html/draft-olteanu-intarea-socks-6-04)
* [SIGCOMM poster](http://nets.cs.pub.ro/~vlad/socks6/socks6posterpubredux.pdf) [abstract](http://nets.cs.pub.ro/~vlad/socks6/p126-Olteanu.pdf)
* Repos [https://github.com/45G](https://github.com/45G)
	* [libsocks6msg](https://github.com/45G/libsocks6msg)
	* [libsocks6util](https://github.com/45G/libsocks6util)
	* [sixtysocks](https://github.com/vlolteanu/sixtysocks) (feature-rich proxifier and proxy; under heavy development)
	* [Prototype based on Shadowsocks](https://github.com/45G/shadowsocks-libev) (basic feature set, but based on a popular codebase)
