# ATT&CK Report and IR

<h3>Scenario</h3>
<br>
I’m a cybersecurity analyst at a large SOC. We are a small 100–200 person company with an on-prem active directory infrastructure. (We are 100% on-prem, no 
cloud infrastructure in our environment.) All employees are assigned a Windows 10 Laptop 
which is domain joined by our IT department. We also have a plethora of Linux Servers hosting 
our web infrastructure.

<br>

Let’s talk about security products. Endpoint monitoring is in a rough state at the moment. We 
are currently checking out several vendors for the best price and security coverage. The 
Security engineers on the team are not remarkably familiar with Endpoint Policy configurations. 
They will need training for file integrity and process monitoring, so we need a user-friendly EDR 
(Endpoint Detection and Response) product with extensive training to get secure as fast as 
possible. We also understand that most Endpoint products allow the creation of custom-made 
detections. This is something we do not currently have and would love to build our own library 
of detections eventually. As for Network security, we are very well versed as we need to ensure 
that our web traffic is secure. We have several security controls for network protection such as 
web proxies, web content filters, and NextGen Firewalls which have excellent policy 
configurations that already have shown to detect and prevent malicious traffic with a low false 
positive rate. We currently utilize Splunk as our log aggregation and correlation engine for 
network events, and we plan to implement EDR products once we have decided which ones to 
go with. 
Our IT team is new with not a whole lot of security experience. They are familiar with Windows 
infrastructure but may need your help with access control settings so we can ensure that users 
have least privileged access. 
We are happy to have you! Now please, secure our company!

<br>

<h3>Goals & Objectives</h3>
<br>
Analyse the situation using the ATT&CK Calculator tool (https://top-attack-techniques.mitre-engenuity.org/calculator) and create a report to start building a response, building trust and improving security practices within the company.
<br>
<br/>

<br>
<h3>Results</h3>
<br>

I'll address the operating systems. I will check Windows and Linux as those are the primary devices in the organisation. Next, I needed to address the Detection Analytics portion. I checked Splunk, CAR, and Sigma as I want the techniques that are displayed to be in at least one of the three public repositories for our detection library.

Now that the filters are in place, I will address the monitoring components to match our environment. Network Monitoring is under control, so we are safe to put that component as high. This will weigh any network related techniques much lower, so we can focus on the tactics that are more important to us. For Cloud Monitoring, I will select high. This is because it was expressed that this is an on-prem environment, and we want all cloud related techniques weighted lowest, so we do not waste time on unnecessary techniques in accordance with our environment. Lastly, I will keep hardware at none as the documentation didn’t mention this aspect. 

<br>Now that everything is configured, let’s go ahead and generate results to see what techniques we are presented with.

<br>
Breakdown of results

<br>

<img src="assets/MITRE Calculator.png" height="80%" width="80%" alt="ifconfig command"/>
<br />

<br/>
<img src="assets/MITRE Calculator 2.png" height="80%" width="80%" alt="ifconfig command"/>
<br />

<br>
<h3>Review</h3>
<br>
We discovered 10 techniques that have high interest. With the weighting system displaying to us the most actionable and prevalent to our needs, we have an ezcellent starting point for technique education, mitigations, and detections for our environment.
<br>
While looking at these results, we may want some more specific techniques applicable to Access Control and Training for phishing as mentioned in the goals of the project. While keeping the same filters in place, we can add all the Access Control (AC) categories in the NIST 800-53 Controls as these deal with Access Controls and add in all the 14’s for CIS security Controls as these deal with Security Awareness and Skills Training. 
<br>
Now that you have applicable techniques to investigate, you may want to review your security control configurations and see if you have defenses against them. We could now further the respond by using a Breach and Attack Simulation tool such as AttackIQ, or utilize a red team to carry out these techniques in the environment to see if the proper protections are in place. Based on your findings after testing, we can build a remediation plan for techniques that were not prevented or alerted on so we can catch these techniques at our next test, or incident.


Hope you enjoyed the walkthrough of the project, with the idea coming from the brilliant Attack IQ!





