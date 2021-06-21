---
layout: default
title: . June 2021, Deploying Secure Unified Communications/Voice and Video over IP Systems  
parent: NSA 
has_children: true
nav_order: 979060000 
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
This is the mobile-friendly web version of the [original article](https://media.defense.gov/2021/Jun/17/2002744054/-1/-1/1/CTR_DEPLOYING%20SECURE%20VVOIP%20SYSTEMS.PDF).

<img src="https://statics.bsafes.com/images/publications/CTR_DEPLOYING%20SECURE%20VVOIP%20SYSTEMS-43.png" alt="Deploying Secure Unified Communications/Voice and Video over IP Systems" style="display:block; margin:0 auto">

## National Security Agency Cybersecurity Technical Report 
{: .no_toc }

# Deploying Secure Unified Communications/Voice and Video over IP Systems 
{: .no_toc }
### June 2021 
{: .no_toc }

SN U/OO/153515-21  
PP-21-0827  
Version 1.0  
 
1. TOC
{:toc}

## Notices and history

### *Document change history*
![Document change history](https://statics.bsafes.com/images/publications/deploying-secure-unified-communications-voice-and-video-over-ip-systems-Document%20change%20history.png)

### *Disclaimer of warranties and endorsement*

The information and opinions contained in this document are provided "as is" and without any warranties or guarantees. Reference herein to any specific commercial products, process, or service by trade name, trademark, manufacturer, or otherwise, does not necessarily constitute or imply its endorsement, recommendation, or favoring by the United States Government, and this guidance shall not be used for advertising or product endorsement purposes.

### *Trademark recognition*
Bluetooth is a registered trademark of Bluetooth Special Interest Group (SIG), Inc. NIST is a trademark and brand of National Institute of Standards and Technology.

## Publication information

### *Contact information*

Client Requirements / General Cybersecurity Inquiries: 
Cybersecurity Requirements Center, 410-854-4200, Cybersecurity_Requests@nsa.gov 

Media Inquiries: 
Media Relations, 443-634-0721, MediaRelations@nsa.gov

### *Purpose*
This document was developed in furtherance of NSA’s cybersecurity missions. This includes its responsibilities to identify and disseminate threats to National Security Systems, Department of Defense information systems, and the Defense Industrial Base, and to develop and issue cybersecurity specifications and mitigations. This information may be shared broadly to reach all appropriate stakeholders.

## Table of contents

**Deploying Secure Unified Communications/Voice and Video over IP Systems..i**
- **Executive summary** 
- **Part I: Network security best practices and mitigations**
    - Accessibility and network separation
        - Mitigations
    - Call eavesdropping protections 
        - Mitigations 
    - Physical access protections
        - Mitigations 
    - Network availability protections 
        -  Mitigations 
    - Network services and protocols protections
        - DHCP
        - DNS
        - NTP
    - Trusted path and channel protections 
        - Mitigations 
    -  Summary of Part I

- **Part II: Perimeter security best practices and mitigations** 
    - PSTN gateway protections
        - Mitigations 
    - Protections for public IP networks functioning as voice carriers
        - Mitigations 
    - Signaling gateway protections 
        - Mitigations 
    - Media gateway protections 
        - Mitigations 
    - Wide area network (WAN) link protections
        - Mitigations 
    - Cloud connectivity protections 
        - Mitigations 

- Summary of Part II

- **Part III: Enterprise session controller security best practices and mitigations** 
    - Software and application protections
        - User accounts and passwords
        - Default UC/VVoIP server configuration settings
        - Audit and logging apparatus 
        -  Software vulnerabilities 
        - Malicious software
        - Network services 
        - Database security
        - Cryptographic key material
    - Physical security protections 
        - Mitigations 
    - Service availability protections
        - Hardware and power failures
        - Data loss
        - Emergency Services 
    - Client registration protections
        - Mitigations 
    - Remote management protections 
        - Web-based management interfaces
        - Proprietary management software 
    - Summary of Part III

- **Part IV: UC/VVoIP endpoint best practices and mitigations** 
    - Software and hardware security
        - Software vulnerabilities 
        - Third-party software 
        - Malicious software
        - Embedded microphones
    - Remote management of UC/VVoIP endpoints
        - Downloading firmware and configuration files
        - Web-based management interface
        - Simple Network Management Protocol (SNMP) 
        - Telnet 
    - Network connectivity
        - Ethernet
        - Infrared 
        - Wireless personal area network (WPAN)
        - Wireless local area network (WLAN)
        - Network connectivity mitigation summary 
    - Convergence features
        - Mitigations
    - Softphones
        - Mitigations 
    - Summary of Part IV

- **End of guidelines**

## Figures

Figure 1: Logical view of a UC/VVoIP system following NSA guidelines

Figure 2: Perimeter security device placement following NSA guidelines

</div>
