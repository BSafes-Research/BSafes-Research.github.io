---
layout: default
title: . June 2021 -  Cybersecurity Framework Profile for Ransomware Risk Management
parent: NIST 
nav_order: 9790600
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
This is the mobile-friendly web version of the [original article](https://csrc.nist.gov/CSRC/media/Publications/nistir/draft/documents/NIST.IR.8374-preliminary-draft.pdf).

<img src="https://statics.bsafes.com/images/publications/NIST.IR.8374-preliminary-draft-22.png" alt="Cybersecurity Framework Profile for Ransomware Risk Management" style="display:block; margin:0 auto">

<img src="https://statics.bsafes.com/images/publications/NIST.IR.8374-preliminary-draft-2.png" alt="Cybersecurity Framework Profile for Ransomware Risk Management" style="display:block; margin:0 auto">

### Cybersecurity Framework Profile for Ransomware Risk Management
{: .no_toc }
## Cybersecurity Framework Profile for Ransomware Risk Management 
{: .no_toc }

William C. Barker   
Karen Scarfone   
William Fisher   
Murugiah Souppaya  

***

This is Preliminary Draft publication.
For additional details, see the Note to Reviewers on page ii.

***

William C. Barker
*Dakota Consulting*
*Silver Spring, MD*

Karen Scarfone
*Scarfone Cybersecurity*
*Clifton, VA*

William Fisher
*Applied Cybersecurity Division*
*Information Technology Laboratory*

Murugiah Souppaya
*Computer Security Division*
*Information Technology Laboratory*

June 2021

U.S. Department of Commerce
*Gina M. Raimondo, Secretary*

*National Institute of Standards and Technology*
*James K. Olthoff, Performing the Non-Exclusive Functions and Duties of the Under Secretary of Commerce for Standards and Technology & Director, National Institute of Standards and Technology*

***  

National Institute of Standards and Technology Interagency or Internal Report 8374 3 22 pages (June 2021)

> **Certain commercial entities, equipment, or materials may be identified in this document in order to describe an 5 experimental procedure or concept adequately. Such identification is not intended to imply recommendation or 6 endorsement by NIST, nor is it intended to imply that the entities, materials, or equipment are necessarily the best 7 available for the purpose.**
> 
>**There may be references in this publication to other publications currently under development by NIST in accordance 9 with its assigned statutory responsibilities. The information in this publication, including concepts and methodologies, 10 may be used by federal agencies even before the completion of such companion publications. Thus, until each 11 publication is completed, current requirements, guidelines, and procedures, where they exist, remain operative. For 12 planning and transition purposes, federal agencies may wish to closely follow the development of these new 13 publications by NIST.**
>
>**Organizations are encouraged to review all draft publications during public comment periods and provide feedback to  NIST. Many NIST cybersecurity publications, other than the ones noted above, are available at  https://csrc.nist.gov/publications.**

**Public comment period: *June 9, 2021 through July 9, 2021***

National Institute of Standards and Technology
Attn: Applied Cybersecurity Division, Information Technology Laboratory
100 Bureau Drive (Mail Stop 2000) Gaithersburg, MD 20899-2000 21 
Email: ransomware@nist.gov

All comments are subject to release under the Freedom of Information Act (FOIA).

**Reports on Computer Systems Technology**
The Information Technology Laboratory (ITL) at the National Institute of Standards and Technology (NIST) promotes the U.S. economy and public welfare by providing technical leadership for the Nation’s measurement and standards infrastructure. ITL develops tests, test methods, reference data, proof of concept implementations, and technical analyses to advance the development and productive use of information technology. ITL’s responsibilities include the development of management, administrative, technical, and physical standards and guidelines for the cost-effective security and privacy of other than national security-related information in federal information systems.

***

1. TOC
{:toc}

## Abstract
Ransomware is a type of malicious attack where attackers encrypt an organization’s data and demand payment to restore access. In some instances, attackers may also steal an organization’s information and demand an additional payment in return for not disclosing the information to authorities, competitors, or the public. This Ransomware Profile identifies the Cybersecurity Framework Version 1.1 security objectives that support preventing, responding to, and recovering from ransomware events. The profile can be used as a guide to managing the risk of ransomware events. That includes helping to gauge an organization's level of readiness to counter ransomware threats and to deal with the potential consequences of events.

**Keywords**
Cybersecurity Framework; detect; identify; protect; ransomware; recover; respond; risk; security.

**Acknowledgments**
The authors wish to thank all individuals and organizations that contributed to the creation of this document

**Note to Reviewers**
NIST is adopting an agile and iterative methodology to publish this content. The content is being made available as soon as possible, rather than delaying release until all the elements are completed. This is a preliminary draft. There will be at least one additional public comment period for this.

Any updates for this document that are not yet published in an errata update or revision— including additional issues and corrections—will be posted as they are identified. See the NIST Interagency or Internal Report (NISTIR) 8374 publication details page for more information.

## Table of Contents

- **1 Introduction** 
  - 1.1 The Ransomware Challenge 
  - 1.2 Audience
  - 1.3 Additional Resources
- **2 The Ransomware Profile**
- **References**

## 1 Introduction
The Ransomware Profile defined in this report maps security objectives from the [*Framework for Improving Critical Infrastructure Cybersecurity, Version 1.1*](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.04162018.pdf) [1] (also known as the Cybersecurity Framework) to security capabilities and measures that support preventing, responding to, and recovering from ransomware events. The profile can be used as a guide to managing the risk of ransomware events. That includes helping to gauge an organization's level of readiness to mitigate ransomware threats and to react to the potential impact of events. The profile can also be used to identify opportunities for improving cybersecurity to help thwart ransomware.

### 1.1 The Ransomware Challenge
Ransomware is a type of malicious attack where attackers encrypt an organization’s data and  demand payment to restore access. In some instances, attackers may also steal an organization’s information and demand an additional payment in return for not disclosing the information to authorities, competitors, or the public. Ransomware disrupts or halts an organization’s operations and poses a dilemma for management: pay the ransom and hope that the attackers keep their word about restoring access and not disclosing data, or do not pay the ransom and restore operations themselves. The methods used to gain access to an organization’s information and systems are common to cyberattacks more broadly, but they are aimed at forcing a ransom to be paid. Ransomware attacks target the organization’s data.

Fortunately, organizations can follow recommended steps to prepare for and reduce the potential for successful ransomware attacks. This includes identifying and protecting critical data, systems, and devices from ransomware, and preparing to respond to any ransomware attacks that succeed. There are many resources available to assist organizations in these efforts. They include information from the [National Institute of Standards and Technology (NIST)](https://csrc.nist.gov/projects/ransomware-protection-and-response), the Federal Bureau of Investigation (FBI), and the [Department of Homeland Security (DHS)](https://csrc.nist.gov/projects/ransomware-protection-and-response).

The security capabilities and measures provided in this profile support a detailed approach to preventing and mitigating ransomware events. Even without undertaking all of these measures, there are some basic preventative steps that an organization can take now to protect against the ransomware threat. These include:

- **Use antivirus software at all times.** Set your software to automatically scan emails and flash drives. 

- **Keep computers fully patched.** Run scheduled checks to keep everything up-to-date. 

- **Block access to ransomware sites.** Use security products or services that block access to known ransomware sites. 

- **Allow only authorized apps.** Configure operating systems or use third-party software to allow only authorized applications on computers.

- **Restrict personally owned devices** on work networks. 

- **Use standard user accounts** versus accounts with administrative privileges whenever possible.

- **Avoid using personal apps**—like email, chat, and social media—from work computers. 

- **Beware of unknown sources.** Don’t open files or click on links from unknown sources unless you first run an antivirus scan or look at links carefully.

Steps that organizations can take now to help recover from a future ransomware event include:

- **Make an incident recovery plan.** Develop and implement an incident recovery plan with defined roles and strategies for decision making. This can be part of a continuity of operations plan. 

- **Backup and restore.** Carefully plan, implement, and test a data backup and restoration strategy—and secure and isolate backups of important data. 

- **Keep your contacts.** Maintain an up-to-date list of internal and external contacts for ransomware attacks, including law enforcement.

### 1.2 Audience

The Ransomware Profile is intended for a general audience and is broadly applicable to organizations that:

- have already adopted the NIST Cybersecurity Framework to help identify, assess, and manage cybersecurity risks; 

- are familiar with the Cybersecurity Framework and want to improve their risk postures; or 

- are unfamiliar with the Cybersecurity Framework but need to implement risk management frameworks to meet ransomware threats.

### 1.3 Additional Resources
NIST’s National Cybersecurity Center of Excellence (NCCoE) has produced additional reference materials intended to support ransomware threat mitigation. These references include:

- [*NIST Special Publication (SP) 1800-26, Data Integrity: Detecting and Responding to Ransomware and Other Destructive Events*](https://doi.org/10.6028/NIST.SP.1800-26) addresses how an organization can handle an attack when it occurs, and what capabilities it needs to have in place to detect and respond to destructive events. 

- [*NIST SP 1800-25, Data Integrity: Identifying and Protecting Assets Against Ransomware and Other Destructive Events*](https://doi.org/10.6028/NIST.SP.1800-25) addresses how an organization can work before an attack to identify its assets and potential vulnerabilities and remedy the discovered vulnerabilities to protect these assets. 

- [*NIST SP 1800-11, Data Integrity: Recovering from Ransomware and Other Destructive Events*](https://doi.org/10.6028/NIST.SP.1800-11) addresses approaches for recovery should a data integrity attack be successful. 

- [*Protecting Data from Ransomware and Other Data Loss Events*](https://www.nccoe.nist.gov/sites/default/files/library/supplemental-files/msp-protecting-data-extended.pdf) is a guide for managed service providers to conduct, maintain, and test backup files that are critical to recovering from ransomware attacks.

NIST has many other resources that, while not ransomware-specific, contain valuable information about preventing, preparing for, detecting, and responding and recovering from ransomware events. Several of these resources are highlighted below. For the complete list of resources, visit NIST’s Ransomware Protection and Response site at <https://csrc.nist.gov/ransomware>.

- Improving the security of **telework, remote access,** and **bring-your-own-device (BYOD)** technologies:

  - [Telework: Working Anytime, Anywhere project](https://csrc.nist.gov/projects/telework-working-anytime-anywhere) 

  - [NIST SP 800-46 Revision 2, *Guide to Enterprise Telework, Remote Access, and Bring Your Own Device (BYOD) Security*](https://csrc.nist.gov/publications/detail/sp/800-46/rev-2/final)
  
- **Patching software** to eliminate vulnerabilities:

  - [NIST SP 800-40 Revision 3, *Guide to Enterprise Patch Management Technologies*](https://csrc.nist.gov/publications/detail/sp/800-40/rev-3/final)

  - [Critical Cybersecurity Hygiene: Patching the Enterprise project](https://www.nccoe.nist.gov/projects/building-blocks/patching-enterprise)

- **Using application control technology** to prevent ransomware execution:

- [NIST SP 800-167, *Guide to Application Whitelisting*](https://csrc.nist.gov/publications/detail/sp/800-167/final)

- Finding low-level guidance on securely configuring software to eliminate
vulnerabilities:

  - [National Checklist Program](https://csrc.nist.gov/projects/national-checklist-program)

- Getting the latest **information on known vulnerabilities:**

  - [National Vulnerability Database](https://csrc.nist.gov/projects/national-vulnerability-database)

- **Planning for** cybersecurity event **recovery:**

  - [NIST SP 800-184, *Guide for Cybersecurity Event Recovery*](https://csrc.nist.gov/publications/detail/sp/800-184/final)

- **Contingency planning for restoring operations** after a disruption caused by ransomware: 

   - [NIST SP 800-34 Revision 1, *Contingency Planning Guide for Federal Information Systems*](https://csrc.nist.gov/publications/detail/sp/800-34/rev-1/final)

- **Handling ransomware** and other malware **incidents:**

  - [NIST SP 800-83 Revision 1, *Guide to Malware Incident Prevention and Handling for Desktops and Laptops*](https://csrc.nist.gov/publications/detail/sp/800-83/rev-1/final)

- **Handling** cybersecurity **incidents** in general: 

  - [NIST SP 800-61 Revision 2, *Computer Security Incident Handling Guide*](https://csrc.nist.gov/publications/detail/sp/800-61/rev-2/final)
  
## 2 The Ransomware Profile
The Ransomware Profile aligns organizations’ ransomware prevention and mitigation requirements, objectives, risk appetite, and resources with the elements of the Cybersecurity Framework. The purpose of the profile is to help organizations identify and prioritize opportunities for improving their ransomware resistance. Organizations can use this document as a guide for profiling the state of their own readiness. For example, they can determine their current state and set a target profile to identify gaps to achieve their goal.

Table 1 defines the Ransomware Profile. The first two columns of the table list the relevant Categories and Subcategories from the Cybersecurity Framework. The third column briefly explains how each of the listed Subcategories supports preventing, responding to, and recovering from ransomware events.

The second column of Table 1 also cites relevant requirements from two of the informative references included in the Cybersecurity Framework: International Organization for Standardization/International Electrotechnical Commission (ISO/IEC) 27001:2013, *Information technology—Security techniques—Information security management systems—Requirements* [2] and NIST SP 800-53 Revision 5, *Security and Privacy Controls for Information Systems and Organizations* [3]. Additional informative references may be included in subsequent versions of this report.

The Cybersecurity Framework lists additional Informative References for each Subcategory. Informative References are specific sections of standards, guidelines, and practices common among critical infrastructure sectors that illustrate a method to achieve the outcomes associated with each subcategory. The Informative References in the Cybersecurity Framework are illustrative and not exhaustive. They are based upon cross-sector guidance most frequently referenced during the Framework development process.

The five Cybersecurity Framework Functions that are used to organize the Categories are:

- **Identify** – Develop an organizational understanding to manage cybersecurity risk to systems, people, assets, data, and capabilities. The activities in the Identify Function are foundational for effective use of the Framework. Understanding the business context, the resources that support critical functions, and the related cybersecurity risks enables an organization to focus and prioritize its efforts, consistent with its risk management strategy and business needs. 

- **Protect** – Develop and implement appropriate safeguards to ensure delivery of critical services. The Protect Function supports the ability to limit or contain the impact of a potential cybersecurity event.

- **Detect** – Develop and implement appropriate activities to identify the occurrence of a cybersecurity event. The Detect Function enables timely discovery of cybersecurity events. 

- **Respond** – Develop and implement appropriate activities to take action regarding a detected cybersecurity incident. The Respond Function supports the ability to contain the impact of a potential cybersecurity incident.

- **Recover** – Develop and implement appropriate activities to maintain plans for resilience and to restore any capabilities or services that were impaired due to a cybersecurity incident. The Recover Function supports timely recovery to normal operations to reduce the impact from a cybersecurity incident.

**Table 1: Ransomware Profile**
![Table 1: Ransomware Profile](https://statics.bsafes.com/images/publications/cybersecurity-framework-profile-for-ransomware-risk-management-table-1.png)
![Table 1: Ransomware Profile](https://statics.bsafes.com/images/publications/cybersecurity-framework-profile-for-ransomware-risk-management-table-2.png)
![Table 1: Ransomware Profile](https://statics.bsafes.com/images/publications/cybersecurity-framework-profile-for-ransomware-risk-management-table-3.png)
![Table 1: Ransomware Profile](https://statics.bsafes.com/images/publications/cybersecurity-framework-profile-for-ransomware-risk-management-table-4.png)
![Table 1: Ransomware Profile](https://statics.bsafes.com/images/publications/cybersecurity-framework-profile-for-ransomware-risk-management-table-5.png)
![Table 1: Ransomware Profile](https://statics.bsafes.com/images/publications/cybersecurity-framework-profile-for-ransomware-risk-management-table-6.png)
![Table 1: Ransomware Profile](https://statics.bsafes.com/images/publications/cybersecurity-framework-profile-for-ransomware-risk-management-table-7.png)
![Table 1: Ransomware Profile](https://statics.bsafes.com/images/publications/cybersecurity-framework-profile-for-ransomware-risk-management-table-8.png)
![Table 1: Ransomware Profile](https://statics.bsafes.com/images/publications/cybersecurity-framework-profile-for-ransomware-risk-management-table-9.png)
![Table 1: Ransomware Profile](https://statics.bsafes.com/images/publications/cybersecurity-framework-profile-for-ransomware-risk-management-table-10.png)
![Table 1: Ransomware Profile](https://statics.bsafes.com/images/publications/cybersecurity-framework-profile-for-ransomware-risk-management-table-11.png)
![Table 1: Ransomware Profile](https://statics.bsafes.com/images/publications/cybersecurity-framework-profile-for-ransomware-risk-management-table-12.png)
## References

[1] National Institute of Standards and Technology (2018) Framework for Improving Critical Infrastructure Cybersecurity, Version 1.1. (National Institute of Standards and Technology, Gaithersburg, MD). <https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.04162018.pdf>

[2] International Organization for Standardization/International Electrotechnical Commission (ISO/IEC) (2013) Information technology—Security techniques—Information security management systems—Requirements. (International Organization for Standardization/International Electrotechnical Commission, Geneva, Switzerland), ISO/IEC 27001:2013. <https://www.iso.org/isoiec-27001-information-security.html> 

[3] Joint Task Force (2020) Security and Privacy Controls for Information Systems and Organizations. (National Institute of Standards and Technology, Gaithersburg, MD), NIST Special Publication (SP) 800-53, Rev. 5. Includes updates as of December 10,  2020. <https://doi.org/10.6028/NIST.SP.800-53r5>

</div>
