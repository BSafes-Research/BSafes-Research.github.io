---
layout: default
title: Part I - Network security best practices and mitigations 
parent: . June 2021, Deploying Secure Unified Communications/Voice and Video over IP Systems  
grand_parent: NSA 
nav_order: 20 
---
<style>
.dont-break-out {
  /* These are technically the same, but use both */
  overflow-wrap: break-word;
  word-wrap: break-word;

  -ms-word-break: break-all;
  /* This is the dangerous one in WebKit, as it breaks things wherever */
  word-break: break-all;
  /* Instead use this non-standard one: */
  word-break: break-word;
}
</style>

<div class="dont-break-out" markdown="1">
  
1. TOC
{:toc}


## Part I: Network security best practices and mitigations
To securely deploy Unified Communications / Voice and Video over Internet Protocol (UC/VVoIP) systems, the network is the first critical area to implement security protections. Part I of *Deploying Secure Unified Communications/Voice and Video over IP Systems* addresses how to secure the network of one of these systems.

UC/VVoIP call-processing security is dependent on a defense-in-depth approach. UC/VVoIP call-processing network elements are on the data network, requiring careful deployment and configuration of the network infrastructure to address possible threats related to UC/VVoIP systems. The data-only network infrastructure—including transport devices such as switches and routers—must mitigate known vulnerabilities of the Internet Protocol (IP) network to protect the call-processing devices.

Deploying across a data-only network infrastructure makes devices such as call servers, desktop video teleconferences (VTCs), and UC/VVoIP endpoints more accessible to malicious cyber actors. Compromises of the call-processing network are performed using the same tools used to compromise data-only networks and related peripherals (e.g., PCs, smartphones, printers, switches, routers). In addition, malicious actors can connect to the UC/VVoIP call-processing infrastructure using the data network infrastructure. Separating the UC/VVoIP call-processing and data-only infrastructures makes penetrating the UC/VVoIP systems harder. Virtual local area networks (VLANs) allow multiple networks to use the same physical layer 2/3 medium (e.g., switches, routers), but remain logically separated.

Because UC/VVoIP endpoint calls in UC/VVoIP systems are carried over more accessible data networks than the traditional public switched telephone network (PSTN), eavesdropping is more of a risk. While it cannot eliminate the risk altogether, network security can help make eavesdropping more difficult.

In addition, the data-only network infrastructure must now meet the same reliability and quality of service (QoS) requirements as the UC/VVoIP call-processing network. To ensure a secure deployment of UC/VVoIP systems and devices across the data network in a way that also ensures high availability requires the implementation of redundancy, data backups, power backups, and physical protection of the network.

![Figure 1: Logical view of a UC/VVoIP system following NSA guidelines](https://statics.bsafes.com/images/publications/deploying-secure-unified-communications-voice-and-video-over-ip-systems-fig-1.png)
_Figure 1: Logical view of a UC/VVoIP system following NSA guidelines_

### *Accessibility and network separation*
Physical convergence of voice/video technology across a data network is an advantage of UC/VVoIP call-processing systems. However, placing UC/VVoIP systems and data systems on the same network means both technologies are now susceptible to the same techniques and accessible by the same malicious actors. Once an actor has penetrated the network, both data services and UC/VVoIP call processing will be available for exploit. This violates the basic defense-in-depth principle, because vulnerabilities in one part of the network should not make another part of the network vulnerable. The border between the voice/video network and the data network should be treated as untrusted and secured accordingly. They should not be freely accessible to each other. Access from the data network to the UC/VVoIP network should be denied unless explicitly allowed. The converse from the UC/VVoIP to the data network should also be enforced.

#### Mitigations
By using VLAN technology, lateral movement between the data network and the UC/VVoIP network can be limited, even though both networks share the same physical network. While VLANs were not designed as security mechanisms, they can be used to enable security features, such as placing access controls on the type of traffic that is allowed on specific VLANs. VLANs allow UC/VVoIP traffic to be isolated from data traffic and vice versa, while enabling any interactions between them to be tightly controlled. This limits the reconnaissance a malicious actor can perform from one network to the other and limits the protocols they can exploit.

Place all network devices not specifically used to support UC/VVoIP—such as PCs, file servers, and email servers—on data VLANs. UC/VVoIP devices should be placed on different VLANs according to their role in the network. Limiting each VLAN to groups of similar devices and protocols makes the development, implementation, and management of security features much easier. UC/VVoIP servers should be placed in different VLANs depending on the UC/VVoIP protocol they implement. As an example, all H.323 servers should be placed in an H.323-only VLAN, and all Session Initiation Protocol (SIP) servers should be placed in a SIP VLAN. If a single server implements multiple protocols, the network interface card (NIC) should support virtual VLANS so the server can participate in multiple VLANs. The UC/VVoIP network and the data network should have their own servers for standard network support services like the Domain Name System (DNS), Dynamic Host Configuration Protocol (DHCP), and Network Time Protocol (NTP). This is necessary because traffic from these services should not have to cross the boundary between UC/VVoIP and data VLANs.

Dividing the network into multiple VLANs does not provide any benefit if the traffic between the VLANs is not restricted. As traffic enters the network through the border router, the border router only performs stateless packet filtering on the traffic due to routing load. Starting at the session border controller (SBC), control traffic between UC/VVoIP VLANs with stateful packet filtering devices. Configure the access control lists (ACLs) on the stateful packet filtering devices to allow UC/VVoIP endpoints to connect only to the UC/VVoIP servers the endpoints need to function and vice versa. Filter based on IP address, port number, and transport protocol instead of on port number alone. Only allow protocols necessary for operation to be allowed by the filter. Everything else should be denied.

Use an application-layer firewall to separate the UC/VVoIP VLANs from the data VLANs. The application-layer firewall will function as a checkpoint for all traffic between the UC/VVoIP and data networks. No traffic should be allowed directly between the UC/VVoIP VLAN segmented network and the data VLAN segmented network without being examined at the application layer by either the firewall or a proxy device in the demilitarized zone (DMZ). Only necessary protocols should be allowed through the firewall.

Some devices, such as unified messaging servers, fulfill roles on both networks, and thus need access to both the data and UC/VVoIP VLANs. Place these devices in the DMZ managed by the application-layer firewall.

### *Call eavesdropping protections*
Unencrypted voice and video communication is susceptible to eavesdropping when conversations travel over an IP network. Commercial tools exist that allow media streams to be reconstructed if packets can be captured, even when using proprietary coder-decoders (codecs). Network-layer security protections may not be able to prevent call eavesdropping completely, but they can make it much more difficult.

#### Mitigations
The best mitigation against eavesdropping is encrypting all voice and video traffic endto-end. Additionally, limiting access to the traffic can be achieved by enabling port security on all switches. Port security restricts access to the network at the layer 2 level. If a rogue device physically tries to connect to a switch with port security enabled, the switch disables the port and does not grant the rogue device access to the network. Port security 802.1x device authentication should be enabled to force clients to authenticate before they are allowed onto the network.

### *Physical access protections*
With physical access to equipment, a malicious actor can disable the network, eavesdrop, and otherwise compromise the UC/VVoIP call-processing system. Most digital safeguards on the network are meaningless if an intruder gains physical access to the equipment being protected. With physical access to equipment, malicious actors can often use a simple USB device to install malware. Backdoors can be installed or entire databases containing sensitive information can be downloaded. For these reasons, it is imperative to put physical protections for the equipment in place.

#### Mitigations
Grant physical access to network hardware only to authorized personnel. Place network hardware in a locked, restricted, and controlled area. A log with timestamps of personnel accessing these areas should be kept, if possible. The hardware equipment should be kept in cabinets that can be locked. The cabinets should remained locked unless there is a need for authorized personnel to physically access the equipment. Video cameras should also be installed to provide video surveillance of the restricted areas if practicable.

### Network availability protections
Denial of service (DoS) impacts take many forms and are difficult to prevent. DoS effects can be triggered by software vulnerabilities to disable UC/VVoIP devices, consume resources on a UC/VVoIP server, or consume excessive amounts of network bandwidth. The first two types are addressed by using trusted software and staying current on patching. However, over-consumption of network bandwidth can often be addressed at the network level.

There are also environmental factors that can disable or degrade availability of the network. Power outages are an example of such a factor. These events must also be taken into account.

#### Mitigations
DoS techniques using network bandwidth can directly target UC/VVoIP devices. Limiting the rate of traffic to UC/VVoIP VLANs can reduce the effects of such DoS attempts coming from outside the UC/VVoIP call-processing network. When designing the UC/VVoIP call-processing network, determine the number of simultaneous incoming external calls that can be handled without detrimentally affecting the ability to place internal calls. Use network perimeter devices such as firewalls, SBCs, and filtering routers to limit the bandwidth allocated to incoming external calls. These perimeter devices typically have built-in features that detect and limit DoS attempts. This reduces the amount of network traffic allowed into UC/VVoIP call-processing VLANs.

UC/VVoIP protocols are time sensitive protocols and vulnerable to jitter, latency, and packet loss. UC/VVoIP traffic should not be delayed due to lower priority traffic. There are mechanisms available to score and prioritize traffic traversing the network. One of these is QoS. Quality of service should be enabled on network hardware that route UC/VVoIP call-processing traffic and given a higher priority than less time-sensitive traffic.

To guard against power outages, a backup power source should be installed. UC/VVoIP endpoints receive power over the network cable using Power over Ethernet (PoE) technology. To ensure telephone service in the event of a power outage, any network hardware device that provides PoE to any UC/VVoIP client should be attached to a backup power source.

### *Network services and protocols protections*
Many network-based services are required to maintain secure, enterprise-wide UC/VVoIP call-processing. This section covers three of them: DHCP, DNS, and NTP.

#### DHCP 
DHCP is most often used to assign network settings such as IP addresses, DNS name servers, and gateway routers to UC/VVoIP clients. DHCP is a good option for assigning IP addresses to UC/VVoIP endpoints and other peripheral IP devices. The other option is to statically assign IP addresses, but that comes with a higher administrative burden as each IP address must be manually assigned to each device. Implementation of DHCP requires careful consideration because DHCP is inherently vulnerable. It does not possess security features such as authentication and encryption, which are prevalent in modern protocols. A rogue DHCP server can connect to the network and provide network settings to a UC/VVoIP endpoint, which could result in a DoS effect or man-in-the-middle interception. In addition, a malicious DHCP client can also cause a DoS effect by continuously requesting IP addresses until the DHCP pool is exhausted. Without an IP address, phone service is unavailable.

##### *Mitigations*
Since UC/VVoIP deployments may contain hundreds or thousands of endpoint needing IP addresses, DHCP may be the only reasonable solution in assigning IP addresses. Manually assigning IP addresses does not scale well in larger environments. To guard against rogue DHCP servers on the network, DHCP snooping should be employed on local area network (LAN) switches. DHCP snooping is a layer 2 technology that drops DHCP messages from DHCP servers that are not authorized. DHCP snooping also keeps track of successful DHCP bindings and inspects DHCP traffic for malicious data.

To combat malicious DHCP clients connecting to the network, port security should be enabled on the LAN switches. If an unauthorized DHCP client is plugged into the switch, port security will disable the port and deny the unauthorized client access to the network. Port security 802.1x device authentication should also be enabled to force clients to authenticate before they are allowed onto the network.

The UC/VVoIP network should have a separate DHCP server from the data network. Only clients on the UC/VVoIP network should be allowed to request addresses from this DHCP server.

#### DNS
DNS is foundational to all data and UC/VVoIP networks for translating domain names into IP addresses where messages can be sent. In its inception, DNS was not designed with security in mind, so malicious issues such as DNS cache-poisoning, compromised DNS servers, and malicious DNS registrations have arisen. These have led to secure DNS-related proposals such as DNSSEC (DNS Security Extensions). Malicious DNS techniques could result in man-in-the-middle compromises or UC/VVoIP connections to malicious devices.

##### *Mitigations*
DNSSEC should be employed at your enterprise boundary, by enabling DNSSEC validation at the recursive resolvers. DNSSEC adds two important security features to DNS: authentication and integrity. DNSSEC assures that the data the DNS server receives from other DNS servers has not been modified and that the data was received from the authoritative zone the data originated from. If an error occurs in validating the DNS data, the data is dropped.

There are also techniques such as forward-confirmed-reverse-DNS that can make DNS more secure. This is a networking parameter configuration in which an IP address has both forward (name-to-address) and reverse (address-to-name) DNS entries that match each other.

In addition to DNSSEC and forward-confirmed-reverse-DNS, zone transfers should be disabled. With zone transfers enabled, a malicious actor could issue a DNS query that would initiate a zone transfer of the internal DNS database. A DNS zone transfer replicates DNS records across DNS servers, eliminating the need to manually update DNS servers. If a DNS server can be tricked into sending a DNS zone transfer to a malicious actor, the actor could use that information to easily map and target specific servers on the network. DNS zone transfers should only be allowed to servers that have a specific need for the information. All other zone transfer requests should be denied.

Lastly, use a dedicated DNS server to service UC/VVoIP clients. The DNS server should be separate from the DNS server that services the data network. The DNS server should be behind a firewall and access to the DNS server should be restricted by access control lists.

#### NTP
NTP is intended to synchronize all connecting IP devices on the UC/VVoIP callprocessing network. Special attention should be paid to securing these timing servers. Abuse of NTP could desynchronize devices causing a denial of service.

##### *Mitigations*
The NTP server providing time to the UC/VVoIP clients should be a dedicated NTP server separate from the data network’s NTP server. The UC/VVoIP server should use the latest available NTP version that supports authentication and integrity. Older versions of NTP have less robust security features.

To limit the attack surface of the UC/VVoIP NTP server, the server should be placed behind a firewall and access to the NTP server limited. Only clients on the UC/VVoIP VLAN should have the ability to request time from the UC/VVoIP NTP server. All other requests should be denied.

### *Trusted path and channel protections*
When sensitive data is passed from client endpoint to a UC/VVoIP call-processing server, that data must be protected from modification and disclosure. Data must be protected when administering UC/VVoIP servers and endpoints as well. This can be achieved through using protocols that provide encryption. In addition to modification and disclosure protections, IP devices should also use protocols that provide two-way authentication that is cryptographically secure. In the absence of encryption, a malicious actor could eavesdrop on a connection to steal credentials or sensitive information. In the absence of server authentication, a malicious actor could perform man-in-the-middle interception of a connection and masquerade as the server to compromise a client. In addition, in the absence of client authentication and encryption, a malicious actor could perform a man-in-the-middle on a client endpoint and masquerade as an authorized client endpoint.

#### Mitigations
Standard protocols can be used to provide encryption and two-way authentication to secure sensitive data: Internet Protocol Security (IPsec), Secure Shell (SSH), Transport Layer Security (TLS), Datagram TLS (DTLS), and Hypertext Transport Protocol Secure (HTTPS) are such protocols. The NSA-approved Commercial National Security Algorithm (CNSA) Suite provides cryptographic requirements for these protocols to be used securely and are listed in Committee on National Security Systems Policy No. 15 (https://cnss.gov/CNSS/issuances/Policies.cfm).

### *Summary of Part I*
When securely deploying UC/VVoIP systems, the network is the first critical place to enact security. Leverage security features included in network equipment to enforce access control and data/voice separation and to implement traffic prioritization, encryption, and authentication services. By configuring the network to adhere to the recommendations in this guide, the network can provide essential security services to protect data traversing the network as well as the devices connecting to it.

Once an administrator has implemented these network security recommendations, the next step is to move on to security at the perimeter.

***

#### Table of Contents
{: .no_toc}

<ul><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-1/">Executive summary</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-2/">Part I - Network security best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-3/">Part II - Perimeter security best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-4/">Part III - Enterprise session controller security best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-5/">Part IV - UC/VVoIP endpoint best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-6/">End of guidelines</a></li></ul>

***

</div>
