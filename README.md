# DNS Analysis Mini-Project

## Overview

This mini-project aims to analyze different DNS queries and responses using various tools, including dig, nslookup, and ipconfig, along with capturing DNS packets using *Wireshark*. The project focuses on understanding how DNS queries are resolved, the behavior of DNS caching, and the differences between various DNS resolution methods.

## Tools Used

- *Wireshark*: A network protocol analyzer that allows capturing and interacting with data packets on the network.
- *dig*: A flexible command-line tool for querying DNS servers and retrieving information about DNS records.
- *nslookup*: A command-line tool used to query DNS to obtain domain name or IP address mapping.
- *ipconfig*: A command-line tool for Windows that displays the current network configuration and DNS cache.

## Objectives

- To capture and analyze DNS packets using Wireshark.
- To analyze the differences in DNS responses obtained from dig and nslookup.
- To investigate DNS caching behavior using ipconfig.


## Setup

1. *Install Necessary Tools:*
   - Install Wireshark from [the official website](https://www.wireshark.org/).
   - Ensure that dig and nslookup are available on your system. These tools are typically available on Linux and macOS. For Windows, you may need to use nslookup and install a tool like BIND to get dig.
   - For ipconfig, no installation is necessary as it is a built-in command on Windows.

2. *Network Configuration:*
   - Ensure you have internet access to perform DNS queries.
   - Optionally, configure your DNS settings to use a public DNS server like Google DNS (8.8.8.8).

## Usage

### Capturing DNS Packets with Wireshark

1. *Open Wireshark*:
   - Launch Wireshark and select the network interface you want to capture packets on.

2. *Set Up Filters*:
   - To focus on DNS traffic, set a display filter by entering dns in the filter bar.

3. *Start Capture*:
   - Click the start capture button to begin recording network packets.

4. *Perform DNS Queries*:
   - Use dig, nslookup, or perform any DNS queries from your browser or terminal.

5. *Stop Capture*:
   - After you have captured enough packets, stop the capture in Wireshark.

### Analyzing DNS Queries with dig

To perform DNS queries using dig, these are the commands we used to capture different packets.

```bash
dig <domain_name> A
dig <domain_name> AAAA
dig <domain_name> MX
```
### Analyzing DNS Queries with nslookup

To perform DNS queries using nslookup, these are the commands we used to capture different packets.

```bash
nslookup <domain_name>
nslookup -type=AAAA <domain_name>
```

### Analyzing DNS Caching using ipconfig

To observe DNS caching, we can take two packets one with caching and the other without.

To view the local cache

```bash
ipconfig /displaydns
```
To clear the cache
```bash
ipconfig /flushdns
```
As the dig command doesnt utilize the local cache, we can use ping to compare the response times.
```bash
ping <domain_name>
```
