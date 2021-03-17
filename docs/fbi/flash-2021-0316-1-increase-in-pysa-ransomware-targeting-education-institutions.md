---
layout: default
title: . 3/16/2021 - Increase in PYSA Ransomware Targeting Education Institutions 
parent: FBI 
nav_order: 979091599 
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
This is the mobile-friendly web version of the [original article](https://assets.documentcloud.org/documents/20514564/pysa-ransomware-bc.pdf).

<img src="https://statics.bsafes.com/images/publications/pysa-ransomware-bc.png" alt="Increase in PYSA Ransomware Targeting Education Institutions" style="display:block; margin:0 auto">

### 16 MAR 2021
{: .no_toc }
#### Alert Number
{: .no_toc }
### CP-000142-MW 
{: .no_toc }  

1. TOC
{:toc}

The following information is being provided by the FBI, with no guarantees or warranties, for potential use at the sole discretion of recipients in order to protect against cyber threats. This data is provided to help cyber security professionals and system administrators guard against the persistent malicious actions of cyber actors. This FLASH was coordinated with DHS-CISA.

This FLASH has been released TLP:WHITE Subject to standard copyright rules, TLP:WHITE information may be distributed without restriction.

# Increase in PYSA Ransomware Targeting Education Institutions 

## Summary
FBI reporting has indicated a recent increase in PYSA ransomware targeting education institutions in 12 US states and the United Kingdom. PYSA, also known as Mespinoza, is a malware capable of exfiltrating data and encrypting users’ critical files and data stored on their systems. The unidentified cyber actors have specifically targeted higher education, K-12 schools, and seminaries. These actors use PYSA to exfiltrate data from victims prior to encrypting victim’s systems to use as leverage in eliciting ransom payments.

## Technical Details
Since March 2020, the FBI has become aware of PYSA ransomware attacks against US and foreign government entities, educational institutions, private companies, and the healthcare sector by unidentified cyber actors. PYSA typically gains unauthorized access to victim networks by compromising Remote Desktop Protocol (RDP) credentials and/or through phishing emails. The cyber actors use Advanced Port Scanner and Advanced IP Scanner<sup>1</sup> to conduct network reconnaissance, and proceed to install open source tools, such as PowerShell Empire<sup>2</sup>, Koadic<sup>3</sup>, and Mimikatz<sup>4</sup>. The cyber actors execute commands to deactivate antivirus capabilities on the victim network prior to deploying the ransomware.

The cyber actors then exfiltrate files from the victim’s network, sometimes using the free open- source tool WinSCP<sup>5</sup>, and proceed to encrypt all connected Windows and/or Linux devices and data, rendering critical files, databases, virtual machines, backups, and applications inaccessible to users. In previous incidents, cyber actors exfiltrated employment records that contained personally identifiable information (PII), payroll tax information, and other data that could be used to extort victims to pay a ransom.

Upon malware execution, a detailed ransom message is generated and displayed on the victim’s login or lock screen. The ransom message contains information on how to contact the actors via email, displays frequently asked questions (FAQs), and offers to decrypt the affected files. If the ransom is not met, the actors warn that the information will be uploaded and monetized on the darknet. Additionally, the malware is dropped in a user folder, such as C:\Users\%username%\Downloads\. Observed instances of the malware showed a filename of svchost.exe, which is most likely an effort by the cyber actors to trick victims and disguise the ransomware as the generic Windows host process name. In some instances, the actors removed the malicious files after deployment, resulting in victims not finding any malicious files on their systems.

***
<sup>1</sup> They cyber actors used the Advanced Port Scanner and Advanced IP Scanner by FAMATECH, which is an open source tool that allows users to find open network computers and discover the versions of programs on those ports.
{: .fs-2}
<sup>2</sup> PowerShell Empire is a post exploitation toolkit that provides the ability to run PowerShell agents without needing powershell.exe, as well as provide modules ranging from keyloggers to Mimikatz, and adaptable communication to avoid network detection.
{: .fs-2}
<sup>3</sup> Koadic is an open source penetration toolkit that has several options for staging payloads and creating implants.
{: .fs-2}
<sup>4</sup> Mimikatz is an open source post exploitation toolkit that pulls passwords from memory, as well as hashes, and other authentication credentials.
{: .fs-2}
<sup>5</sup> WinSCP is an open source tool that provides secure file transfer between local and remote computer systems.
{: .fs-2}
***

The cyber actors have uploaded stolen data to MEGA.NZ, a cloud storage and file sharing service, by uploading the data through the MEGA website or by installing the MEGA client application directly on a victim’s computer. However, in the past actors have used other methods of exfiltrating data that leaves less evidence of what was stolen.

## Indicators
The following are characteristics of the compromise:
<table style="width: 100%;">
	<tbody>
		<tr>
			<td colspan="3" style="width: 99.8182%; background-color: rgb(84, 172, 210);"><strong>Indicators<br></strong></td>
		</tr>
		<tr>
			<td style="width: 50.0000%;">File Extension of encrypted files:
				<br>
			</td>
			<td colspan="2" style="width: 50.0000%;">.pysa
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 50.0000%;">Observed malware filename:
				<br>
			</td>
			<td colspan="2" style="width: 50.0000%;">\Users\%username%\Downloads\svchost.exe
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 50.0000%;">SHA1 Hashes<sup>6</sup>:
				<br>
			</td>
			<td style="width: 34.6995%;">Unknown
				<br>
			</td>
			<td style="width: 34.6995%;">07cb2a3fe86414b054e2b002f283935bb0cb993c
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 50.0000%;">
				<br>
			</td>
			<td style="width: 34.6084%;">svchost.exe
				<br>
			</td>
			<td style="width: 34.6084%;">52b2fc13ec0dbf8a0250c066cd3486b635a27827
				<br>
			</td>
		</tr>
		<tr>
			<td>
				<br>
			</td>
			<td>svchost.exe
				<br>
			</td>
			<td>728CB56F98EDBADA697FE66FBF7D367215271F10
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 50.0000%;">
				<br>
			</td>
			<td style="width: 34.6084%;">17535.pyz
				<br>
			</td>
			<td style="width: 34.6084%;">c74378a93806628b62276195f9657487310a96fd
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 50.0000%;">
				<br>
			</td>
			<td style="width: 34.6084%;">Step2.ps1
				<br>
			</td>
			<td style="width: 34.6084%;">24c592ad9b21df380cb4f39a85d4375b6a8a6175
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 50.0000%;">
				<br>
			</td>
			<td style="width: 34.6084%;">sshs.exe or explorer.exe
				<br>
			</td>
			<td style="width: 34.6084%;">f2dda8720a5549d4666269b8ca9d629ea8b76bdf
				<br>
				<br>
			</td>
		</tr>
		<tr>
			<td>Tor URLs:
				<br>
			</td>
			<td colspan="2" style="width: 85.1138%;">pysa2bitc5ldeyfak4seeruqymqs4sj5wt5qkcq7aoyg4h2acqieywad.onion
				<br>na47pldl5eoqxt42.onion
				<br>
			</td>
		</tr>
	</tbody>
</table>

The following domains are associated with this activity:
<table>
	<tbody>
		<tr>
			<td colspan="2" rowspan="1"><strong>Domains Found in Ransom Notes</strong>
				<br>
			</td>
		</tr>
		<tr>
			<td>ced_cririele93@protonmail.com
				<br>
			</td>
			<td>veronabello@onionmail.org
				<br>
			</td>
		</tr>
		<tr>
			<td>irvingalfie@protonmail.com
				<br>
			</td>
			<td>giuliacabello@onionmail.org
				<br>
			</td>
		</tr>
		<tr>
			<td>gustaf.wixon@protonmail.com
				<br>
			</td>
			<td>avitacabrera@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td>ralfgriffin@protonmail.com
				<br>
			</td>
			<td>domenikuvoker@protonmail.com
				<br>
			</td>
		</tr>
	</tbody>
</table>

<table style="margin-right: calc(4%); width: 96%;">
	<tbody>
		<tr>
			<td style="width: 39.2248%;">korgy.torky@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">mespinoza980@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">astion11@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">&nbsp;ellershaw.kiley@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">Bfgkwethnsb@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">jonivaeng@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">Logan_A_Gray@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">alanson_street8@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">rafaeldari@onionmail.org
				<br>
			</td>
			<td style="width: 60.6202%;">&nbsp;raingemaximo@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">Abelzackary@onionmail.org
				<br>
			</td>
			<td style="width: 60.6202%;">mcpherson.artair@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">Elliotstaarss1@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">lambchristoffer@protonmail.com
				<br>&nbsp;</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">TimWestbrook@onionmail.org
				<br>
			</td>
			<td style="width: 60.6202%;">gareth.mckie3l@protonmail.com
				<br>&nbsp;</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">PaulDade@onionmail.org
				<br>
			</td>
			<td style="width: 60.6202%;">rohrbacherlucho@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">CarmenWashingtonGton@portonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">&nbsp;aireyeric@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">cozmo.storton@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">noblecocking@protonmail.com
				<br>&nbsp;</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">karim.abson@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">presleybarry63@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">chettle.willem@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">&nbsp;duncan_cautherey@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">dalliss.prout96@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">shdujdsh@protonmail.com
				<br>&nbsp;</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">karkeck.arch@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">ihdtwesfs@portonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">keefe.mcmeckan@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">&nbsp;williamjohnson1963@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">keepupchell@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">casualstroons@portonmail.com
				<br>&nbsp;</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">gabriel8970@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">izak.pollington@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">masonhoyt@onionmail.org
				<br>
			</td>
			<td style="width: 60.6202%;">&nbsp;t_trstram@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">merry.lane@mailfence.com
				<br>
			</td>
			<td style="width: 60.6202%;">willmottlem01@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">Jamesy.kettlewell@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">BettyRacine@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">platt.lucais@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">Ohsgsuywb@protonmail.com
				<br>&nbsp;</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">jarret.wharram@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">Lojdgseywu@protonmail.copm
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">hewitt_rogers@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">Johnbeamvv@protonmail.com
				<br>&nbsp;
				<a href="mailto:%3C/td%3E%3C/tr%3E%3Ctr%3E%3Ctd%3E%3Cp%3E%3Cspan%3Ethorvald_beattie@protonmail.com%3C/span%3E%3C/p%3E%3C/td%3E%3Ctd%3E%3Cp%3E%3Cspan%3Erewhgsch@protonmail.com%3C/span%3E%3C/p%3E%3C/td%3E%3C/tr%3E%3Ctr%3E%3Ctd%3E%3Cp%3E%3Cspan%3Ewarden_riddoch@protonmail.com%3C/span%3E%3C/p%3E%3C/td%3E%3Ctd%3E%3Cp%3E%3Cspan%3Elhdbeysdq@protonmail.com%3C/span%3E%3C/p%3E%3C/td%3E%3C/tr%3E%3Ctr%3E%3Ctd%3E%3Cp%3E%3Cspan%3Ecowland_lothaire@protonmail.com%3C/span%3E%3C/p%3E%3C/td%3E%3Ctd%3E%3Cp%3E%3Cspan%3Emario1@mailfence.com%3C/span%3E%3C/p%3E%3C/td%3E%3C/tr%3E%3Ctr%3E%3Ctd%3E%3Cp%3E%3Cspan%3ENickola_men@protonmail.com%3C/span%3E%3C/p%3E%3C/td%3E%3Ctd%3E%3C/td%3E%3C/tr%3E%3C/tbody%3E%3C/table%3E"></a>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">thorvald_beattie@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">rewhgsch@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">warden_riddoch@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">lhdbeysdq@protonmail.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">cowland_lothaire@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">mario1@mailfence.com
				<br>
			</td>
		</tr>
		<tr>
			<td style="width: 39.2248%;">Nickola_men@protonmail.com
				<br>
			</td>
			<td style="width: 60.6202%;">
				<br>
			</td>
		</tr>
	</tbody>
</table>

***
<sup>6</sup> As the cyber actors continue to develop the malicious codes, the filenames and SHA1 hashes will change and evolve.
{: .fs-2}
***

## Information Requested:
The FBI does not encourage paying ransoms. Payment does not guarantee files will be recovered. It may also embolden adversaries to target additional organizations, encourage other criminal actors to engage in the distribution of ransomware, and/or fund illicit activities. However, the FBI understands that when victims are faced with an inability to function, all options are evaluated to protect shareholders, employees and customers. Regardless of whether your organization decided to pay the ransom, the FBI urges you to report ransomware incidents to your local FBI field office or the FBI’s Internet Crime Complaint Center (IC3) (https://ic3.gov). Doing so provides the FBI with critical information needed to prevent future attacks by identifying and tracking ransomware attackers and holding them accountable under U.S. law.

Recommended Mitigations
- Regularly back up data, air gap, and password protect backup copies offline. Ensure copies of critical data are not accessible for modification or deletion from the system where the data resides.
- Implement network segmentation.
- Implement a recovery plan to maintain and retain multiple copies of sensitive or proprietary
data and servers in a physically separate, segmented, secure location (i.e., hard drive, storage
device, the cloud).
- Install updates/patch operating systems, software, and firmware as soon as they are
released.
- Use multifactor authentication where possible.
- Regularly, change passwords to network systems and accounts, and avoid reusing passwords
for different accounts. Implement the shortest acceptable timeframe for password changes.
- Disable unused remote access/RDP ports and monitor remote access/RDP logs.
- Audit user accounts with administrative privileges and configure access controls with least
privilege in mind.
- Install and regularly update anti-virus and anti-malware software on all hosts.
- Only use secure networks and avoid using public Wi-Fi networks. Consider installing and using
a VPN.
- Consider adding an email banner to messages coming from outside your organizations.
- Disable hyperlinks in received emails.
- Focus on awareness and training. Provide users with training on information security principles and techniques as well as overall emerging cybersecurity risks and vulnerabilities (i.e., ransomware and phishing scams).

## Administrative Note
This product is marked TLP:WHITE. Subject to standard copyright rules, TLP:WHITE information may be distributed without restriction.

For comments or questions related to the content or dissemination of this product, contact CyWatch.

<div style="background-color:lightblue; padding:20px" markdown="1">
<h3 style="text-align:center">Your Feedback on the Value of this Product Is Critical</h3>
Was this product of value to your organization? Was the content clear and concise? Your comments are very important to us and can be submitted anonymously. Please take a moment to complete the survey at the link below. Feedback should be specific to your experience with our written products to enable the FBI to make quick and continuous improvements to such products. Feedback may be submitted online here: https://www.ic3.gov/PIFSurvey

Please note that this survey is for feedback on content and value only. Reporting of technical information regarding FLASH reports must be submitted through FBI CYWATCH.
</div>
</div>
