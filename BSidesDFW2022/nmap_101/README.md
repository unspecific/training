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
- Root vs user - Scan types change

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
- List Scan (-sL) - Display what would be scanned, can be used to expand CIDR notation
- Ping Scan (-sn for No port scan) - Report which hosts are up, Default is TCP Connect scan on 80

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
- TCP SYN (-sS) - Can only be used as root - half handshake
- UDP (-sU)
- Protocol (-sO) - Can only be used as root - Instead of ports scans for what protocols are available on target

## Target Specific Options
- Scan ports - Defaults to top 1000 commonly detected ports specified by nmap
- Specify Ports (-p)
  - Allows for a list of single ports or ranges, comma separated (-p1-1023,3306,3389,8080)
  - Can mix TCP and UDP (-p T:80,443,U:53)
- Fast Scan (-F) only uses the top 100 ports
- Specify how many ports (--top-ports <#>)

## Other Scan Options
- Traceroute (--traceroute)
- Don't resolve DNS (-n)
- Do it all (-A)
- Timing (-T) - Speed up or slow down scans 1-5, 1 slowest - 5 fastest
- Verbosity (-v -vv -vvv) - Include more details with each increase

## Input Options
- Input options are signified by -i
- Lists (-iL<filename>) - SPecify a file that has a list of IPs, networks, or FQDNs (or mixture of)
- Random (-iR<#>) - Choose random targets
- Default is the last entries are the targets, supports multiple formats
  - IPs (192.169.1.10)
  - FQDNs (scanme.nmap.org) - Will do a DNS lookup to determine the IP.  Will chose the first entry if multiple IPs are returned
  - CIDR Notation (10.0.0.0/8, 192.168.0.0/16) - Will expand to a list of IPs.  See -iL to verify the IPs included
  - Ranges - (192.168.10-20.- 192.168.13.1-20 192.168.13,166,170-180.1) This can get complicated but is very powerful
  - These input options can be used together on in an input file. CIDR and ranges can be included together for example

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
