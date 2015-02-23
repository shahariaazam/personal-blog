---
title: MikroTik NAT Port Forwarding - Access local pc from internet
layout: single_post
ogDescription: Learn how to access your local computer from your local network attached with MikroTik router from internet. Learn easily about MikroTik NAT Port Forwarding.
categories: [networking]
tags: [mikrotik]
---

Let me first tell you the real case scenario for this solution.

**Case 01**

- You have a local network that is designed and attached with a MikroTik router that is easily managable. You have multiple computer in your local network that is running
different types of applications or services. Your MikroTik router is also connected with a public ip provided by your ISP. Now you want that one of your local computer will be 
accessible via internet through that public ip. So in this case you can build web server, you can run mail server, you can run ftp server, other services, etc.. etc.

**Expectation**

- After solving this with this article anybody from internet (or whoever you give access) can access your local pc (192.168.10.23 or any local computer) from internet.
 
 
**Solutions**

- First let me describe you the visual design of network design in your home or office. See Figure: A-1.

![MikroTik NAT Port Forwarding example - Access Local PC from Internet](/assets/img/MikroTik_Nat_Port_Forwarding.jpg)

Your Public IP is 118.168.52.32 which was provided by your ISP and attached with your MikroTik router. And your local pc's are 192.168.10.20,  192.168.10.21,  192.168.10.22,  192.168.10.23.

Now in your 192.168.10.23 pc is running your web server and you want to make it accessible from outside your network that means from internet. Now open your **winbox** and connect to your router.

- Go to IP -> Firewall-> Select NAT Tab

![MikroTik NAT Port Forwarding example - Winbox configuration 1](/assets/img/MikroTik_Nat_Port_Forwarding_Winbox.jpg)

From General tab Select dstnat chain. From Protocol select tcp. From Dst. Port right down the port with which port the remote request will be connect. Here for web server I did 8080.

![MikroTik NAT Port Forwarding example - Winbox configuration 1](/assets/img/MikroTik_Nat_Port_Forwarding_winbox2.jpg)

Now go to Action tab and select Action to dst-nat, In ToAddresses select 192.168.10.23 and To Ports will be 8080. Now save that settings. 
When you want to access 192.168.10.23 web server from internet people can do that by hitting http://118.168.52.32:8080 and that will be 
 connected back and forth with 192.168.10.23.