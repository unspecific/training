# Introduction to Nmap

Have you heard of Nmap but don’t really know where to start?  Maybe you have run a few scans but don’t feel like you know what you are doing?  Have you been told Nmap is the tool you need, but you don’t understand how or why?  Introduction to Nmap is here to help you. We will start from the installation, to the first run of Nmap, to more complex scans, output, fingerprinting, Nmap scripts, and more.  This is the perfect place to get started or to understand better why nmap is so widely popular and useful.
* Live USBs will be provided.
* Laptop needed for hands on.


## Goals
- Identify what Nmap is
- Understand what nmap can do
- Understand how nmap works
- Learn nmap Options (the most imoprtant ones)
- Experience nmap scripting and the power of

## Introduction
- What is nmap -  Nmap is a Network Mapper that started as a simple Port Scanner and has sense grown to incorporate many more details about the target
- History of nmap - Nmap is first released in Phrack magazine Issue 51, Article 11. It doesn't have a version number because new releases were not planned. Nmap was about 2,000 lines long
- Official Nmap book -  Published on January 1, 2009 https://nmap.org/book/
- Installation
  - https://nmap.org/download.html

## Basic Scans
Nmap is easy to get started with.  ALl you have to do is provide a target.
- Input - IP or FQDN
- Output - Displaying ports that are open
- Root vs user

## Interpreting Scan Data
```
$ nmap 192.168.170.1
Starting Nmap 7.80 ( https://nmap.org ) at 2022-10-23 11:30 CDT
Nmap scan report for _gateway (192.168.170.1)
Host is up (0.0053s latency).
Not shown: 996 closed ports
PORT     STATE SERVICE
53/tcp   open  domain
80/tcp   open  http
443/tcp  open  https
1900/tcp open  upnp
```

## Scan types
- -s means Scan type
- List Scan (-sL)
- Ping Scan (-sn for No port scan)

# Ping types
- Ping determins whether or not to port scan a host
- -P means Ping Type
  - No Ping (-Pn) Assume all hosts are up
  - ICMP Echo Request (-Pe)
  - SYN on a Port (-PS<port>) - non-root will use Connect
  - ARP (-PR) - Default for local LAN --disable-arp-ping to disable

## Scan Types (Cont)
There are more options.  We will only cover common scan types.
- TCP Connect (-sT) - Default when not root
- TCP SYN (-sS)
- UDP (-sU)
- Protocol (-sO)

## Other Scan Options
- Traceroute (--traceroute)
- Don't resolve DNS (-n)
- Do it all (-A)
- Timing (-T) - Speed up or slow down scans
- Verbosity (-v -vv -vvv) - Include more details with each increase

## Input Options
- Lists
- Random
- Source

## Output formats
- Output Files
- Grepable
- XML
- Standard

## Interpreting Advanced Scan Data
- open vs filtered vs closed
- OS Fingerprinting
- Service Fingerprinting
- Script output


## Conclusions

## Q&A
- madhat@unspecific.com
- Twitter: @unspecific
- Counter.Social: @unspecific
- GitHub: https://github.com/unspecific/training/tree/main/BSidesDFW2022/nmap_101
