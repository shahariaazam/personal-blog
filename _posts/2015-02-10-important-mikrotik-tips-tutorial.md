---
title: Some Important MikroTik Tips and Tricks
layout: single_post
ogDescription: Learn some important Mikrotik simple tips and tricks to maintain your mikrotik more effectively to maintain your network.
categories: [Networking]
tags: [mikrotik]
---

###Port Forwarding to local IP/PORT
Type the following value into a Terminal window to enter this port forwarding rule.

```bash
/ip firewall nat
add action=dst-nat chain=dstnat disabled=no dst-port=80 in-interface=ether1-gateway protocol=tcp to-addresses=192.168.1.20 to-ports=80
```

In the above MikroTik NAT forwarding rule add through MikroTik RouterOS terminal what I am doing with the above command?
We are just forwarding any kinds of request to our main IP in 80 and forwarding that connection to `192.168.1.20` ip which is in my local network and port **80** will be used from 192.168.1.20 for that request.
