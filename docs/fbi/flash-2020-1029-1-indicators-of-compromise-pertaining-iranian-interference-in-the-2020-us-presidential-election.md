---
layout: default
title: . FBI FLASH - Indicators of Compromise Pertaining to Iranian Interference in the 2020 US Presidential Election  
parent: FBI 
nav_order: 980020299 
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
This is the mobile-friendly web version of the [original article](https://www.aba.com/-/media/documents/cybersecurity-reports/fbi-flash/fbi-flash-indicators-of-compromise-iranian-interference-10292020.pdf?rev=95f070ca93eb48dcac192ccbe82498de).

<img src="https://statics.bsafes.com/images/publications/FBI%20Flash%20Indicators%20of%20Compromise%20Iranian%20Interference%2010292020.png" alt="Indicators of Compromise Pertaining to Iranian Interference in the 2020 US Presidential Election" style="display:block; margin:0 auto">

### 29 OCT 2020
{: .no_toc }
#### Alert Number
{: .no_toc }
### ME-000138-TT 
{: .no_toc }  

1. TOC
{:toc}

The following information is being provided by the FBI, with no guarantees or warranties, for potential use at the sole discretion of recipients in order to protect against cyber threats. This data is provided in order to help cyber security professionals and system administrators to guard against the persistent malicious actions of cyber criminals. This FLASH was coordinated with DHS/CISA.

This FLASH has been released TLP:WHITE : Subject to standard copyright rules, TLP:WHITE information may be distributed without restriction.

# Indicators of Compromise Pertaining to Iranian Interference in the 2020 US Presidential Election
{: .no_toc }

## Summary
On 22 October 2020, the Cybersecurity and Infrastructure Security Agency (CISA) and the Federal Bureau of Investigation (FBI) published a joint Cybersecurity Advisory (Alert AA20-296B) warning that Iranian advanced persistent threat (APT) actors are likely intent on influencing and interfering with the US elections to sow discord among voters and undermine public confidence in the US electoral process. APT actors are creating fictitious media sites and spoofing legitimate media sites to spread anti-American propaganda and misinformation about voter suppression. 

The Cybersecurity Advisory followed a joint press conference from the Director of National Intelligence (DNI) and FBI Director on election security, alerting the American public that Iran had taken specific actions to influence public opinion relating to the 2020 US Presidential Election. 

The FBI is now providing a list of indicators of compromise (IOCs) pertaining to a threat group, assessed to be located in Iran, conducting operations aimed at influencing and interfering in the 2020 US Presidential Election.

## Technical Details
The FBI is providing the below list of identified IP addresses previously used as part of an Iran-based campaign to conduct operations aimed at impacting the 2020 US Presidential Election, to include voter intimidation emails and dissemination of US election-related propaganda. The FBI has high confidence these IP addresses were used by the Iranian group on the corresponding dates. Please note many of these IP addresses likely correspond to Virtual Private Network (VPN) services which can be used by individuals all over the world. While this creates the potential for false positives, any activity on the below would likely warrant further investigation.

This group has been linked to efforts to disseminate a propaganda video concerning voter fraud and hacking of US voter information. The FBI advises this video is almost certainly intended to make US voter information and the voting process appear insecure and susceptible to fraud. The FBI advises that certain demonstrational activity in the video [e.g., a purported Structured Query Language (SQL) injection to obtain US voter information] may have been fabricated by the actors for psychological effect.

The video shows actors using the SQLmap tool. While the video alone does not necessarily validate whether the actors successfully conducted a SQL injection against US election infrastructure and/or obtained voter information, it should be assumed that this group is familiar with traditional TTPs such as SQL injection and other exploitation methods referenced in AA20-296B. While there is reason to doubt the veracity of the activity portrayed in the video, the FBI advises this group is likely capable of exploiting US Web sites with common vulnerabilities.

The below IOC list includes several Class C ranges (e.g., 212.102.45.X). This is based on the expectation that the group may have used, or may use in the future, IPs in those ranges based on known VPN service usage. Many VPN service IPs linked to the group are from the NordVPN service, and these IPs may not necessarily correspond to VPN services via IP address lookup services. The VPN service IPs may correspond to providers such as:

- Provider name variants including “CDN77”
- Provider name variants including “HQSERV”
- Provider name variants including “M247”

<table cellpadding="0" cellspacing="0">
	<tbody>
		<tr>
			<td valign="top"><strong>IP address</strong>
				<br>
			</td>
			<td valign="top"><strong>Timeframe</strong>
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">93.119.208.86
				<br>
			</td>
			<td valign="top">13 October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">92.223.89.X (range)
				<br>
			</td>
			<td valign="top">August - September 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">92.223.89.224
				<br>
			</td>
			<td valign="top">12 September 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">92.223.89.212
				<br>
			</td>
			<td valign="top">6 September 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">88.202.178.104
				<br>
			</td>
			<td valign="top">20 October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">70.32.0.107
				<br>
			</td>
			<td valign="top">21 October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">64.44.81.36
				<br>
			</td>
			<td valign="top">12 September 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">45.131.211.246
				<br>
			</td>
			<td valign="top">21 October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">37.235.103.27
				<br>
			</td>
			<td valign="top">16 October 2020 &ndash;&nbsp;
				<br>17 October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">212.102.45.X (range)
				<br>
			</td>
			<td valign="top">October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">212.102.45.23
				<br>
			</td>
			<td valign="top">21 October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">212.102.45.13
				<br>
			</td>
			<td valign="top">12 October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">185.191.207.X (range)
				<br>
			</td>
			<td valign="top">February - September 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">185.191.207.164
				<br>
			</td>
			<td valign="top">19 September 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">184.170.241.13
				<br>
			</td>
			<td valign="top">17 October 2020 &ndash;&nbsp;
				<br>19 October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">156.46.54.X (range)
				<br>
			</td>
			<td valign="top">October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">156.146.55.X (range)
				<br>
			</td>
			<td valign="top">October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">156.146.55.195
				<br>
			</td>
			<td valign="top">15 October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">156.146.54.X (range)
				<br>
			</td>
			<td valign="top">October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">156.146.54.58
				<br>
			</td>
			<td valign="top">20 October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">156.146.54.45
				<br>
			</td>
			<td valign="top">18 October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top"><strong>IP address</strong>
				<br>
			</td>
			<td valign="top"><strong>Timeframe</strong>
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">154.3.251.56
				<br>
			</td>
			<td valign="top">16 October 2020 &ndash;&nbsp;
				<br>21 October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">145.239.110.112
				<br>
			</td>
			<td valign="top">20 October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">104.237.232.153
				<br>
			</td>
			<td valign="top">13 October 2020 &ndash;&nbsp;
				<br>19 October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">103.205.140.X (range)
				<br>
			</td>
			<td valign="top">October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">185.183.32.177
				<br>
			</td>
			<td valign="top">October 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">92.223.89.191
				<br>
			</td>
			<td valign="top">19 August 2020 &ndash;&nbsp;
				<br>25 August 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">92.223.89.187
				<br>
			</td>
			<td valign="top">26 August 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">92.223.89.172
				<br>
			</td>
			<td valign="top">26 August 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">212.102.45.63
				<br>
			</td>
			<td valign="top">24 August 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">185.191.207.179
				<br>
			</td>
			<td valign="top">29 July 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">128.90.56.147
				<br>
			</td>
			<td valign="top">23 June 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">104.140.54.91
				<br>
			</td>
			<td valign="top">23 August 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">91.239.206.181
				<br>
			</td>
			<td valign="top">23 April 2019
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">91.223.106.201
				<br>
			</td>
			<td valign="top">10 March 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">91.223.106.148
				<br>
			</td>
			<td valign="top">22 February 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">89.165.43.244
				<br>
			</td>
			<td valign="top">24 February 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">5.160.253.152
				<br>
			</td>
			<td valign="top">24 February 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">46.45.138.100
				<br>
			</td>
			<td valign="top">3 May 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">185.191.207.36
				<br>
			</td>
			<td valign="top">17 September 2019
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">185.191.207.184
				<br>
			</td>
			<td valign="top">18 February 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">176.53.23.252
				<br>
			</td>
			<td valign="top">31 May 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top"><strong>IP address</strong>
				<br>
			</td>
			<td valign="top"><strong>Timeframe</strong>
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">103.205.140.30
				<br>
			</td>
			<td valign="top">11 March 2020
				<br>
			</td>
		</tr>
		<tr>
			<td valign="top">103.205.140.177
				<br>
			</td>
			<td valign="top">10 March 2020
				<br>
			</td>
		</tr>
	</tbody>
</table>



## Best Practices for Network Security and Defense:
- Employ regular updates to applications and the host operating system to ensure protection against known vulnerabilities.
- Establish, and backup offline, a "known good" version of the relevant server and a regular changemanagement policy to enable monitoring for alterations to servable content with a file integrity system.
- Employ user input validation to restrict local and remote file inclusion vulnerabilities.
- Implement a least-privileges policy on the Webserver to:
 - Reduce adversaries’ ability to escalate privileges or pivot laterally to other hosts.
 - Control creation and execution of files in particular directories.
- If not already present, consider deploying a demilitarized zone (DMZ) between the Web-facing systems and corporate network. Limiting the interaction and logging traffic between the two provides a method to identify possible malicious activity.
- Ensure a secure configuration of Webservers. All unnecessary services and ports should be disabled or blocked. All necessary services and ports should be restricted where feasible. This can include whitelisting or blocking external access to administration panels and not using default login credentials.
- Use a reverse proxy or alternative service to restrict accessible URL paths to known legitimate ones.
- Conduct regular system and application vulnerability scans to establish areas of risk. While this method does not protect against zero day attacks, it will highlight possible areas of concern
- Deploy a Web application firewall and conduct regular virus signature checks, application fuzzing, code reviews, and server network analysis.

## Reporting Notice
The FBI encourages recipients of this document to report information concerning suspicious or criminal activity to their local FBI field office or the FBI’s 24/7 Cyber Watch (CyWatch). Field office contacts can be identified at www.fbi.gov/contact-us/field. CyWatch can be contacted by phone at (855) 292-3937 or by email at CyWatch@ic.fbi.gov. When available, each report submitted should include the date, time, location, type of activity, number of people, and type of equipment used for the activity, the name of the submitting company or organization, and a designated point of contact. Press inquiries should be directed to the FBI’s National Press Office at npo@ic.fbi.gov or (202) 324-3691.

## Administrative Note
This product is marked TLP:WHITE. Subject to standard copyright rules, TLP:WHITE information may be distributed without restriction.

For comments or questions related to the content or dissemination of this product, contact CyWatch.

<div style="background-color:lightblue; padding:20px" markdown="1">
<h3 style="text-align:center">Your Feedback on the Value of this Product Is Critical</h3>
Was this product of value to your organization? Was the content clear and concise? Your comments are very important to us and can be submitted anonymously. Please take a moment to complete the survey at the link below. Feedback should be specific to your experience with our written products to enable the FBI to make quick and continuous improvements to such products. Feedback may be submitted online here: https://www.ic3.gov/PIFSurvey

Please note that this survey is for feedback on content and value only. Reporting of technical information regarding FLASH reports must be submitted through FBI CYWATCH.
</div>
</div>

