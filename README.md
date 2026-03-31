# Industrial-Control-System-Traffic-Analysis-Lab

Skill: SCADA/ICS Traffic Analysis & SOC Investigation

Note: This documentation was refined using AI-assisted editing to improve clarity and presentation, while maintaining my original analysis and findings.

## Description:
This project demonstrates a full SOC-style network investigation using packet captures from a simulated utility SCADA environment. The lab emphasizes Wireshark-based analysis to identify attacker activity, reconstruct events, and understand operational impact.

## Workflow & Artifacts:

1. Initial Recon & Entry (entry.pcap)
  - Analyzed initial PCAP to determine methods of unauthorized access and tools used for network probing.
  - Identified live hosts, open ports, and services exposed on the internal network.
  - Determined which IPs were likely attacker targets and which were key SCADA devices (HMI/PLC).
2. Network Scanning Analysis (init.recon.pcap)
  - Measured duration of port scans and determined which ports were targeted.
  - Correlated IPs and ports to identify which devices acted as HMIs and which were other networked assets.
  - Mapped scan coverage versus critical SCADA nodes to assess potential threat exposure.
3. SCADA Protocol Inspection (HMI2PLC.pcap)
  - Examined traffic between HMI and PLC devices.
  - Identified industrial protocol in use and tracked data flow at the packet level, including counter fields and request/response patterns.
  - Assessed communication patterns to distinguish normal operational behavior from anomalies.
4. Web Recon & PLC Interaction (web_recon.pcap, hmi_web_recon.pcap)
  - Monitored web traffic to HMI/PLC web interfaces.
  - Determined attacker tools and credentials, authentication events, and operational logs that indicated unauthorized access.
  - Identified time zone discrepancies and timestamps, simulating real SOC correlation of logs across systems.
5. MITM & ARP Spoofing Detection (ettercap.pcap)
  - Captured and analyzed attempted ARP poisoning on PLC and HMI communications.
  - Observed watchdog timer triggers and temporary communication failures caused by spoofed ARP packets.
  - Linked MAC addresses and packet offsets to determine attacker source and confirm the method of disruption.

## Outcome:

Reconstructed a complete timeline of attacker reconnaissance, exploitation, and attempted manipulation of SCADA systems.
Identified IoCs such as unauthorized connections, spoofed ARP replies, and abnormal protocol behavior.
Demonstrated packet-level forensic analysis, correlating PCAP evidence with operational impact.
Produced actionable insights relevant to SOC monitoring, incident response, and critical infrastructure protection.

## Key Skills Demonstrated:

Advanced Wireshark analysis and PCAP forensics
Detection of network reconnaissance, MITM attacks, and protocol anomalies
Correlation of network events with operational SCADA behavior
Ability to generate SOC-relevant insights from raw traffic artifacts
