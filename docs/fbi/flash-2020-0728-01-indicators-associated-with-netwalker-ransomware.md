---
layout: default
title: . FBI FLASH - Indicators Associated with Netwalker Ransomware  
parent: FBI 
nav_order: 980050399 
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
This is the mobile-friendly web version of the [original article](https://www.aba.com/-/media/documents/cybersecurity-reports/fbi-flash/fbi-flash-indicators-associated-with-netwalker-ransomware-07282020.pdf?rev=9ff4d5e93bda4ae3a5c7b5393bce6729).

<img src="https://statics.bsafes.com/images/publications/FBI%20Flash%20Indicators%20Associated%20with%20Netwalker%20Ransomware%2007282020.png" alt="COVID-19 Phishing Email Indicators" style="display:block; margin:0 auto">

### 28 July 2020 
{: .no_toc }
#### Alert Number
{: .no_toc }
### MI-000130-MW 
{: .no_toc }  

1. TOC
{:toc}

The following information is being provided by the FBI, with no guarantees or warranties, for potential use at the sole discretion of recipients in order to protect against cyber threats. This data is provided to help cyber security professionals and system administrators guard against the persistent malicious actions of cyber actors. This product was coordinated with DHS CISA.

This FLASH has been released TLP:WHITE Subject to standard copyright rules, TLP:WHITE information may be distributed without restriction.

# Indicators Associated with Netwalker Ransomware 

## Summary
As of June 2020, the FBI has received notifications of Netwalker ransomware attacks on U.S. and foreign government organizations, education entities, private companies, and health agencies by unidentified cyber actors. Netwalker became widely recognized in March 2020, after intrusions on an Australian transportation and logistics company and a U.S. public health organization. Cyber actors using Netwalker have since taken advantage of the COVID-19 pandemic to compromise an increasing number of unsuspecting victims.

## Technical Details
Following a successful intrusion, Netwalker encrypts all connected Windows based devices and data, rendering critical files, databases, and applications inaccessible to users. When executed, Netwalker deploys an embedded configuration that includes a ransom note, ransom note file names, and various configuration options.

In March 2020, actors using Netwalker began exploiting COVID-19 fears by luring unsuspecting victims with pandemic related phishing e-mails. Specifically, Netwalker spread through a Visual Basic Scripting (VBS) script attached to COVID19 phishing e-mails that executed the payload once opened.

In April 2020, actors using Netwalker began gaining unauthorized access to victim networks by exploiting unpatched Virtual Private Network (VPN) appliances, vulnerable user interface components in web applications, or weak passwords used for Remote Desktop Protocol connections.

Two of the most common vulnerabilities exploited by actors using Netwalker are Pulse Secure VPN (CVE-2019- 11510) and Telerik UI (CVE-2019-18935). Once an actor has infiltrated a network with Netwalker, a combination of malicious programs may be executed to harvest administrator credentials, steal valuable data, and encrypt user files. In order to encrypt the user files on a victim network, the actors typically launch a malicious PowerShell script embedded with the Netwalker ransomware executable. 

Actors using Netwalker have previously uploaded stolen data to the cloud storage and file sharing service, MEGA.NZ (MEGA), by uploading the data through the MEGA website or by installing the MEGA client application directly on a victim’s computer. In June 2020, actors transitioned from uploading and releasing stolen data on MEGA to uploading the stolen data to another file sharing service: website.dropmefiles.com.

<table cellpadding="0" cellspacing="0">
	<tbody>
		<tr>
			<td colspan="3" style="background-color: rgb(61, 142, 185);" valign="top"><strong>Confirmed Indicators</strong>
				<br>
			</td>
		</tr>
		<tr>
			<td colspan="3" style="background-color: rgb(84, 172, 210);" valign="top">Email Addresses:
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">2hamlampampom@cock.li
				<br>
			</td>
			<td valign="top">galgalgalgalk@tutanota.com
				<br>
			</td>
			<td valign="top">johprohnpo@cock.li
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">cancandecan@tutanota.com
				<br>
			</td>
			<td valign="top">galgalgalgawk@tutanota.com
				<br>
			</td>
			<td valign="top">kavariusing@tutanota.com
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">eeaammzzyy@cock.li
				<br>
			</td>
			<td valign="top">hamlampampom@cock.li
				<br>
			</td>
			<td valign="top">kazkavkovkiz@cock.li
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">eeaammzzyy@tuta.io
				<br>
			</td>
			<td valign="top">hariliuios@tutanota.com
				<br>
			</td>
			<td valign="top">kkeessnnkkaa@cock.li
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">eeeooppaaaxxx@tuta.io
				<br>
			</td>
			<td valign="top">hhaaxxhhaaxx@tuta.io
				<br>
			</td>
			<td valign="top">kkkwwwsvvv@cock.li
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">knoocknoo@cock.li
				<br>
			</td>
			<td valign="top">pabpabtab@tuta.io
				<br>
			</td>
			<td valign="top">sevenoneone@cock.li
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">kokbiglock@cock.li
				<br>
			</td>
			<td valign="top">repairdb@seznam.cz
				<br>
			</td>
			<td valign="top">sevenonone@cock.li
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">kokoklock@cock.li
				<br>
			</td>
			<td valign="top">rrrkkktttaaa@cock.li
				<br>
			</td>
			<td valign="top">
				<br>
				<br>
			</td>
		</tr>
	</tbody>
</table>

<p>
	<br>
</p>

<table cellpadding="0" cellspacing="0">
	<tbody>
		<tr>
			<td colspan="2" style="background-color: rgb(84, 172, 210);" valign="top"><strong>MD5 Hashes:</strong>
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">258ed03a6e4d9012f8102c635a5e3dcd
				<br>
			</td>
			<td valign="top">73de5babf166f28dc81d6c2faa369379
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">3d6203df53fcaa16d71add5f47bdd060
				<br>
			</td>
			<td valign="top">7a1288c7be386c99fad964dbd068964f
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">5b80cbbdcb697c0b8ec26e6cf0ff305c
				<br>
			</td>
			<td valign="top">993b73d6490bc5a7e23e02210b317247
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">27304b246c7d5b4e149124d5f93c5b01
				<br>
			</td>
			<td valign="top">8fbc17d634009cb1ce261b5b3b2f2ecb
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">59881abed688ceba3d67c2ff22076ad8
				<br>
			</td>
			<td valign="top">6a64553da499c1d9a64d97f4de3882f5
				<br>
			</td>
		</tr>
	</tbody>
</table>

<p>
	<br>
</p>

<table cellpadding="0" cellspacing="0">
	<tbody>
		<tr>
			<td style="background-color: rgb(84, 172, 210);" valign="top">SHA-256 Hashes:
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">8f834966a06f34682b78e1644c47ab488b394b80109ddea39fc9a29ed0d56a0c
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">58e923ff158fb5aecd293b7a0e0d305296110b83c6e270786edcc4fea1c8404c
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">8639825230d5504fd8126ed55b2d7aeb72944ffe17e762801aab8d4f8f880160
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">9f9027b5db5c408ee43ef2a7c7dd1aecbdb244ef6b16d9aafb599e8c40368967
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">ad8d379a4431cabd079a1c34add903451e11f06652fe28d3f3edb6c469c43893
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">de04d2402154f676f757cf1380671f396f3fc9f7dbb683d9461edd2718c4e09d
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">8f834966a06f34682b78e1644c47ab488b394b80109ddea39fc9a29ed0d56a0c
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">58e923ff158fb5aecd293b7a0e0d305296110b83c6e270786edcc4fea1c8404c
				<br>
			</td>
		</tr>
	</tbody>
</table>

<p>
	<br>
</p>

<table cellpadding="0" cellspacing="0">
	<tbody>
		<tr>
			<td colspan="2" style="background-color: rgb(84, 172, 210);" valign="top">SHA1 Hashes:
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">655352e00c7e478c3fed38bc6f407982dec3768d
				<br>
			</td>
			<td valign="top">a3bc2a30318f9bd2b51cb57e2022996e7f15c69e
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">6fd314af34409e945504e166eb8cd88127c1070e
				<br>
			</td>
			<td valign="top">e393a9ecf0d0a8babaa5efcc34f10577aff1cad1
				<br>
			</td>
		</tr>
	</tbody>
</table>

<p>
	<br>
</p>

<table cellpadding="0" cellspacing="0">
	<tbody>
		<tr>
			<td colspan="4" style="background-color: rgb(84, 172, 210);" valign="top">Malicious Files and Executables:
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">qeSw.exe
				<br>
			</td>
			<td valign="top">pw.exe
				<br>
			</td>
			<td valign="top">Invoke-Mimikatz.ps1
				<br>
			</td>
			<td valign="top">mimikatzN.exe
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">CORONAVIRUS_COVID-19.vbs
				<br>
			</td>
			<td valign="top">wce.exe
				<br>
			</td>
			<td valign="top">Invoke-mimikittenz.ps1
				<br>
			</td>
			<td valign="top">mimikatz.exe
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">t.exe
				<br>
			</td>
			<td valign="top">pwdump7.exe
				<br>
			</td>
			<td valign="top">dl.exe
				<br>
			</td>
			<td valign="top">rz.ps1
				<br>
			</td>
		</tr>
	</tbody>
</table>

<p>
	<br>
</p>

<table cellpadding="0" cellspacing="0">
	<tbody>
		<tr>
			<td style="background-color: rgb(84, 172, 210);" valign="top">Tor Onion URLs:
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">rnfdsgm6wb6j6su5txkekw4u4y47kp2eatvu7d6xhyn5cs4lt4pdrqqd.onion
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">pb36hu4spl6cyjdfhing7h3pw6dhpk32ifemawkujj4gp33ejzdq3did.onion
				<br>
			</td>
		</tr>
	</tbody>
</table>

## Information Requested
The FBI does not encourage paying a ransom to criminal actors. Paying a ransom may embolden adversaries to target additional organizations, encourage other criminal actors to engage in the distribution of ransomware, and/or may fund illicit activities. Paying the ransom also does not guarantee that a victim’s files will be recovered. However, the FBI understands that when businesses are faced with an inability to function, executives will evaluate all options to protect their shareholders, employees, and customers. Regardless of whether you or your organization have decided to pay the ransom, the FBI urges you to report ransomware incidents to your local field office. Doing so provides investigators with the critical information they need to track ransomware attackers, hold them accountable under U.S. law, and prevent future attacks.

## Recommended Mitigations
- Back-up critical data offline.
- Ensure copies of critical data are in the cloud or on an external hard drive or storage device.
- Secure your back-ups and ensure data is not accessible for modification or deletion from the system where the data resides.
- Install and regularly update anti-virus or anti-malware software on all hosts.
- Only use secure networks and avoid using public Wi-Fi networks. Consider installing and using a VPN.
- Use two-factor authentication with strong passwords.
- Keep computers, devices, and applications patched and up-to-date.

## Reporting Notice
The FBI encourages recipients of this document to report information concerning suspicious or criminal activity to their local FBI field office or the FBI’s 24/7 Cyber Watch (CyWatch). Field office contacts can be identified at www.fbi.gov/contact-us/field. CyWatch can be contacted by phone at (855) 292-3937 or by e-mail at CyWatch@ic.fbi.gov. When available, each report submitted should include the date, time, location, type of activity, number of people, and type of equipment used for the activity, the name of the submitting company or organization, and a designated point of contact. Press inquiries should be directed to the FBI’s National Press Office at npo@ic.fbi.gov or (202) 324-3691.

## Administrative Note
This product is marked TLP:WHITE. Subject to standard copyright rules, TLP:WHITE information may be distributed without restriction.

<div style="background-color:lightblue; padding:20px" markdown="1">
<h3 style="text-align:center">Your Feedback on the Value of this Product Is Critical</h3>
Was this product of value to your organization? Was the content clear and concise? Your comments are very important to us and can be submitted anonymously. Please take a moment to complete the survey at the link below. Feedback should be specific to your experience with our written products to enable the FBI to make quick and continuous improvements to such products. Feedback may be submitted online here: https://www.ic3.gov/PIFSurvey

Please note that this survey is for feedback on content and value only. Reporting of technical information regarding FLASH reports must be submitted through FBI CYWATCH.
</div>
</div>

