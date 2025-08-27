![image](https://github.com/nguyendinhkha/Advanced-Computer-Network-Security/assets/82517228/1655b49d-1a42-49cc-85c3-9d41fdf69bd2)


Arkime is an open-source solution that's scalable and offers the capability to capture and search packet data. Arkime enhances modern security infrastructure to enable storage and indexing, with network traffic in the standard PCAP format. The strength of Arkime lies in its ability to provide fast access, with a simple web interface used for browsing PCAPs, searching, and exporting files.

Arkime is a large-scale, open-source solution that provides the capability to capture and search packet data.

There are three components to Arkime:
- The capture component is used for collecting network traffic. It can capture live traffic, from the network or it can process PCAP files.
- Viewer: This is where we'll spend most of our time doing traffic analysis.
- Elastic: is part of the Arkime setup.

Arkime uses Elasticsearch (or OpenSearch) as its metadata storage backend. Metadata retention is based on the scale of the Elasticsearch cluster.

![image](https://github.com/nguyendinhkha/Advanced-Computer-Network-Security/assets/82517228/5ddf9dea-2bb3-4218-b622-69951f6fe8f4)

# NIST Cybersecurity Framework

![image](https://github.com/nguyendinhkha/Advanced-Computer-Network-Security/assets/82517228/f91cd3a8-1d47-4dbe-b5ed-22ecb28afe47)

This framework offers the capability to manage cybersecurity risks within businesses. At its core, it provides functions to achieve specific cybersecurity outcomes: Identify, Protect, Detect, Respond, Recover.

![image](https://github.com/nguyendinhkha/Advanced-Computer-Network-Security/assets/82517228/429304ac-6a86-4f51-9c00-01cebd9d631b)

Each function can be broken down into categories and tightly linked with programming needs and specific activities to protect an organization.

Arkime assists an organization in filling gaps in the categories of “Anomalies and Events” and “Security Continuous Monitoring.”

![image](https://github.com/nguyendinhkha/Advanced-Computer-Network-Security/assets/82517228/ade020a9-2080-4aab-bfb4-983b4055fef3)

Arkime then helps ensure that detected events are analyzed to understand the objectives and methods of attack, the impact of events is determined during analysis, and the network is monitored to detect potential cybersecurity events.

# MITRE ATT&CK

![image](https://github.com/nguyendinhkha/Advanced-Computer-Network-Security/assets/82517228/bc4ee599-788c-4d14-b6cc-d4430691311f)

MITRE ATT&CK provides various attack techniques that adversaries may use against an organization.

![image](https://github.com/nguyendinhkha/Advanced-Computer-Network-Security/assets/82517228/c9c4ef66-545e-40ef-8d31-47f0b7a4432b)

Specifically, we will look at Network Analysis. While Arkime can provide the ability to view all our network traffic, the team will particularly focus on common attack techniques. 

The first is Phishing, and more precisely, Spearphishing Attachment. 
The team will also look at Application Layer Protocols, where attackers use common web protocols like HTTP as they communicate with commands and control. 
Finally, we will examine Exfiltration Over C2 Channel

# MITRE SHIELD 

![image](https://github.com/nguyendinhkha/Advanced-Computer-Network-Security/assets/82517228/5e633856-ebca-4cb9-8021-0455ee01aa5e)

MITRE SHIELD is a framework that helps us map different attack techniques and steps to protect our network. If we map attack techniques and tactics to MITRE SHIELD, we can consider categories such as:

1. DTE0021 – Hunting: The process of searching for the presence or information about the adversary.

2. DTE002 – Network monitoring in which the defender may conduct network monitoring to alert on unusual traffic patterns, large or unexpected data transfers, and other activities that could reveal the presence of an adversary. => Arkime is not used to create alerts, but allows investigation and network traffic analysis to identify these patterns. Arkime also has the capability to integrate with popular and open-source intrusion detection systems, so we can have alert information fed into our Arkime setup.

3. DTE0028 – PCAP Collection: This is one of the key capabilities Arkime offers, the ability to collect full packets of all network traffic. This allows us to review the history of what happened across our network to help recreate events,

![image](https://github.com/nguyendinhkha/Advanced-Computer-Network-Security/assets/82517228/d404fa04-1531-4a27-b4c0-3a5c6caf485f)

So, where does Arkime fit into the standard enterprise setup? The actual deployment depends on where you want coverage. At its core, Arkime needs to monitor network traffic. Thus, any segment of our network that we want to provide the capability to capture full packets is where we should consider placing Arkime.

![image](https://github.com/nguyendinhkha/Advanced-Computer-Network-Security/assets/82517228/e53cd669-dc16-4d1d-9a7f-d44fc82ae73f)

When an Arkime is deployed, it starts capturing entire packets and also sends data to Elasticsearch. What Arkime sends to Elasticsearch is traffic data, and this is the content we want to see in the viewer. This provides us the ability to search through our network traffic data. When we need to view data that isn't part of this data but also have the capability, through the viewer, to download that data for us or allow exporting pcap for further analysis.

![image](https://github.com/nguyendinhkha/Advanced-Computer-Network-Security/assets/82517228/91aac867-3c2c-409f-8a21-025cd0f42991)

A common attack scenario: Phishing with Attachments. A group of attackers attach office documents to an email and attempt to send it to a victim. These documents often contain macros, and while macros are a normal part of office documents, they are used to execute code. If the victim enables the content, it leads to the next stage (Additional Stages N). Powershell might be executed or used to download the next-stage payload, the malware runs and moves to the Infection stage. It's very common for HTTP to be used to request the executable file, and that executable file requests the payload to execute.
