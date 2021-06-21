---
layout: default
title: Part IV - UC/VVoIP endpoint best practices and mitigations  
parent: . June 2021, Deploying Secure Unified Communications/Voice and Video over IP Systems  
grand_parent: NSA 
nav_order: 50 
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
## Part IV: UC/VVoIP endpoint best practices and mitigations
This fourth and final part to* Deploying Secure Unified Communications/Voice and Video over IP Systems* deals with securing UC/VVoIP endpoints. With voice/video/data and call-processing network infrastructures already securely in place, UC/VVoIP phones, desktop VTCs, and other UC/VVoIP endpoint devices can be added to the network and secured. Before adding UC/VVoIP endpoints to the call-processing network, administrators have key decisions to make so the endpoints and network are both secured against malicious actors:

- What elements of the hardware and software need to be locked down?
- Do administrators need to be able to remotely administer the UC/VVoIP endpoints? 
- What convergence features are needed? 
- Do the UC/VVoIP endpoints connect to the network over Ethernet or Wireless?
- Do UC/VVoIP endpoints running on general purpose operating systems need to be supported?

### *Software and hardware security*
Traditional phones contain limited functionality in the actual phone hardware because telephony features are implemented in the central office switch (CO) or PBX. However, UC/VVoIP endpoints are more autonomous because many do not require a CO or PBX in order to take advantage of much of their functionality. This requires a more capable and complex endpoint. The additional functionality and complexity in UC/VVoIP endpoint software increases the chance of vulnerabilities. These vulnerabilities should be mitigated similarly to general-purpose computers on the network. In addition, like computers, some UC/VVoIP endpoints allow users to install third-party software. These applications could also add vulnerabilities if not properly controlled and managed.

#### Software vulnerabilities
UC/VVoIP endpoints run on embedded operating systems or as a software application (softphone) on a general-purpose machine. When running on a general-purpose machine, in addition to the UC/VVoIP software and OS potentially having vulnerabilities, other applications, such as web browsers, that are installed could contain vulnerabilities as well. These vulnerabilities could allow denial of service impacts against the endpoint, modify remote management functionality, or allow a malicious actor to gain complete control of the endpoint and surreptitiously collect room audio.

##### *Mitigations*
Methods to mitigate the software vulnerabilities in UC/VVoIP endpoints are similar to methods used to protect other computer systems on the network. Disable unnecessary applications and services, particularly if they utilize remote connections or provide remote access. Any known vulnerabilities must be patched as soon as possible. This can be automated by having UC/VVoIP endpoints regularly and automatically download signed firmware files from a trusted central server. Finally, network access to the UC/VVoIP endpoints can be limited by placing them on separate UC/VVoIP-only VLANs. VLANs are covered in the first module of the *Deploying Secure Unified Communications/Voice and Video over IP Systems* document that covered securing the UC/VVoIP network. These steps make it more difficult for a malicious actor to exploit vulnerabilities on a UC/VVoIP endpoint or an application-laden video teleconferencing device.

#### Third-party software
Some UC/VVoIP endpoints have the capability to run third-party software downloaded from the network. For example, one Java-based endpoint allows the user to download Java applets from the vendor’s Internet site. There are risks to allowing such behavior: 

- Downloaded software that appears legitimate may contain malicious functionality. 
- The software may contain unknown vulnerabilities, which could be exploited to compromise the endpoint.

##### *Mitigations*
Enforce a policy for downloading external software onto UC/VVoIP endpoints that is at least as strict as that for downloading software to desktop computers. In many cases, the need for higher reliability for the UC/VVoIP system will necessitate stricter policies. Where possible, disable the capability to download external software and only distribute necessary software with firmware upgrades via a controlled mechanism. If there is a need to allow users to load applications on the UC/VVoIP endpoint, then set up a separate server inside the organization to provide only cryptographically signed applications. Block access to vendor web sites offering application downloads for the UC/VVoIP endpoint. Block direct Internet access by the UC/VVoIP endpoints, if possible. If that is not possible, use a DMZ proxy server for Internet web access. If users must connect back remotely with an UC/VVoIP endpoint, ensure the UC/VVoIP endpoint connects back to the enterprise using a cryptographic VPN (e.g., using IPsec).

#### Malicious software
Malicious software could exploit or introduce software vulnerabilities in the UC/VVoIP endpoint. Malicious software manifests in an organization’s telephone network similarly to how it manifests on data-only networks. Malicious software can install backdoors into desktop VTC and UC/VVoIP endpoints, gather sensitive information, or use UC/VVoIP endpoints to compromise other call-processing systems. The spread of worms on UC/VVoIP call-processing networks could disrupt or disable voice/video capability.

##### *Mitigations*
Antivirus solutions exist for some embedded platforms, but not all because the UC/VVoIP industry is still catching up with technology to protect UC/VVoIP endpoint devices. Antivirus software does not completely mitigate malicious software because signature based virus scanners only detect known malware variants. Use cryptographically signed updates along with the antivirus software to minimize malware.

#### Embedded microphones
All UC/VVoIP endpoints contain at least a single microphone in the handset, and usually there is a speakerphone that contains an additional microphone. This includes desktop VTCs and softphones on laptops and PCs, as they too have microphones and speakerphones. The UC/VVoIP endpoints are software-controlled devices, with the microphones controlled by software. A software vulnerability could enable a malicious actor to control the UC/VVoIP endpoint and thus the microphones without the user’s knowledge.

##### *Mitigations*
If a UC/VVoIP is placed in a sensitive area, its speakerphone microphone should be physically removed or at least disabled on the device. The original handsets should be replaced with push-to-talk handsets or headsets. This prevents the microphone from being activated except when a person is using the UC/VVoIP. Another possible mitigation is to use UC/VVoIP endpoints that have handsets and physically disconnect the microphone when the handset is on the hook.

### *Remote management of UC/VVoIP endpoints*
The majority of UC/VVoIP endpoints can be classified as network-controlled devices. There are many UC/VVoIP endpoint types. The various UC/VVoIP endpoint types include handset voice-only VoIP phones, handset voice/video VVoIP phones, softphones with headsets for laptops and PCs, floor model telepresence (voice/video), room size telepresence (voice/video), desktop VTCs, and desktop USB phones. The sheer number of UC/VVoIP endpoints that an organization must deploy means that the UC/VVoIP endpoints are made to be easily configured and managed using remote tools over the network. This capability means that each UC/VVoIP endpoint represents another potential point of network infection and each must be secured. An exploit of this remote management functionality could have serious consequences including denial of unified communications and call-processing services to an organization, and leakage of information to unauthorized parties inside and outside the organization. The common methods for remotely managing UC/VVoIP endpoints are DHCP, firmware and configuration file downloads from a call server, web-based management consoles, network management such as SNMP, or administrative login tools. All of these methods must be addressed during the design of an UC/VVoIP network.

#### Downloading firmware and configuration files
Many UC/VVoIP endpoints are similar to network-booted desktop computers. They connect to the network, obtain an IP address using DHCP, and download operating system images and configuration files from a central server. This keeps the management of software and configuration versions centralized. It also allows for easy updates of the UC/VVoIP endpoint's firmware. However, for a malicious actor, it opens a pathway to completely control an organization’s UC/VVoIP endpoints and other voice/video endpoint devices. By modifying the firmware or configuration file, a malicious actor can insert malicious code into the UC/VVoIP endpoint’s operating system, use the endpoint device as a rogue agent, redirect calls to malicious servers, or disable the UC/VVoIP endpoint.

A UC/VVoIP endpoint’s firmware or configuration file could be modified in one of two ways. A malicious actor could perform a man-in-the-middle technique to intercept and replace the files as they are downloaded from the call server. This requires local network access or the ability to spoof DHCP messages. Or, a malicious actor could compromise the ESC storing the firmware and configuration files. This is a more serious problem because control of an ESC enables a malicious actor to easily compromise all UC/VVoIP endpoints in an organization.

##### *Mitigations*
Choose UC/VVoIP endpoints that will process cryptographically signed firmware and configuration files. Each UC/VVoIP endpoint must have the signature verification key loaded on the UC/VVoIP endpoint in a secure manner such as on an isolated network or over a direct serial connection. Save the signing key in a secure place and do not store it on the download server. The UC/VVoIP endpoint must verify the signature on every file and reject any files with invalid signatures.

#### Web-based management interface
Most hardware UC/VVoIP endpoints have embedded web servers, which allow the modification of important settings on the endpoint device. Many times the same settings downloaded in configuration files are modifiable in this manner. Having web servers running on UC/VVoIP endpoints raise concerns as each UC/VVoIP endpoint now contains a web server that may be vulnerable.

##### *Mitigations* 
The users should access necessary UC/VVoIP endpoint features through the phone’s display, and administrators should configure UC/VVoIP endpoint settings using downloaded configuration files from a server. Deactivate the web interface. If there is a setting that needs to be set through the web server in the UC/VVoIP endpoint, the administrator should enable the web server through a secure signed download. Change the setting with web server, and disable the web server with another secure signed download.

#### Simple Network Management Protocol (SNMP)
SNMP is used to read and write settings on many network devices, allowing them to be integrated into comprehensive network management tools. Some UC/VVoIP endpoints may offer SNMP access to their settings. Compromising SNMP access to UC/VVoIP endpoints has consequences similar to compromising of configuration files or web interfaces.

##### *Mitigations*
Do not use SNMP to manage UC/VVoIP endpoints. Turn off all SNMP versions on the UC/VVoIP endpoint. If SNMP must be used to manage UC/VVoIP endpoints, then use “SNMP version-3 over TLS or DTLS” (SNMPv3, RFC 5953) with its authentication features. Previous versions of SNMP do not offer the same protections. SNMPv3/TLSv1.3 (RFC 5953) allows per-user passwords and uses cryptographic functions to protect the password and message integrity. If SNMPv3/TLSv1.3 is not available, then use signed configuration files that can be downloaded from the call server rather than using SNMPv1 (or v2) to manage the UC/VVoIP endpoints.

#### Telnet
Telnet is another remote management solution available on many UC/VVoIP endpoints. And like DHCP, HTTP, NTP, SNMP, and many earlier protocols, Telnet was not designed with security in mind. Telnet is a command line interface to the UC/VVoIP endpoint configuration. It is an antiquated and unsecured protocol: sensitive information, such as passwords, is transmitted in the clear over the network. Without any analysis tools, a novice actor can view an administrator’s Telnet login password and then use the information to create havoc on the system.

##### *Mitigations*
Disable Telnet. Use other methods of remote management like SSH. Relative to Telnet, SSHv2 is a better option that provides a secure channel for remote management because of its encrypted communications.

### *Network connectivity*
UC/VVoIP endpoints include a variety of network connectivity solutions such as Ethernet, Infrared Data Association (IrDA), Bluetooth®, Console, and Wi-Fi access. Some UC/VVoIP endpoints offer all of these connectivity solutions, acting as a universal wireless access point. While some sort of network connectivity is required, too many connectivity options will make an UC/VVoIP endpoint more difficult to secure. Each connectivity solution adds configuration complexity and offers another potential path for a malicious actor to exploit.

#### Ethernet
Ethernet is a common means of connecting a wired UC/VVoIP endpoint to the UC/VVoIP network. To make deploying UC/VVoIP endpoints easier and to avoid adding additional Ethernet cabling, many UC/VVoIP endpoints feature an integrated Ethernet switch in the UC/VVoIP endpoint to provide another device connection. As an example, a PC can be plugged into the UC/VVoIP endpoint, and the UC/VVoIP endpoint can be connected to the network. This effectively causes the UC/VVoIP endpoint to function like a bridge between the PC and Ethernet switch. The bridge on the UC/VVoIP endpoint will enable both the PC and UC/VVoIP endpoint to use the same network access switch port. Because the UC/VVoIP endpoint and computer will be privy to network traffic meant for each other, a malicious actor who compromises the PC may have direct access to the UC/VVoIP endpoint and vice versa.

Best practices require UC/VVoIP call-processing require voice/video call-processing and data-only networks be kept separate using VLANs. If the UC/VVoIP endpoint does not support VLANs on an integrated Ethernet switch, then a computer connected to the UC/VVoIP endpoint’s PC port has access to the UC/VVoIP call-processing VLAN.

##### *Mitigations*
Do not use the PC port on the UC/VVoIP endpoint and disable it in the UC/VVoIP endpoint’s configuration. This prevents a device from connecting to the UC/VVoIP endpoint and prevents a device from violating VLAN separation. If the environment mandates the PC port be used, then the UC/VVoIP endpoint’s integrated Ethernet switch must support VLANs and be configured.

#### Infrared
Infrared data ports utilizing the IrDA protocol (an infrared protocol for wireless infrared line-of-sight communications for the last meter between devices) are used to transmit data between devices using invisible pulses of light. Example uses of infrared ports include synchronization of data between handheld devices and PCs and printing from handheld devices directly to a printer. Devices that communicate using infrared must be within sight of each other. While some UC/VVoIP endpoints presently have infrared ports, no UC/VVoIP endpoint is known to make use of this port, but its existence suggests that features using the infrared port will be available in the future. For example, a person could synchronize his mobile phone address book with the address book on the UC/VVoIP endpoint.

Infrared ports on UC/VVoIP endpoints raise several security concerns. First, there is no built-in security mechanism other than range of transmission and the line-of-sight requirement. Each application must implement its own confidentiality, authentication, and integrity mechanisms. Second, a malicious actor does not need to physically interact with the UC/VVoIP endpoint to access it. An actor with line-of-sight could potentially compromise the UC/VVoIP endpoint. Third, a compromised UC/VVoIP endpoint could use the infrared port to capture other infrared communications in the same room as itself.

##### *Mitigations* 
Cover the infrared port with metallic tape. This prevents any use of the port, including by a malicious actor who has compromised a UC/VVoIP endpoint. If use of the infrared port is necessary, then individually evaluate and configure each allowed application for security.

#### Wireless personal area network (WPAN)
Bluetooth is a short-range WPAN protocol that connects personal area network devices centered on an individual person’s workspace. The primary differences between Bluetooth and infrared are that Bluetooth does not require line-of-sight for successful data transmission and Bluetooth features some security mechanisms that provide confidentiality and integrity. The designers of UC/VVoIP call-processing devices must be aware of the many security issues associated with WPAN technologies and implement mitigations for them.

##### *Mitigations* 
The best solution is to use devices that do not support Bluetooth. If Bluetooth-enabled UC/VVoIP endpoints are used, then proper security measures must be taken. Disable Bluetooth functionality on UC/VVoIP endpoints and desktop VTCs. Addressing all the security issues related to Bluetooth is outside the scope of this document. NIST’s Special Publication 800-121, Guide to Bluetooth Security (https://csrc.nist.gov/publications/detail/sp/800-121/rev-2/final) discusses the details of Bluetooth security.

#### Wireless local area network (WLAN)
WLANs are increasingly common in organizations. This category of connectivity includes technologies referred to as Wi-Fi or IEEE 802.11. Some UC/VVoIP endpoints can use WLANs as the primary source of connectivity instead of a wired (Ethernet) link.

UC/VVoIP endpoints that use WLANs to connect to the network must mitigate both WLAN and UC/VVoIP call-processing vulnerabilities. They must address problems such as confidentiality, integrity, and reliability of the wireless link in addition to the UC/VVoIP call-processing vulnerabilities discussed elsewhere in this guide. This makes deploying WLAN UC/VVoIP endpoints more complex.

##### *Mitigations*
WLAN UC/VVoIP endpoints must meet the same security policy as other WLAN devices deployed by an organization. In addition, the WLAN UC/VVoIP endpoint and the WLAN network must meet the requirements placed on the overall wired UC/VVoIP callprocessing infrastructure such as separation of data and voice/video call-processing traffic by using VLANs, different WLAN Service Set Identifiers (SSIDs) or entirely separate WLAN infrastructure.

#### Network connectivity mitigation summary
Of the various network connectivity solutions for UC/VVoIP endpoints, only connecting via Ethernet is recommended. If voice/video call-processing and data networks are separated onto different VLANs, the computer port on UC/VVoIP endpoints should not be used unless the UC/VVoIP endpoint supports VLANs. 

The wireless network technologies discussed in this section could present significant vulnerabilities in the voice/video call-processing network. If the organization needs wireless access, it should be implemented using a separate and dedicated wireless infrastructure, and not integrated with the UC/VVoIP call-processing solution.

### *Convergence features* 
Convergence features allow the communication and synchronization of data between many different types of devices. UC/VVoIP endpoints and desktop VTCs may include features that allow them to interact with applications on other IP devices. For instance, an address book application on the PC instructs the UC/VVoIP endpoint to dial a number when the user clicks on an entry in the address book, or a mobile device synchronizes its address book with the address book on the UC/VVoIP endpoint. Each of these features requires another available service on the UC/VVoIP endpoint that could contain vulnerabilities. Each application requires an authentication and authorization mechanism to protect data stored on the UC/VVoIP endpoint and other convergence devices. The data must also be protected while it is in transit between IP devices. Since no standards exist, each application will likely have its own mechanisms for implementing integrity and confidentiality. This makes consistently managing and protecting the use of these applications difficult.

A more serious problem is that synchronization with mobile devices could result in the transfer of malicious code, such as viruses, from these devices to the UC/VVoIP callprocessing network. Many UC/VVoIP endpoints are embedded systems that run software similar to that used on handheld devices and cell phones. If these devices are infected with malicious code, that code could be transferred to the UC/VVoIP endpoint. 

Voicemail services are another area where the UC/VVoIP call-processing network interacts with the data network. Voicemail systems may make voice messages available to users in email messages. Similarly, users may be able to send email that can be accessed from the UC/VVoIP endpoint.

#### Mitigations
UC/VVoIP convergence opens the voice/video call-processing network to many of the same vulnerabilities that afflict the data-only network and also allow the UC/VVoIP network to afflict the data-only network as well. The safest mitigation is to block traffic between voice/video call-processing and data-only networks. However, the advantages of convergence may outweigh the risk. In that case, enforce strong authentication for any such service and put authorization controls in place to prevent malicious actors from abusing convergence solutions.

Authorized users can still inadvertently spread malicious code. In this case, the points where data moves between networks should be tightly controlled. Data transfer should not occur directly between the UC/VVoIP endpoint and other devices. Instead, a firewall or SBC should be set up to act as a gateway between the voice/video call-processing and data networks. At minimum, use a stateful layer 3 and 4 SBC. More appropriate is a stateful layer 3-7 SBC and an application-layer firewall that can check all data for malicious code. Place any services that must be used on both networks in a DMZ between the networks. For example, consider synchronizing a mobile device and UC/VVoIP endpoint with the same address book. The mobile device should not synchronize directly with the UC/VVoIP endpoint. Instead, employ a messaging server in the DMZ between the voice/video call-processing and data networks. The UC/VVoIP endpoint, mobile device, and desktop PC would all access the address book from the messaging server. The messaging server could then act as a gateway between devices, providing authentication and authorization services and scanning data for malicious code.

### *Softphones*
A softphone is UC/VVoIP endpoint software that runs on a general-purpose device. The use of these phones poses several challenges when the voice/video call-processing and data networks are logically separated using VLANs. The softphones must operate on a computer that is connected to both the data and telephony networks. The PC violates the separation between the telephony and data networks because it must directly access both networks. Thus, compromise of the PC would allow access to both networks.

Replacing desktop UC/VVoIP endpoints with softphones also creates a single point of failure for communications. A widespread problem that affects many PCs or the network infrastructure will disable all communications. Users will not even have a means to report the failure. A fast spreading worm or power outage could create such a situation. 

Softphones make management of the UC/VVoIP endpoint network more difficult because the UC/VVoIP call-processing server will not be able to reliably determine the type of device connecting to it. Untrusted softphones can be loaded on PCs by end users. Since the UC/VVoIP call-processing server does not know about these softphones, it will not be able to ensure they are configured securely.

#### Mitigations
If softphones are in use, create another VLAN and place all PCs with softphones on it. Configure traffic filtering rules to allow UC/VVoIP traffic between this VLAN and the UC/VVoIP call-processing VLANs, but do not allow UC/VVoIP traffic on the data VLAN. Similarly, do not allow general data traffic to flow to the UC/VVoIP call-processing server or on UC/VVoIP endpoint call-processing VLANs.

If softphones are densely deployed throughout the network, it is not practical to have separate data softphone VLANs. Instead, place all PCs—whether or not they have softphones installed—in data VLANs and filter traffic as described for the softphone VLAN in the previous paragraph. 

When softphones are used as the primary voice communication mechanism, provide a backup communication method, which does not depend on the UC/VVoIP network, and make it available in every office to ensure some form of reliable communication.

### *Summary of Part IV*
UC/VVoIP can be deployed securely in its environment following secure guidelines. An administrator can secure a UC/VVoIP endpoint by locking down the software and hardware. Update and patch the software as it becomes available using signed files from a trusted server. Limit network access of the UC/VVoIP endpoint. For UC/VVoIP endpoints that have handsets and used in areas where sensitive conversations occur, use an endpoint that physically disconnects the microphone when on hook, remove the speakerphone microphone, or replace the handset with a push–to-talk handset. Disable any unnecessary applications on the UC/VVoIP endpoint. Remote management should use secure paths, secure protocols, authentication between devices, and strong cryptographic functions. For network connectivity use wired Ethernet, and disable Wi-Fi, infrared, and other non-wired protocols. Place the UC/VVoIP endpoints in their own VLAN separating voice/video traffic from all other traffic. Computers and handheld devices may use softphones, but with the same precautions as in hardware UC/VVoIP endpoints. Using security guidelines with smart configurations and management controls increases the UC/VVoIP endpoint security.

***

#### Table of Contents
{: .no_toc}

<ul><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-1/">Executive summary</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-2/">Part I - Network security best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-3/">Part II - Perimeter security best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-4/">Part III - Enterprise session controller security best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-5/">Part IV - UC/VVoIP endpoint best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-6/">End of guidelines</a></li></ul>

***

</div>
