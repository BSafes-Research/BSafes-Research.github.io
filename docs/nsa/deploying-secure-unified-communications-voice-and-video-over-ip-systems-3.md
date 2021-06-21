---
layout: default
title: Part II - Perimeter security best practices and mitigations 
parent: . June 2021, Deploying Secure Unified Communications/Voice and Video over IP Systems  
grand_parent: NSA 
nav_order: 30 
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

## Part II: Perimeter security best practices and mitigations
While the first part of this report addressed UC/VVoIP security on the network, Part II addresses security at the perimeter. 

The perimeter is where all communications external to the organization’s UC/VVoIP system enter or leave the call-processing network. Session border controllers are essential and enforce call signaling protocol standards for traffic entering and exiting the local UC/VVoIP network. By enforcing call signaling protocol standards, a layer of protection is provided to the servers residing on the internal network that process UC/VVoIP communication packets. In addition, SBCs support secure connectivity from local UC/VVoIP servers to remote service providers and other external UC/VVoIP systems. Implementation of perimeter security should be done after implementing best practices for the network, as described in Part I.

The perimeter, in this case, refers to the external method of communication for the UC/VVoIP call-processing system only. This includes PSTN gateways, SBCs, and virtual private networks (VPNs). All devices that form the perimeter should be securely managed from a dedicated management network.

### *PSTN gateway protections*
PSTN gateways connect a UC/VVoIP call-processing system to the PSTN. The threat presented by gateway devices is that malicious users from outside of the network could connect directly to the gateway device and make unauthorized calls. Unauthorized calls could lead to toll fraud. Another problem with some PSTN gateways is that they can directly pass call-signaling messages to internal enterprise session controllers (ESCs). This could allow a direct compromise of the UC/VVoIP servers.

#### Mitigations
The best way to prevent unauthorized calls is to require authorized users or peer gateways to authenticate before the gateway will complete a call. Some gateways query a separate server to check if a call is authorized. In this case, a secure channel must be used between the gateway and the authorization server.

Place PSTN gateways on their own VLAN and in a DMZ off of a session border controller interface. Use packet filtering to allow signaling messages from authorized servers only. Prevent UC/VVoIP endpoints from sending signaling messages directly to the gateway. Instead, use the UC/VVoIP server as an intermediary.

Gateways must validate and terminate all PSTN signaling at the gateway. The gateway should convert PSTN signaling messages to UC/VVoIP signaling messages. This reduces the likelihood of a successful compromise of the UC/VVoIP servers through the gateway. A malicious actor could still directly compromise the gateway and use it as a platform for lateral movement to other UC/VVoIP devices, but this requires additional steps.

Regularly apply security updates to the software on gateways located at the perimeter.

![Figure 2: Perimeter security device placement following NSA guidelines](https://statics.bsafes.com/images/publications/deploying-secure-unified-communications-voice-and-video-over-ip-systems-fig-2.png)
_Figure 2: Perimeter security device placement following NSA guidelines_

### *Protections for public IP networks functioning as voice carriers*
A benefit of UC/VVoIP is the ability to use public IP networks to carry voice traffic between physically separate offices or between organizations. However, this use of UC/VVoIP requires special security considerations because the organization has little control over its voice/video traffic once it enters other networks.

Once on the public network, an organization’s UC/VVoIP call-processing traffic will traverse computers and networks owned by any number of third parties who could intercept and modify packets without the caller’s or organization’s knowledge. An organization’s internal network policy may allow call-processing traffic to be sent in the clear; however, the accessibility of voice/video traffic on a public network necessitates the use of encryption and authentication to establish a secure channel between the calling and answering parties.

#### Mitigations
Using UC/VVoIP over a public network to establish calls between different organizations requires specific security steps. For confidentiality reasons, UC/VVoIP should use encrypted trunks when communicating over public IP networks. An organization should not trust the traffic originating from another organization. Decrypt and inspect any UC/VVoIP traffic before it is allowed into the internal network. Additionally, an organization should hide its internal network topology by using network address translation (NAT) and non-routable IP addresses on its internal UC/VVoIP network.

An SBC deployed at the network perimeter can provide inspection of the UC/VVoIP traffic as well as provide for NAT traversal. An SBC sits on the edge of the network and proxies the UC/VVoIP connection between the network and the service provider. The SBC rewrites signaling messages (control signals) and dynamically opens ports so media streams can traverse the SBC. SBCs are back-to-back user agents (B2BUAs). B2BUAs proxy connections between endpoints resulting in two separate connections for the communication channel. SBCs understand and inspect UC/VVoIP communication at a level that traditional network firewalls cannot. Because they are B2BUAs, SBCs maintain a separate connection between the internal network and the service provider. This property allows the SBC to inspect and manipulate (i.e., rewrite) portions of the UC/VVoIP packets traversing it. If the streams traversing the SBC are unencrypted, the SBC can rewrite the internal IP addresses buried within the UC/VVoIP packets with external IP addresses, allowing for NAT. The use of non-routable addresses prohibits a malicious actor from directly routing a packet across the Internet to a device on the internal network.

Inter-office communication can be established using encrypted VPNs. A VPN is likely already established between offices for data-only traffic. However, since it is recommended that UC/VVoIP call-processing and data networks should be kept on separate VLANs, a separate VPN must be established for call-processing traffic or the VPN must respect and maintain VLAN separation.

### *Signaling gateway protections*
A signaling gateway is a translation device that is used to pass signaling (i.e., call control) information between two different network protocols or across a public IP network. In the case of UC/VVoIP, this is between an IP-based call-processing system and an external legacy telephony network (i.e., central office SS7, T1, etc.). A compromise of a signaling gateway can lead to a disruption of voice and video services, access to the topological information of the network, identifying the subscribers, or other effects. The gateway device can be stand-alone or integrated with another signaling gateway.

#### Mitigations
Signaling gateways are public facing servers. As with all public facing servers, the signaling gateway should be placed in a demilitarized zone (DMZ). The DMZ in this case should be an interface off of the SBC. In addition to being placed in a DMZ, the signaling gateway should be placed in its own VLAN. UC/VVoIP devices should not be able to send call control signaling messages directly to the gateway, and instead should use the UC/VVoIP server as an intermediary or protocol translation device. The gateway will send the signaling messages to the ESC server, which acts as an intermediary between the two UC/VVoIP endpoint devices. Signaling gateways must validate and terminate all PSTN signaling, then convert the terminated signaling messages to UC/VVoIP call control signaling messages for communications to UC/VVoIP-based devices. This type of protocol translation enacted by the signaling gateway helps reduce the likelihood of a successful compromise of the ESC server. For all signaling protocols that can be encrypted, encryption should be utilized.

The signaling gateway should be configured to log all calls. Because the signaling gateway is located at the perimeter, it is capable of keeping records of calls entering and exiting the network. Keeping call records that include call connection time, length of call, and other data often proves useful when trying to identify origin and identification of a malicious actor.

### *Media gateway protections*
A media gateway is a translation device that converts media streams (voice, video) between different communications formats and protocols. For example, a media gateway device can convert voice media originating from a time-division multiplexingbased (TDM) system to voice media destined for a UC/VVoIP system. The media gateway device can be stand-alone or integrated with another device (i.e., signaling gateway). Also note that a signaling gateway can initiate and terminate communications on the media gateway. A successful compromise of the media gateway can lead to the eavesdropping or disruption of all voice and video calls traversing the gateway.

#### Mitigations
Place media gateways in their own media VLAN and in a DMZ off of an SBC interface. When calls are routed over public networks, encryption of media protocols is essential in the same way as with signaling protocols. Use a VPN for any inter-office communications across the public network.

### *Wide area network (WAN) link protections*
Network connections to remote offices are considered part of the internal network and thus should follow the same data and UC/VVoIP call-processing separation guidelines. In this context, remote office WAN links refer to dedicated leased lines connecting the remote and primary networks where both ends of the link are managed by the same organization. Because the WAN link connects the internal network to the outside world, if it is not protected properly, it puts the internal network at risk.

#### Mitigations
WAN protection methods include VPN protocols such as IPsec and TLS. The VPN must support the separation of UC/VVoIP call-processing networks and data networks by either supporting VLANs or creating individual VPNs for each network.

### *Cloud connectivity protections*
Some organizations are currently migrating the Internet Protocol private branch exchange (PBX) to the cloud to accrue benefits the cloud offers (increased efficiency, greater flexibility, reduced infrastructure costs, lower operational costs, and improved communications). Cloud-based communications systems can include IP PBXs, SIP servers, UC/VVoIP teleconferencing, and other applications.

With the rise of cloud computing, security remains a top concern. Just as security concerns expanded when PBXs migrated to IP PBXs and then evolved to UC/VVoIP systems, security is just as relevant now, as UC/VVoIP systems begin the migration to the cloud. Threats to the cloud include denial of service effects, access misconfigurations, and unsecured application programmable interfaces used by programmers. When migrating to a cloud-based solution, data security must be maintained. Confidentiality of the call signaling must be maintained, the media channel (voice, video, and data) must prevent eavesdropping, and all devices involved must be properly authenticated.

#### Mitigations
To help mitigate risks around migrations to the cloud, employ cryptographic protocols to encrypt communications between UC/VVoIP devices. Whether moving a call server entirely into the cloud, or just providing trunk connectivity from an external call server to the cloud, it is best to protect call server peripherals with encryption and authentication. The encryption should be configured on UC/VVoIP signaling and media devices. To protect call control signaling originating from local UC/VVoIP systems out to the cloud, use SIP over TLS or H.235 (H.323 over TLS). To protect voice/video media originating from local UC/VVoIP systems out to the cloud, use Secure Real-Time Protocol (SRTP). Secure connections to the cloud must be established by implementing trusted paths and channels that support encryption and two-way authentication such as IPsec, TLS, DTLS, HTTPS, and SSH.

DMZ-like separation between logical external gateways and logical internal capabilities should be maintained. Access control mechanisms should be employed to restrict access to the systems hosted in the cloud. Robust logging should be enabled and those logs routinely reviewed to detect and trace any potential compromises.

### *Summary of Part II*
Perimeter security is paramount when deploying UC/VVoIP systems. Protection from external intrusions can be mitigated by employing the security features of devices located at the perimeter, as well as deploying special purpose UC/VVoIP security devices such as an SBC. Access control, data/voice separation, encryption, authentication, logging, and secure management are all considerations. By implementing these core security components in accordance with this document, the security at the perimeter will be greatly enhanced.

Once security at the network and perimeter is addressed, one can turn attention to ESCs.

***

#### Table of Contents
{: .no_toc}

<ul><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-1/">Executive summary</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-2/">Part I - Network security best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-3/">Part II - Perimeter security best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-4/">Part III - Enterprise session controller security best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-5/">Part IV - UC/VVoIP endpoint best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-6/">End of guidelines</a></li></ul>

***

</div>
