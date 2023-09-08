# Analyzing-Network-Attacks-Incident-Report
<h1>Description</h1>
I delved into a scenario involving a customer of a company who encounters a security issue while trying to access the company's website. My initial task was to pinpoint the likely cause of the service disruption. Following that, I elucidated the details of the attack, including how it transpired and the adverse effects it had on the website.
I have gained insights into various common network attacks, learning their names, execution methods, and the characteristics they exhibit from a target's perspective. This comprehension of the impact of these attacks on a network will be invaluable in troubleshooting problems within a organization's network and implementing measures to minimize harm and safeguard against future attacks.

<h2>Scenario</h2>
Review the scenario below.

You work as a security analyst for a travel agency that advertises sales and promotions on the company’s website. The employees of the company regularly access the company’s sales webpage to search for vacation packages their customers might like.

One afternoon, you receive an automated alert from your monitoring system indicating a problem with the web server. You attempt to visit the company’s website, but you receive a connection timeout error message in your browser.

You use a packet sniffer to capture data packets in transit to and from the web server. You notice a large number of TCP SYN requests coming from an unfamiliar IP address. The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. You suspect the server is under attack by a malicious actor.

You take the server offline temporarily so that the machine can recover and return to a normal operating status. You also configure the company’s firewall to block the IP address that was sending the abnormal number of SYN requests. You know that your IP blocking solution won’t last long, as an attacker can spoof other IP addresses to get around this block. 

You need to alert your manager about this problem quickly and discuss the next steps to stop this attacker and prevent this problem from happening again. You will need to be prepared to tell your boss about the type of attack you discovered and how it affected the web server and employees.

- <a> Required Documents from Botium Toys </a>
  - [How to read a Wireshark TCP_HTTP log](https://github.com/malikaii99/Analyzing-Network-Attacks-IncidentReport/blob/303098a8fa4b32fd23f0aab146776969cf31dbf9/How%20to%20read%20a%20Wireshark%20TCP_HTTP%20log.docx)

<h3>Section 1: Identify the type of attack that may have caused this network interruption</h3>
The log from the packet sniffer shows that a large number of TCP SYN requests were coming from an unfamiliar IP address. The web server was overwhelmed by the traffic requests and unable to conduct normal business. Based on the log summary, this could be caused by a SYN flood attack (DoS).
<h3>Section 2: Explain how the attack is causing the website to malfunction</h3>
When the website visitors try to establish a connection with the web server, a three-way handshake occurs using the TCP protocol. The handshake consists of three steps: 

  - A SYN packet is sent from the source to the destination, requesting to connect.
  - The destination replies to the source with a SYN-ACK packet to accept the connection request. The destination will reserve resources for the source to connect.
  - A final ACK packet is sent from the source to the destination, acknowledging permission to connect.

Presently, the ongoing situation revolves around the actions of a malicious actor who has engaged in the simultaneous transmission of an extensive quantity of SYN packets towards the server. This relentless barrage of SYN packets has, in turn, resulted in a state where the web server seems to be grappling with a tremendous influx of incoming traffic, causing a pronounced diminishment in its capacity to effectively address this exceptionally high volume of SYN requests. In an effort to mitigate this attack, a temporary measure has been taken, wherein a firewall has been employed to restrict access from the specific IP address responsible for the onslaught. However, it's important to note that this firewall-based solution is merely a short-term countermeasure.

