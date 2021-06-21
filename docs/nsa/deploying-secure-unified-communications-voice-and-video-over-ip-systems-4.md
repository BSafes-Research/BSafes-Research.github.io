---
layout: default
title: Part III - Enterprise session controller security best practices and mitigations 
parent: . June 2021, Deploying Secure Unified Communications/Voice and Video over IP Systems  
grand_parent: NSA 
nav_order: 40 
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

## Part III: Enterprise session controller security best practices and mitigations
Parts I and II of *Deploying Secure Unified Communications/Voice and Video over IP Systems* lay out best practices for preparing the network infrastructure and perimeter in preparation for deployment of UC/VVoIP systems. Part III addresses the third step of securing UC/VVoIP systems by readying enterprise session controllers, also known as UC/VVoIP ESCs. A UC/VVoIP ESC is also commonly called an Advanced IP PBX, SIP server, SIP proxy, H.323 Gatekeeper, a call-processing server, or simply just an ESC.

These servers are analogous to the central switches in a legacy PBX system and are just as essential. They are necessary for establishing calls and using many features such as call forwarding, voice mail, and conference calling. Unlike a PBX, an ESC can securely manage all UC/VVoIP endpoint devices registered to it. They process calls between IP endpoints and/or trunk the calls to another ESC.

Several aspects of ESCs require security considerations to protect the UC/VVoIP callprocessing system from compromise and misuse. The software installed on the ESCs— such as operating systems, databases, and call-processing applications—must be hardened by removing unnecessary applications, services, and default accounts. Most ESCs use remote management capabilities that make the server more vulnerable if not configured with appropriate security mechanisms. The ESCs must meet the stringent reliability and availability requirements of traditional (legacy) telephony systems.

ESCs also perform the critical function of authenticating and authorizing IP-phones and their users. In addition to discussing how to protect ESCs themselves, this section addresses what authentication and authorization features on the ESC should be used to control access to the UC/VVoIP call-processing network.

### *Software and application protections*
ESCs usually execute on general-purpose server hardware. Administrators of call processing systems must pay special attention when managing user accounts, examining default configuration settings for security weaknesses, ensuring auditing and logging are enabled, and configuring any specialized services or features. This section will address these problems as they pertain to ESC software.

#### User accounts and passwords
User accounts grant access to the server with various rights and privileges. The more users with access to the server, the more opportunity for it to be intentionally or unintentionally compromised. Limiting access to the server helps prevent this. Many systems include a number of built-in default user accounts with default passwords, which are public knowledge or can be easily guessed. These accounts provide easy entry for malicious actors and are often overlooked during the installation process. The lack of a password or a bad password choice can allow easy access into the device and therefore into the network.

##### *Mitigations*
User accounts must only be created for those individuals who manage the server. These accounts should be granted the absolute minimum permissions necessary to complete the user’s task. User accounts and passwords that are built-in or default should be deleted or changed. To prevent password guessing, enforce complexity rules for user account passwords and limit the number of consecutive failed login attempts. Follow National Institute of Standards and Technology (NIST®) Special Publication SP 800-63B Digital Identity Guidelines (https://pages.nist.gov/800-63-3/sp800-63b.html#sec5). NSA recommends using multi-factor authentication for managing critical IT components like ESCs, when possible. However, not all ESCs currently support multi-factor authentication.

#### Default UC/VVoIP server configuration settings
The software on call-processing servers is typically installed with default configuration settings. The server may be configured by default for maximum functionality instead of adequate security. Unknown to the administrator, features could be enabled that are not appropriate for the installation environment.

##### *Mitigations*
Servers should be configured in accordance with the Security Technical Implementation Guides (STIGs) maintained at the DoD CYBER EXCHANGE (https://public.cyber.mil/stigs). If no STIGs are available for the deployed server, the vendor hardening guides should be followed instead. Periodically check the configuration settings to verify unattended changes to the configuration have not occurred. Settings that enable extra features should be carefully considered and evaluated before enabling.

#### Audit and logging apparatus
Without auditing and logging, unauthorized access or modification of the ESC will not be recorded. System records should be kept for any and all accesses to the ESC, whether by a user or administrator. Even an authorized change to the ESC’s configuration might result in a server malfunction. Detecting and recovering from server actions may require reconstructing the events from the audit log messages. UC/VVoIP systems perform call logging for calling records. This is done using call detail records (CDRs). CDRs can also be used for detecting toll fraud and other unauthorized usage of the UC/VVoIP call-processing system.

##### *Mitigations*
Enable auditing and logging (including CDRs) on the server and any critical devices such as conferencing systems, integrated voicemail systems, and gateway protocol translators. Review logs regularly for security and access violations. Store logs for a period of time in accordance with an organization’s security policy. Securely transmit logs to a separate logging server that has been hardened and capable of encrypting the logs at rest. Configure the logging server to accept entries only from authenticated machines.

#### Software vulnerabilities
Software vulnerabilities will inevitably arise in the ESC operating system and server applications. Software vulnerabilities can leave an ESC open to denial of service and remote access techniques.

##### *Mitigations*
Applying software security patches to the ESC should be applied immediately once available. Software updates should be cryptographically signed by the software vendor to ensure authenticity. To reduce the chances of updates causing unforeseen problems on production servers, test the updates on a test network that approximates the production network.

#### Malicious software
Since many ESCs run general-purpose operating systems, they are susceptible to the same computer viruses. This includes Trojan horses, worms, and other malicious software that affect these operating systems.

##### *Mitigations*
For ESCs that run atop general-purpose operating systems, install anti-virus software and regularly update virus definitions. Do not use ESCs for general Internet activities, such as email and web applications. If available, use a host-based firewall to protect against malware and to limit the spread of any infection. Enforce signed software (see Enforce Signed Software Execution Polices, https://www.nsa.gov/What-WeDo/Cybersecurity/Advisories-Technical-Guidance) to verify that the software is valid and to keep malicious software off the device.

#### Network services
Network services running on production servers represent a threat because unknown vulnerabilities could be exploited by a malicious actor. Types of network service protocols include DHCP, DNS, File Transfer Protocol (FTP), and Simple Mail Transfer Protocol (SMTP). Unnecessary network services running on an ESC provide additional attack surface and represent a drain on the resources needed to maintain calling services. If administrators are unaware of the services running on their ESCs, security updates could go unapplied, and compromises could go unnoticed.

##### *Mitigations*
Disable all network services on the ESC that are not in use and not needed for ESC functionality. Consult the server vendor to determine which services are required by the system. Carefully consider the security implications of maintaining a service against the features provided by the service.

#### Database security
UC/VVoIP call-processing systems may employ a separate database to store user, device, and call detail record information. Access to this database is typically managed via the remote management interface employed by the ESC, such as a web interface or vendor software. However, the database server may be directly accessible by other means that require protection. Compromising the database server compromises the call-processing network.

##### *Mitigations*
Secure the database by following all the guidelines for general software security outlined above.

Reference vendor documentation on securing the database. If the database is running on hardware (virtual or physical) separate from the ESC, VLANs should be used to create a dedicated communication channel between the database and the ESC. This channel should be encrypted. Authentication to the database server should be enabled. If possible, on the database server configure an allow list that only allows the ESC and management hosts to communicate with it.

#### Cryptographic key material
ESCs that support encrypted communications also store cryptographic key material for encryption and authentication purposes. A malicious actor with access to these servers may be able to extract the key material from the ESC. If successful, they may be able to impersonate the server and more easily eavesdrop on or capture calls, including some types of encrypted calls.

##### *Mitigations*
Different types of key material require different levels of protection. At a minimum, private keys used to digitally sign configuration and firmware files, downloadable applications, and certificates should be stored encrypted on the ESC. When backing up keys for recovery purposes, those keys should be stored on a computer or device that is not connected to the network. If supported by the ESC, use a cryptographic hardware token to store keys and to perform all cryptographic operations requiring access to the keys. Detailed information on key management, storage, and protection can be found in NIST Special Publication 800-57 (https://csrc.nist.gov/projects/key-management/key-managementguidelines).

### *Physical security protections*
In most cases, a server that can be physically reached can be compromised. An unauthorized person could easily disable the server by shutting it down or physically damaging it.

An unauthorized person could also use one of many common techniques to try to gain administrative access to the servers. BIOS passwords can be reset using jumpers on the motherboard, boot disks can be used to load alternate operating systems, passwords can be changed on servers, and many other techniques can be used to break into a server once physical access has been obtained. Server hardware can be physically damaged in a number of other ways, including intentional and unintentional fires, flooding from broken water pipes, and natural disasters.

##### Mitigations
Physical security precautions must be taken to deny unauthorized access to the ESC. Put the ESC in a locked cabinet in a locked and controlled room. Place alarms on the entry points to the server room. Use a control for access to the room that logs personnel entering and exiting. Use surveillance cameras and human monitoring in high-value installations.

Disable booting from removable media and enable BIOS passwords to prevent BIOS modification. 

Install fire suppression systems to protect the ESC servers from fire damage. Use suppression systems safe for electronic equipment in high value installations. To prevent accidental flooding, do not run water or sewage mains through the room housing the ESC. 

Ensure availability of services so, if a disaster destroys one data center, the whole organization does not lose UC/VVoIP call-processing services. For example, provide each geographic location with its own ESC and a backup connection to the PSTN service provider, or another remote ESC.

### *Service availability protections*
Availability of UC/VVoIP call-processing services is one of the most important considerations, because UC/VVoIP device users are accustomed to the 99.999% telephone dial tone off-hook standard. To ensure ESCs meet this level of availability, potential power and hardware failures, data loss, and access to emergency services must be addressed.

#### Hardware and power failures
Disk drives, power supplies, motherboards, memory, and other equipment will eventually fail along with power outages.

##### *Mitigations*
At a minimum, server hardware must have RAID (redundant arrays of independent disks) support to protect against disk drive failure. To protect against total hardware failure, configure ESCs in a high availability configuration that automatically takes over the duties of the primary server should it fail. Keep a spare duplicate server readily available to replace the failed server. Have redundant power supplies on separate circuits in case of a circuit failure. Provide short-term power backup using uninterruptible power supplies for all servers. When availability is critical, provide long-term backup power.

#### Data loss
High-availability hardware cannot protect against all hardware failures, software errors, or intrusions corrupting data on ESCs. Such failures should require quick recovery of ESCs to return to operational status.

##### *Mitigations*
To ensure a quick system recovery, regularly back up data from the UC/VVoIP systems. A backup and recovery policy that describes the recovery process must be in place. Test backup and recovery processes.

Store backups in an environmentally controlled secure location that will ensure they are not compromised. Encrypt any backups that leave the physical control of the organization (e.g., for shipping).

#### Emergency Services
One of the advantages of UC/VVoIP call-processing systems is being able to physically move a UC/VVoIP device from location to location and keep the same number. This physical move could be to a different room, a different building, or even a different city. The downside to having such flexibility is that it may be hard to pinpoint the exact physical location of a caller in cases of emergencies. The UC/VVoIP call processing system must maintain a reliable mechanism to connect to emergency services through the network that provides the location of the caller.

##### *Mitigations* 
Subscribe to an enhanced 911 (E911) service through the UC/VVoIP service provider and only route 911 calls that originate within the network to the 911 service. The E911 service provides a callback number as well as the physical location of the caller to emergency personnel. The subscriber should keep location information updated with the service provider. In large enterprises where there are multiple buildings or geographic locations, phone numbers should be grouped into direct inward dialing numbers (DIDs) denoting different physical locations. DIDs allow multiple phone numbers to be mapped to one virtual phone number. Users making emergency calls originating outside of the internal network should use other means (hotel phone, cell phone, etc.) to make emergency calls.

### *Client registration protections*
Many UC/VVoIP call-processing systems allow clients to register automatically with the system. The automatic registration keeps the administrator from needing to individually provision each device. Ease of deployment can lead to a malicious actor masquerading as a legitimate device registering with the ESC and subverting the system.

#### Mitigations
Configure the call-processing systems to use two-way authentication. The ESC should authenticate the identity of the client, and the client should similarly authenticate the ESC. Disable automatic registration to control registration to the ESC and prevent unauthorized devices from registering.

### *Remote management protections*
UC/VVoIP servers offer a variety of methods of remote management, such as webbased interfaces, proprietary vendor software, open source software such as Simple Network Management Protocols (SNMP) and—as part of a service agreement—remote management by service providers. Remote management poses a security threat because unauthorized access can seriously damage or compromise UC/VVoIP networks, capabilities, and security features. The flexibility and timesaving benefits of remote management can be safely used if appropriate security precautions are taken.

#### Web-based management interfaces
Many systems offer web-based remote management interfaces because of their familiarity and easy ability to remotely manage the UC/VVoIP system from anywhere on the network. However, web servers and web applications commonly are susceptible to a variety of vulnerabilities such as buffer overflows, cross-site scripting, authentication bypass, and injection. Additionally, some webservers allow communication over the HTTP protocol that is not encrypted. A malicious actor in the communication channel between the administrator and the web server could compromise important information such as the administrator’s password. Many browsers also allow users to cache login information for authenticating to web sites. Unauthorized access to administrator workstations could potentially compromise the login for the ESC.

##### *Mitigations*
Remotely managing an ESC via a web interface should only be done over an encrypted channel. TLS on the web server should be enabled and all non-TLS web access disabled. This will ensure all management sessions protect sensitive information such as login information.

The web-based interfaces should be only accessible via a management network that is separate from the general-purpose network. Additionally, access to the web-based interface should be limited to IP addresses of administrative workstations. If remotely managing the ESC from a remote location outside of the network’s perimeter, a trusted channel that connects the administrator into the management network before they can administer the ESC should be used.

Finally, all management hosts should have their web browsers configured to not cache login information.

#### Proprietary management software
Some vendors have written proprietary client and ESC software to manage their ESC. If the proprietary software and connection between the ESC and client are not encrypted and authenticated, then control over the ESC can be obtained by a malicious actor.

##### *Mitigations*
To protect the use of proprietary management software, take precautions similar to web-based interfaces. Network traffic should be encrypted. If the software does not support encryption, route traffic through an encrypted tunnel. Limit access of the management interface on the ESC to a separate administrative network and to specific IP addresses. Usernames and passwords must not be cached by the client software. Apply security updates to the ESC in accordance with the guidelines referenced in the Software Vulnerabilities, Malicious Software, and Network Services sections of this guide.

### *Summary of Part III*
This part of the report covered UC/VVoIP ESC best practices and mitigations for a secure system. Software updates (operating system and applications) should be cryptographically signed to ensure authenticity. Only software needed by the server should reside on the server. Management accounts and access to the server should be minimized and protected by good password policy. All settings (including default) should be evaluated for their impact on ESC security and system security. Enable secure auditing and logging with regular review to identify security issues. All cryptographic keys should be securely stored. Physically secure the ESC machinery and limit physical access. Authenticate, encrypt, and limit remote access as much as possible. A secure ESC will produce a more secure UC/VVoIP system overall.

Once security of the ESC is addressed, one can turn attention to the UC/VVoIP endpoints.

***

#### Table of Contents
{: .no_toc}

<ul><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-1/">Executive summary</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-2/">Part I - Network security best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-3/">Part II - Perimeter security best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-4/">Part III - Enterprise session controller security best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-5/">Part IV - UC/VVoIP endpoint best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-6/">End of guidelines</a></li></ul>

***

</div>
