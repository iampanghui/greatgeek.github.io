---
layout:     post
title:	What is a CNAME
subtitle:   
date:       2019-11-25
author: 	庞晖
header-img: img/post-bg-ios9-web.jpg
catalog: 	 true
tags: 	网络
---
以下是CNAME的wiki 链接,域名服务商还给我们提供了其他的设置记录项,在此一起补全:

 [wiki CNAME record](https://en.wikipedia.org/wiki/CNAME_record)

### Address Mapping records(A)
The record A specifies IP address (IPv4) for given host. A records are used for conversion of domain names to corresponding IP address.

### IP Version 6 Address records (AAAA)
The record AAAA (also quad-A record) specifies IPv6 address for given host. So it works the same way as the A record and the differences is the type of IP address.

**IP v4 地址为32位, IP v6地址为128位. 128/32=4, 既然IP v4的地址映射记录为A, 那么IP v6的地址映射记录为AAAA**

### Canonical Name records(CNAME)
The CNAME record specifies a domain name that has to be queried in order to resolve the original DNS query. Therefore CNAME records are used for creating aliases of domain names. CNAME records are truly useful when we want to alias our domain to an external domain. In other cases we can remove CNAME records and replace them with A records and even decrease performance overhead.

### Host Information records(HINFO)
HINFO records are used to acquire general information about a host. The record specifies type of CPU and OS. The HINFO record data provides the possibility to use operating system specific protocols when two hosts want to communicate. For security reasons the HINFO records are not typically used on public servers. 

### Integrated Services Digital Network records (ISDN)
The ISDN resource record specifies ISDN address for a host. An ISDN address is a telephone number that consists of a country code, a national destination code, a ISDN Subscriber number and, optionally, a ISDN subaddress. The function of the record is only variation of the A resource record function. 

### Mail exchanger record(RX)
The MX resource record specifies a mail exchange server for a DNS domain name. The information is used by Simple Mail Transfer Protocol (SMTP) to route emails to proper hosts. Typically, there are more than one mail exchange server for a DNS domain and each of them have set priority. 

### Name Server records (NS)
The NS record specifies an authoritative name server for given host. 

### Reverse-lookup Pointer records(PTR)
As opposed to forward DNS resolution (A and AAAA DNS records), the PTR record is used to look up domain names based on an IP address. 

### Start of Authority records(SOA)
The record specifies core information about a DNS zone, including the primary name server, the email of the domain administrator, the domain serial number, and several timers relating to refreshing the zone. 

### Text records (TXT)
The text record can hold arbitrary non-formatted text string. Typically, the record is used by Sender Policy Framework (SPF) to prevent fake emails to appear to be sent by you. 