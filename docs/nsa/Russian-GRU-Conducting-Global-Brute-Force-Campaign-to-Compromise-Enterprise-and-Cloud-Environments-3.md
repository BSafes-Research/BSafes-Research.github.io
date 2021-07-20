---
layout: default
title: Detection and mitigation
parent: . July 2021 - Russian GRU Conducting Global Brute Force Campaign to Compromise Enterprise and Cloud Environments  
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

.youtube-container {
    position: relative;
    width: 100%;
    height: 0;
    padding-bottom: 56.25%;
}
.youtube-video {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}

</style>

<div class="dont-break-out" markdown="1">

1. TOC
{:toc}

## Detection and mitigation
In an attempt to obfuscate its true origin and to provide a degree of anonymity, the Kubernetes cluster normally routes brute force authentication attempts through TOR and commercial VPN services, including CactusVPN, IPVanish® , NordVPN® , ProtonVPN® , Surfshark® , and WorldVPN. Authentication attempts that did not use TOR or a VPN service were also occasionally delivered directly to targets from nodes in the Kubernetes cluster.

The scalable nature of the password spray capability means that specific indicators of compromise (IOC) can be easily altered to bypass IOC-based mitigation. In addition to blocking activity associated with the specific indicators listed in this Cybersecurity Advisory, organizations should consider denying all inbound activity from known TOR nodes and other public VPN services to exchange servers or portals where such access is not associated with typical use.

### *IP addresses*
Although the exact makeup of the Kubernetes cluster may change over time, a number of nodes have been identified as responsible for sending and routing the brute force authentication attempts. At some point between November 2020 and March 2021, the following IP addresses were identified as corresponding to nodes in the Kubernetes cluster:

- 158.58.173[.]40

- 185.141.63[.]47

- 185.233.185[.]21

- 188.214.30[.]76

- 195.154.250[.]89

- 93.115.28[.]161

- 95.141.36[.]180

- 77.83.247[.]81

- 192.145.125[.]42

- 193.29.187[.]60

### *User agents*
In cases where HTTP was the underlying protocol used to deliver authentication requests, the actors used many different User-Agent strings, which are crafted to appear consistent with those sent by legitimate client software. Some of the User-Agent strings delivered in the authentication requests are incomplete or truncated versions of legitimate User-Agent strings, offering the following unique detection opportunities:

- ‘Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.’ 

- ‘Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.110 Safari/537.36’ 

- ‘Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:63.0) Gecko/20100101 Firefox/63.0’ 

- ‘Mozilla/5.0 (Windows NT 6.1; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.110 Safari/537.36’ 

- ‘Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_1) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.1 Safari/605.1.15’ 

- ‘Microsoft Office/14.0 (Windows NT 6.1; Microsoft Outlook 14.0.7162; Pro’ 

- ‘Microsoft Office/14.0 (Windows NT 6.1; Microsoft Outlook 14.0.7166; Pro)’ 

- ‘Microsoft Office/14.0 (Windows NT 6.1; Microsoft Outlook 14.0.7143; Pro)’ 

- ‘Microsoft Office/15.0 (Windows NT 6.1; Microsoft Outlook 15.0.4605; Pro)’

### *Yara rule*
The following Yara rule matches the reGeorg variant web shell used by the actors. As this is a publicly available web shell, the rule does not uniquely identify 85th GTsSS malicious activity.<sup>[3]</sup>

rule reGeorg_Variant_Web shell {  
strings:  
$pageLanguage = "<%@ Page Language=\"C#\""  
$obfuscationFunction = "StrTr"  
$target = "target_str"   
$IPcomms = "System.Net.IPEndPoint"  
$addHeader = "Response.AddHeader"  
$socket = "Socket"  
condition:  
5 of them  
}  

### *General mitigations*
As with mitigations for other credential theft techniques, organizations can take the following measures to ensure strong access control:

- Use multi-factor authentication with strong factors and require regular reauthentication<sup>[4]</sup>. Strong authentication factors are not guessable, so they would not be guessed during brute force attempts. 

- Enable time-out and lock-out features whenever password authentication is needed. Time-out features should increase in duration with additional failed login attempts. Lock-out features should temporarily disable accounts after many consecutive failed attempts. This can force slower brute force attempts, making them infeasible. 

- Some services can check passwords against common password dictionaries when users change passwords, denying many poor password choices before they are set. This makes brute-force password guessing far more difficult.

- For protocols that support human interaction, utilize captchas to hinder automated access attempts. 

- Change all default credentials and disable protocols that use weak authentication (e.g., clear-text passwords, or outdated and vulnerable authentication or encryption protocols) or do not support multi-factor authentication. Always configure access controls on cloud resources carefully to ensure that only wellmaintained and well-authenticated accounts have access<sup>[5]</sup> . 

- Employ appropriate network segmentation and restrictions to limit access and utilize additional attributes (such as device information, environment, access path) when making access decisions, with the desired state being a Zero Trust security model<sup>[6]</sup>. 

- Use automated tools to audit access logs for security concerns and identify anomalous access requests.


***

#### Table of Contents
{: .no_toc}

<ul><li> <a href="/docs/nsa/Russian-GRU-Conducting-Global-Brute-Force-Campaign-to-Compromise-Enterprise-and-Cloud-Environments-1/">Description of targets</a></li><li> <a href="/docs/nsa/Russian-GRU-Conducting-Global-Brute-Force-Campaign-to-Compromise-Enterprise-and-Cloud-Environments-2/">Known TTPs</a></li><li> <a href="/docs/nsa/Russian-GRU-Conducting-Global-Brute-Force-Campaign-to-Compromise-Enterprise-and-Cloud-Environments-3/">Detection and mitigation</a></li><li> <a href="/docs/nsa/Russian-GRU-Conducting-Global-Brute-Force-Campaign-to-Compromise-Enterprise-and-Cloud-Environments-4/">Works cited</a></li></ul>

***

</div>
