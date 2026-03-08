# Network-Traffic-Analysis
An analysis of network traffic using Wireshark, demonstrating packet capture techniques and the security vulnerabilities of unencrypted HTTP communication.

# Network Traffic Analysis - Wireshark

## Objective
The objective of this project is to capture and analyze network traffic using Wireshark to observe the initial handshake process of secure connections. Specifically, this project demonstrates how network interceptors can identify target websites by analyzing plain-text data exposed during the TLS routing process.

## Tools Used
* **Wireshark:** For packet sniffing, protocol analysis, and traffic observation.
* **Web Browser:** To generate specific HTTPS traffic for analysis.

## Files in this Repository
* TLS-Handshake-Capture.pcapng: The raw master capture file containing the network traffic data.
* IITP-TLS-Client-Hello.jpg: Packet details highlighting the Server Name Indication (SNI) for the IIT Patna domain.
* Google-TLS-Client-Hello.jpg: Packet details highlighting the SNI for the Google domain.
* Capture-Interface-Details.jpg: Frame and Ethernet interface metadata from the active capture.
* TCP-Reset-Packet-Analysis.jpg: Analysis of a specific Transmission Control Protocol (TCP) reset packet.

## Methodology
1. Initialized Wireshark and began capturing packets on the active network interface.
2. Navigated to secure websites (registrations.iitp-cep.in and www.google.com) to generate TLS traffic.
3. Stopped the packet capture and isolated the relevant traffic using display filters.
4. Analyzed the Client Hello packets within the Transport Layer Security (TLS) protocol to observe exposed metadata.

## Findings
By analyzing the network traffic, I observed the initial handshake process for secure connections. Specifically:

**Server Name Indication (SNI) Exposure** : Even though the connections to the target domains utilize TLSv1.3 encryption, the initial Client Hello packet transmits the target website's domain name in plain text.

  
**Observation** : This demonstrates that while HTTPS encrypts the payload (the actual web page data or passwords), network interceptors can still easily map which specific websites a user is visiting by analyzing the SNI data in the transport layer.

## Conclusion
This exercise highlights that while TLS/SSL encryption is critical for securing data payloads, metadata such as routing information and SNI remains visible. Understanding this limitation is essential for comprehensive network security and privacy threat modeling.

---

## Visual Evidence

1. Capture Interface Details [Capture Interface Details](https://github.com/Kumaradarshiitp/Network-Traffic-Analysis/blob/main/Capture-Interface-Details.jpg)

2. Google TLS Client Hello  [Google TLS Client Hello](https://github.com/Kumaradarshiitp/Network-Traffic-Analysis/blob/main/Google-TLS-Client-Hello.jpg.png)

3. IIT Patna TLS Client Hello [IITP TLS Client Hello](https://github.com/Kumaradarshiitp/Network-Traffic-Analysis/blob/main/IITP-TLS-Client-Hello.jpg.png)

4. TCP Reset Packet Analysis [TCP Reset Packet Analysis](https://github.com/Kumaradarshiitp/Network-Traffic-Analysis/blob/main/TCP-Reset-Packet-Analysis.jpg.png)


   
