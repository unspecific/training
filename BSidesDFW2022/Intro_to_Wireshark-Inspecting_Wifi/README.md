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
  - iwconfig/ipconfig/ip (net-tools, iproute2, wireless-tools)
  - Wireshark (Wireshark.org, wireshark)
  - airmon-ng (aircrack-ng)
  - airodump-ng (aircrack-ng)
  - aircrack-ng (aircrack-ng)
  - wpa_passphrase (wpasupplicant)


## Running Wireshark
- Root vs User
- CLI vs Alt-F2/Menu

## Wifi Interface Mode
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
- Adding/Removing Columns
  - Apply as Column
- Wireless -> WLAN Traffic

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
  - Channel Hopping - Loses packets
  - Specifying Channel - Collect more packets
- airodump-ng
- Packet Types
  - Beacons (type 0x0008)
  - Probe-Requests (type 0x0004)
  - Probe-Response (type 0x0005)
  - Data (type 0x0020)
  - Acknowledgment (type 0x001d)  
  - Authentication (type 0x000b)
  - Key/EAPOL

## Identify Target
- Select Channel
  - Monitor traffic
  - Update airomon-ng
- Identify Beacon && Router
  - Select SSID
  - Wireshark Display Filters
- Identify all Traffic to and from Target
  - Wireshark Display Filters

## Capturing a Handshake
- Key/EAPOL packets
  - 4 Packet Handshake
- Beacons
- Exporting as pcapng file

## Crack That Password
- aircrack-ng
- Dictionary/Wordlists
  - Rockyou
- Tada!!!

## WiFi Passwords vs PSK
- Wireshark Preferences
  - IEEE 802.11
  - wpa-pass
  - wpa-psk
    - wpa_passphrase (SSID, Passphrase)

## Network/WiFi Monitoring
- DNS Traffic
- What other traffic
- Plain Text protocols
  - Usernames and Passwords

## Conclusions

## Q&A
