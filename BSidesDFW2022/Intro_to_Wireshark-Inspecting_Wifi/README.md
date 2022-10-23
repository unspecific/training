# Exploring Wireless Networks with Wireshark

This introduction to Wireshare, the powerful protocol analyzer, will explain the the basics of the UI then work on a real time example of monitoring a WiFi network, including decrypting the packets.  This class will also utilize a few command line tools, such as airomon and airodump.  If you do not have a WiFi card that can be used in monitor mode, you will still be able to follow along via a packet capture provided.  
* Live USBs will be provided.
* Laptop needed for hands on.


## Introduction
- RedTeam Exercise with the Goal of monitoring the network, without leaving fingerprints on that Network
- Wireshark (formally Ethereal) for Analyzing the traffic and different protocols
- Always another way

## Goals
- Learn Wireshark UI
- Find WiFi Network
- Identify traffic necessary to get WiFi "password"
- Crack that Password
- Monitor WiFi network without being seen
- Identify interesting and useful traffic

## Installation
- Tools
  - iwconfig/ipconfig/ip
  - Wireshare (Wireshark.org)
  - airomon-ng
  - aircrack-ng

## Running Wireshark
- Root vs User
- CLI vs Alt-F2

## Interface Mode
- Standard vs Promiscuous vs Monitor
  - Standard - Only what is meant for you + Broadcast
  - Promiscuous - All IP traffic on your subnet that is delivered to you
  - Monitor - All network traffic that you can see (dependent on frequency)

## UI Basics
- Zones in Wireshark
  - Packet List
  - Packet Details
  - Packet Bytes
- Preferences
  - Layout
  - Name Resolution
- Capture Options
  - Output
  - Options


## Wireshark Capture Filters vs Display Filters
- Capture filter limit what is actually captured and can be saved
  - pcap/tcpdump syntax
  - https://wiki.wireshark.org/CaptureFilters
  - https://www.tcpdump.org/manpages/pcap-filter.7.html
- Display filters limit what is shown in Wireshark without modifying the packets captured
  - Wireshark specific syntax
  - https://wiki.wireshark.org/DisplayFilters
  - <right-click> -> Apply as Filter is your Friend

## WiFi Basics
- airomon-ng
- Packet Types
- 

## Capturing a Handshake

## WiFi Passwords vs PSK

## WiFi Session Keys

## Network/WiFi Monitoring
