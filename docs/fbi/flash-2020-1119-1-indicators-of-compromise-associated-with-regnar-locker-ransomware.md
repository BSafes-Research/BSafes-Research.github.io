---
layout: default
title: . 11/19/2020 - Indicators of Compromise Associated with Ragnar Locker Ransomware  
parent: FBI 
nav_order: 980011299 
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
This is the mobile-friendly web version of the [original article](https://www.aba.com/-/media/documents/cybersecurity-reports/fbi-flash/fbi-flash-indicators-of-compromise-ragnar-locker-ransomware-11192020.pdf?rev=e2d550b4a9224163ba7c93a2b8898228).

<img src="https://statics.bsafes.com/images/publications/FBI-Flash-Indicators-of-Compromise-Ragnar-Locker-Ransomware.png" alt="Indicators of Compromise Associated with Ragnar Locker Ransomware" style="display:block; margin:0 auto">

### 19 NOV 2020
{: .no_toc }
#### Alert Number
{: .no_toc }
### MU-000140-MW
{: .no_toc }  

1. TOC
{:toc}

The following information is being provided by the FBI, with no guarantees or warranties, for potential use at the sole discretion of recipients in order to protect against cyber threats. This data is provided in order to help cyber security professionals and system administrators to guard against the persistent malicious actions of cyber criminals. This FLASH was coordinated with DHS-CISA.

This FLASH has been released TLP:WHITE Subject to standard copyright rules, TLP:WHITE information may be distributed without restriction.

# Indicators of Compromise Associated with Ragnar Locker Ransomware

## Summary
The FBI first observed Ragnar Locker<sup>1</sup> ransomware in April 2020, when unknown actors used it to encrypt a large corporation’s files for an approximately $11 million ransom and threatened to release 10 TB of sensitive company data. Since then, Ragnar Locker has been deployed against an increasing list of victims, including cloud service providers, communication, construction, travel, and enterprise software companies. The FBI is providing details of Ragnar Locker ransomware to assist with understanding the code and identifying the activity. Ragnar Locker actors first obtain access to a victim’s network and perform reconnaissance to locate network resources, backups, or other sensitive files for data exfiltration. In the final stage of the attack, actors manually deploy the ransomware, encrypting the victim’s data.

## Technical Details
The Ragnar Locker ransomware family<sup>2</sup> is frequently changing obfuscation techniques to avoid detection and prevention. The Ragnar Locker ransomware is identified by the extension “.RGNR_<ID>,” where <ID> is a hash of the computer’s NETBIOS name. Furthermore, the actors, identifying themselves as“RAGNAR_LOCKER,” leave a .txt ransom note, with instructions on how to pay the ransom and decrypt the data. Ragnar Locker has used VMProtect, UPX, and custom packing algorithms. Ragnar Locker has been deployed within an attacker’s custom Windows XP virtual machine on a target’s site.

Ragnar Locker uses Windows API GetLocaleInfoW to get the infected machine’s current locale. If the victim’s locale is found to be "Azerbaijani," "Armenian," "Belorussian," "Kazakh," "Kyrgyz," "Moldavian," "Tajik," "Russian," "Turkmen," "Uzbek," "Ukrainian," or "Georgian," the process will terminate.

![Figure 1 _ Code Snippet](https://statics.bsafes.com/images/publications/FBI-Flash-Indicators-of-Compromise-Ragnar-Locker-Ransomware-Fig-1.png)

The ransomware also checks for current infections to prevent multiple encryption transforms of the data, potentially corrupting it. The binary gathers the unique machine GUID, operating system product name, and user name currently running the process. This data is sent through a custom hashing algorithm to generate a unique identifier: <HashedMachineGuid>- <HashedWindowsProductName>-<HashedUser>-<HashedComputerName>- <HashedAllDataTogether>.

The Ragnar Locker ransomware identifies all attached hard drives, whether assigned a drive letter or not, using Windows APIs: CreateFileW, DeviceIoControl, GetLogicalDrives, and SetVolumeMountPointA. The ransomware assigns a drive letter to any volumes not assigned a logical drive letter and makes them accessible. These newly attached volumes are later encrypted during the final stage of the binary.

Ragnar Locker iterates through all running services and terminates services commonly used by managed service providers to remotely administer networks. 

<table cellpadding="0" cellspacing="0">
	<tbody>
		<tr>
			<td colspan="7" style="background-color: rgb(84, 172, 210);" valign="top"><strong>The list of services terminated includes:</strong>
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">vss
				<br>
			</td>
			<td valign="top">sql
				<br>
			</td>
			<td valign="top">memtas
				<br>
			</td>
			<td valign="top">mepocs
				<br>
			</td>
			<td valign="top">sophos
				<br>
			</td>
			<td valign="top">dfs
				<br>
			</td>
			<td valign="top">splashtop
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">veeam
				<br>
			</td>
			<td valign="top">backup
				<br>
			</td>
			<td valign="top">pulseway
				<br>
			</td>
			<td valign="top">logme
				<br>
			</td>
			<td valign="top">ogmein
				<br>
			</td>
			<td valign="top">mysql
				<br>
			</td>
			<td valign="top">connectwise
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
			<td colspan="5" style="background-color: rgb(84, 172, 210);" valign="top"><strong>Ragnar Locker also terminates the following running processes:</strong>
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">sql
				<br>
			</td>
			<td valign="top">mysql
				<br>
			</td>
			<td valign="top">veeam
				<br>
			</td>
			<td valign="top">oracle
				<br>
			</td>
			<td valign="top">ocssd
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">dbsnmp
				<br>
			</td>
			<td valign="top">synctime
				<br>
			</td>
			<td valign="top">agntsvc
				<br>
			</td>
			<td valign="top">isqlplussvc
				<br>
			</td>
			<td valign="top">xfssvccon
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">mydesktopservice
				<br>
			</td>
			<td valign="top">ocautoupds
				<br>
			</td>
			<td valign="top">encsvc
				<br>
			</td>
			<td valign="top">firefox
				<br>
			</td>
			<td valign="top">tbirdconfig
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">mydesktopqos
				<br>
			</td>
			<td valign="top">ocomm
				<br>
			</td>
			<td valign="top">dbeng50
				<br>
			</td>
			<td valign="top">sqbcoreservice
				<br>
			</td>
			<td valign="top">excel
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">infopath
				<br>
			</td>
			<td valign="top">msaccess
				<br>
			</td>
			<td valign="top">mspub
				<br>
			</td>
			<td valign="top">onenote
				<br>
			</td>
			<td valign="top">outlook
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">powerpnt
				<br>
			</td>
			<td valign="top">steam
				<br>
			</td>
			<td valign="top">thebat
				<br>
			</td>
			<td valign="top">thunderbird
				<br>
			</td>
			<td valign="top">visio
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">winword
				<br>
			</td>
			<td valign="top">wordpad
				<br>
			</td>
			<td valign="top">EduLink2SIMS
				<br>
			</td>
			<td valign="top">bengine
				<br>
			</td>
			<td valign="top">benetns
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">beserver
				<br>
			</td>
			<td valign="top">pvlsvr
				<br>
			</td>
			<td valign="top">beremote
				<br>
			</td>
			<td valign="top">VxLockdownServer
				<br>
			</td>
			<td valign="top">postgres
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">dfssvc.exe
				<br>
			</td>
			<td valign="top">SavService.exe
				<br>
			</td>
			<td valign="top">OWSTIMER
				<br>
			</td>
			<td valign="top">SAVAdminService
				<br>
			</td>
			<td valign="top">wsstracing
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">Fdhost
				<br>
			</td>
			<td valign="top">dfsrs.exe
				<br>
			</td>
			<td valign="top">sophos
				<br>
			</td>
			<td valign="top">WSSADMIN
				<br>
			</td>
			<td valign="top">swc_service.exe
				<br>
			</td>
		</tr>
	</tbody>
</table>


The malware then attempts to silently delete all Volume Shadow Copies preventing user recovery of encrypted files, using two different methods:
- \> vssadmin delete shadows /all /quiet
- \> wmic.exe.shadowcopy.delete

Lastly, Ragnar Locker encrypts all available files of interest. Instead of choosing which files to encrypt, Ragnar Locker chooses which folders it will not encrypt. Taking this approach allows the computer to continue to operate “normally” while the malware encrypts files with known and unknown extensions containing data of value to the victim. For example, if the logical drive being processed is the C: drive, the malware does not encrypt files in the following folders:

- Windows
- Windows.old
- Tor browser
- Internet Explorer
- Google
- Opera
- Mozilla
- Mozilla Firefox
- $Recycle.Bin
- ProgramData
- Opera Software


Also, when iterating through files, the malware does not encrypt files with the following extensions:
- .db
- .sys
- .dll
- lnk
- .msi
- .drv
- exe

## Recommended Mitigations

- Back-up critical data offline.
- Ensure copies of critical data are in the cloud or on an external hard drive or storage device. This information should not be accessible from the compromised network.
- Secure your back-ups and ensure data is not accessible for modification or deletion from the system where the data resides.
- Install and regularly update anti-virus or anti-malware software on all hosts.
- Only use secure networks and avoid using public Wi-Fi networks. Consider installing and using a VPN.
- Use multi-factor authentication with strong passwords.
- Keep computers, devices, and applications patched and up-to-date.

## Reporting Notice
The FBI encourages recipients of this document to report information concerning suspicious or criminal activity to their local FBI field office or the FBI’s 24/7 Cyber Watch (CyWatch). Field office contacts can be identified at CyWatch can be contacted by phone at (855) 292-3937 or by email at CyWatch@fbi.gov. When available, each report submitted should include the date, time, location, type of activity, number of people, and type of equipment used for the activity, the name of the submitting company or organization, and a designated point of contact. Press inquiries should be directed to the FBI’s national Press Office at npo@fbi.gov or (202) 324 3691.

## Administrative Note
This product is marked TLP:WHITE. Subject to standard copyright rules, TLP:WHITE information may be distributed without restriction.

For comments or questions related to the content or dissemination of this product, contact CyWatch.

<div style="background-color:lightblue; padding:20px" markdown="1">
<h3 style="text-align:center">Your Feedback on the Value of this Product Is Critical</h3>
Was this product of value to your organization? Was the content clear and concise? Your comments are very important to us and can be submitted anonymously. Please take a moment to complete the survey at the link below. Feedback should be specific to your experience with our written products to enable the FBI to make quick and continuous improvements to such products. Feedback may be submitted online here: https://www.ic3.gov/PIFSurvey

Please note that this survey is for feedback on content and value only. Reporting of technical information regarding FLASH reports must be submitted through FBI CYWATCH.
</div>
</div>
