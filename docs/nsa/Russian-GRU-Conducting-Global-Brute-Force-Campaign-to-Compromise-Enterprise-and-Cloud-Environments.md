---
layout: default
title: . July 2021 - Russian GRU Conducting Global Brute Force Campaign to Compromise Enterprise and Cloud Environments
parent: NSA 
has_children: true
nav_order: 9790500
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
This is the mobile-friendly web version of the [original article](https://media.defense.gov/2021/Jul/01/2002753896/-1/-1/1/CSA_GRU_GLOBAL_BRUTE_FORCE_CAMPAIGN_UOO158036-21.PDF).
{: .no_toc }

# Russian GRU Conducting Global Brute Force Campaign to Compromise Enterprise and Cloud Environments
{: .no_toc}

![Russian GRU Conducting Global Brute Force Campaign to Compromise Enterprise and Cloud Environments](https://statics.bsafes.com/images/publications/CSA_GRU_GLOBAL_BRUTE_FORCE_CAMPAIGN_UOO158036-21-8.png)


### Cybersecurity Advisory
{: .no_toc }


1. TOC
{:toc}

## Executive summary
Since at least mid-2019 through early 2021, Russian General Staff Main Intelligence Directorate (GRU) 85th Main Special Service Center (GTsSS), military unit 26165, used a Kubernetes® cluster to conduct widespread, distributed, and anonymized brute force access attempts against hundreds of government and private sector targets worldwide. GTsSS malicious cyber activity has previously been attributed by the private sector using the names Fancy Bear, APT28, Strontium, and a variety of other identifiers. The 85th GTsSS directed a significant amount of this activity at organizations using Microsoft Office 365® cloud services; however, they also targeted other service providers and onpremises email servers using a variety of different protocols. These efforts are almost certainly still ongoing.

This brute force capability allows the 85th GTsSS actors to access protected data, including email, and identify valid account credentials. Those credentials may then be used for a variety of purposes, including initial access, persistence, privilege escalation, and defense evasion. The actors have used identified account credentials in conjunction with exploiting publicly known vulnerabilities, such as exploiting Microsoft Exchange servers using CVE 2020-0688 and CVE 2020-17144, for remote code execution and further access to target networks. After gaining remote access, many well-known tactics, techniques, and procedures (TTPs) are combined to move laterally, evade defenses, and collect additional information within target networks.

Network managers should adopt and expand usage of multi-factor authentication to help counter the effectiveness of this capability. Additional mitigations to ensure strong access controls include time-out and lock-out features, the mandatory use of strong passwords, implementation of a Zero Trust security model that uses additional attributes when determining access, and analytics to detect anomalous accesses. Additionally, organizations can consider denying all inbound activity from known anonymization services, such as commercial virtual private networks (VPNs) and The Onion Router (TOR), where such access is not associated with typical use.

</div>
