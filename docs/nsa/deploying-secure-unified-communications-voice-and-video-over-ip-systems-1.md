---
layout: default
title: Executive summary
parent: . June 2021, Deploying Secure Unified Communications/Voice and Video over IP Systems  
grand_parent: NSA 
nav_order: 10 
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

## Executive summary
Unified Communications (UC) and Voice and Video over IP (VVoIP) call-processing systems provide rich collaboration tools and offer flexible ways to communicate by combining voice, video conferencing, and instant messaging in the modern workplace. Today these systems are integrated into an enterprise’s existing Internet Protocol (IP) infrastructure, use commodity software, and are likely to use open-source and standard protocols.

However, the same IP infrastructure that enables UC/VVoIP systems also extends the attack surface into an enterprise’s network, introducing vulnerabilities and the potential for unauthorized access to communications. These vulnerabilities were harder to reach in earlier telephony systems, but now voice services and infrastructure are accessible to malicious actors who penetrate the IP network to eavesdrop on conversations, impersonate users, commit toll fraud, or perpetrate a denial of service effects. Compromises can lead to high-definition room audio and/or video being covertly collected and delivered using the IP infrastructure as a transport mechanism.

If properly secured, a UC/VVoIP system limits the risk to data confidentiality and communication system availability. This security requires careful consideration, detailed planning and deployment, and continuous testing and maintenance. *Deploying Secure Unified Communications/Voice and Video over IP Systems* outlines best practices for the secure deployment of UC/VVoIP systems and presents mitigations for vulnerabilities due to inadequate network design, configurations, and connectivity. This report is separated into four parts. Each part speaks to the system administrators who will lead mitigation efforts in each area of the system. It describes the mitigations and best practices to use when:

- Preparing networks
- Establishing perimeters
- Using enterprise session controllers (ESCs)
- Adding UC/VVoIP endpoints for deployment of a UC/VVoIP system

Using the mitigations and best practices explained here, organizations may embrace the benefits of UC/VVoIP while minimizing the risk of disclosing sensitive information or losing service.

***

#### Table of Contents
{: .no_toc}

<ul><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-1/">Executive summary</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-2/">Part I - Network security best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-3/">Part II - Perimeter security best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-4/">Part III - Enterprise session controller security best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-5/">Part IV - UC/VVoIP endpoint best practices and mitigations</a></li><li> <a href="/docs/nsa/deploying-secure-unified-communications-voice-and-video-over-ip-systems-6/">End of guidelines</a></li></ul>

***

</div>
