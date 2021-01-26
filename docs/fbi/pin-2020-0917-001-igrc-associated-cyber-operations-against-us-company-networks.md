---
layout: default
title: . PIN# 20200917-001 - IRGC-Associated Cyber Operations Against US Company Networks  
parent: FBI 
nav_order: 980031499 
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
This is the mobile-friendly web version of the [original article](https://www.aba.com/-/media/documents/cybersecurity-reports/pin/fbi-pin-irgc-associated-cyber-ops-09172020.pdf?rev=369cf164519f424d9cb8bf1591c36758).

<img src="https://statics.bsafes.com/images/publications/FBI%20PIN%20IRGC%20Associated%20Cyber%20Ops%2009172020.png" alt="IRGC-Associated Cyber Operations Against US" style="display:block; margin:0 auto">

### 17 September 2020 
{: .no_toc }
#### PIN Number
{: .no_toc }
### 20200917-001
{: .no_toc }  
# IRGC-Associated Cyber Operations Against US 
{: .no_toc }

1. TOC
{:toc}

The following information is being provided by the FBI, with no guarantees or warranties, for potential use at the sole discretion of recipients to protect against cyber threats. This data is provided to help cyber security professionals and system administrators guard against the persistent malicious actions of cyber actors. This product was coordinated with DHS-CISA.

This product is marked TLP:WHITE. Subject to standard copyright rules, TLP:WHITE information may be distributed without restriction.

# IRGC-Associated Cyber Operations Against US Company Networks

## Summary
The FBI is sharing information about a group of Iran-based cyber actors recently indicted for conducting malicious cyber operations to obtain access to US-based networks and steal information. The Iranian nationals indicted are Said Pourkarim Arabi, a member of Iran’s Islamic Revolutionary Guard Corps (IRGC), Mohammad Reza Espargham, and Mohammad Bayati, both associates of Arabi. Since at least 2015, the actors conducted malicious cyber activity against US-based and foreign organizations and companies involved in aerospace or satellite technology and international government organizations in the United States, the United Kingdom, Singapore, Australia, and Israel. 

The FBI is providing an overview of the group’s tactics, techniques, and procedures, as well as indicators of compromise, to aid potential targets in the identification of malicious activity.

## Details
The FBI has observed Iran-based cyber actors conducting multi-phased cyber operations targeted against companies in the United States. The FBI advises these cyber actors can achieve substantial unauthorized access to US company networks through harvesting of personally identifying information, use of fraudulent identities, social engineering, and off-the-shelf malicious tools. These operations have led to significant financial losses, with the actors accessing sensitive business information, intellectual property, and vendor information. 

The FBI has observed these actors beginning their operations by identifying employees connected to the US aerospace and satellite industry. The FBI judges the malicious cyber actors obtained personal details needed to impersonate employees via openly available sources, such as professional development and networking Web sites. The actors create fraudulent social
media accounts impersonating those individuals. The actors then use information about those employees for other purposes related to their operations, such as registering email and PayPal accounts and fraudulently purchasing domains and hacking tools. 

The FBI has observed the actors create and send customized spear-phishing emails purporting to be from the individuals whose identities they had stolen. The emails would entice recipients to take action – usually clicking on a malicious link, which would download malware being downloaded onto the victim’s computer and enable unauthorized access to victim networks. In one instance, the actors were observed hosting malicious code on a file-sharing service registered in the name of a US company employee, and including links to that malicious code in spear-phishing emails. One of the actors was observed using a fraudulent domain to host malware, then sending a link to the malware via spear phishing.

The FBI observed these actors conducting follow-on activities to expand and maintain their unauthorized access, such as creating additional backdoors and escalating privileges. The actors were observed using the below tools to exploit victims.

<table cellpadding="0" cellspacing="0">
	<tbody>
		<tr>
			<td style="background-color: rgb(84, 172, 210);" valign="top"><strong>Tool</strong>
				<br>
			</td>
			<td style="background-color: rgb(84, 172, 210);" valign="top"><strong>Description</strong>
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">Metasploit Framework
				<br>
			</td>
			<td valign="top">An open source pen-testing framework sometimes used by attackers to exploit vulnerable systems and gain remote access. Metasploit contains a catalog of prewritten modules and payloads that make its usage by attackers very simple.
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">Mimikatz
				<br>
			</td>
			<td valign="top">A post-exploitation tool that dumps passwords from memory, as well as hashes, PINS, and Kerberos tickets
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">NanoCore RAT
				<br>
			</td>
			<td valign="top">Remote Access Trojan that allows a user to remotely access and control computers. Also used to record user credentials and conduct surveillance using infected computers.
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">OCRA shell-code stagers
				<br>
			</td>
			<td valign="top">Used to execute intrusions once malicious code is active on a running system.
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">Python Backdoor
				<br>
			</td>
			<td valign="top">Open source backdoor written in the Python programming language. Additional way to control a victim&rsquo;s computer.
				<br>
			</td>
		</tr>
	</tbody>
</table>

The FBI advises that the below indicators of compromise are historical in nature, but may be used to identify historical targeting efforts.

<table cellpadding="0" cellspacing="0">
	<tbody>
		<tr>
			<td style="background-color: rgb(84, 172, 210);" valign="top"><strong>Indicator</strong>
				<br>
			</td>
			<td style="background-color: rgb(84, 172, 210);" valign="top"><strong>Context</strong>
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">tleanalyser[.]com
				<br>
			</td>
			<td valign="top">May be included in spear-phishing messages as a provided link
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">theanalyser@gmail[.]com
				<br>
			</td>
			<td valign="top">May be included in spear-phishing messages as contact email
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">reseller.apples@gmail[.]com
				<br>
			</td>
			<td valign="top">Sending account for spear-phishing emails
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">noreply@theanalyser[.]com
				<br>
			</td>
			<td valign="top">From: line on spear-phishing messages
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">idc-team[.]net
				<br>
			</td>
			<td valign="top">May be identified in malware
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">109.236.81[.]86
				<br>
			</td>
			<td valign="top">Used in 2017 intrusion activity
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">91.210.107[.]120
				<br>
			</td>
			<td valign="top">Used in 2017 intrusion activity
				<br>
			</td>
		</tr>
	</tbody>
</table>

**Example spear-phishing email using a link to a file-sharing service account hosting malware:**

![Example spear-phishing email using a link to a file-sharing service account hosting malware:](https://statics.bsafes.com/images/publications/FBI%20PIN%20IRGC%20Associated%20Cyber%20Ops%2009172020-Fig-1.png "Example spear-phishing email using a link to a file-sharing service account hosting malware:")

**Example spear-phishing email using an actor-registered and controlled domain hosting malware:**

![Example spear-phishing email using an actor-registered and controlled domain hosting malware:](https://statics.bsafes.com/images/publications/FBI%20PIN%20IRGC%20Associated%20Cyber%20Ops%2009172020-Fig-2.png "Example spear-phishing email using an actor-registered and controlled domain hosting malware:")

## Recommendations
- Ensure anti-virus and anti-malware software is enabled and signature definitions are updated regularly in a timely manner. Well-maintained anti-virus software may prevent use of commonly deployed attacker tools that are delivered via spear phishing.

- Adopt threat reputation services at the network device, operating system, application, and email service levels. Reputation services can be used to detect or prevent lowreputation email addresses, files, URLs, and IP addresses used in spear-phishing attacks.

- Deploy application control software to limit which applications and executable code can be run by users. Email attachments, and files downloaded via links in emails, often contain executable code. Application control software limits users so they can only execute applications and code allowed by the organization, rendering malicious executables delivered via spear phishing unable to execute.

- Limit the use of administrator privileges. Users who browse the internet, use email, and execute code with administrator privileges make spear phishing much more effective by enabling attackers to move laterally across a network, gain additional accesses, and access highly sensitive information.

- Be suspicious of unsolicited contact via email or social media from any individual you do not know personally.

- Be suspicious of unsolicited or unexpected email or social media messages enticing recipients to open an attached or hosted file.

## Reporting Notice
The FBI encourages recipients of this document to report information concerning suspicious or criminal activity to their local FBI field office or the FBI’s 24/7 Cyber Watch (CyWatch). Field office contacts can be identified at www.fbi.gov/contact-us/fieldoffices. CyWatch can be contacted by phone at (855) 292-3937 or by e-mail at CyWatch@fbi.gov. When available, each report submitted should include the date, time, location, type of activity, number of people, and type of equipment used for the activity, the name of the submitting company or organization, and a designated point of contact. Press inquiries should be directed to the FBI’s National Press Office at npo@ic.fbi.gov or (202) 324-3691.

## Administrative Note
This product is marked TLP:WHITE. Subject to standard copyright rules, TLP:WHITE information may be distributed without restriction.

For comments or questions related to the content or dissemination of this product, contact CyWatch.

<div style="background-color:lightblue; padding:20px" markdown="1">
<h3 style="text-align:center">Your Feedback Regarding this Product is Critical</h3>
Please take a few minutes to send us your feedback. Your feedback
submission may be anonymous. We read each submission carefully, and your feedback will be extremely valuable to the FBI. Feedback should be specific to your experience with our written products to enable the FBI to make quick and continuous improvements to these products. Feedback may be submitted online here: https://www.ic3.gov/PIFSurvey
</div> 
</div>


