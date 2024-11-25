# Cybersecurity-Incident-Report-for-Company-s-Website-Outage-1
Section 1: Attack Analysis
Description of the Attack: The incident observed in the network logs reveals a Denial of Service (DoS) attack targeting the company’s web server. Specifically, this attack involves a high volume of TCP SYN requests originating from a single, unfamiliar IP address. This type of attack overwhelms the server by flooding it with incomplete connection requests, consuming its resources, and preventing legitimate traffic from being processed.

Symptoms and Characteristics:

A large number of TCP SYN requests were captured in the packet sniffer logs, all coming from the same source.
These SYN requests were not followed by the completion of the TCP handshake, leaving the server in a half-open state and exhausting its connection resources.
Legitimate users, including employees, experienced a connection timeout error when attempting to access the company’s website.
Type of Network Attack: This attack is classified as a SYN flood, a subset of a DoS attack. Unlike a Distributed Denial of Service (DDoS) attack, which originates from multiple sources, this DoS attack is centralized, making it slightly easier to mitigate but still disruptive.

Section 2: Effects on the Organization and Recommendations
Impact on the Organization:

Disruption of Website Functionality: The web server’s inability to handle the overwhelming number of SYN requests resulted in legitimate traffic being denied access. This caused the website to become non-functional and inaccessible to both employees and external customers.
Operational Delays: Employees could not use the sales webpage to access vacation packages, leading to delays in servicing customer requests.
Potential Loss of Revenue: The website outage could discourage potential customers, leading to a decline in sales and reputational damage for the company.
Potential Consequences: If the attack continues or evolves (e.g., spoofing additional IPs), it could:

Lead to prolonged downtime.
Damage the company’s reputation for reliability.
Increase operational costs due to emergency response and mitigation efforts.
Network Devices and Activities Involved:

Web Server: Targeted directly by the SYN flood, causing it to become unresponsive.
Firewall: Used to block the attacking IP address as a temporary measure.
Packet Sniffer: Utilized to capture and analyze network traffic to confirm the nature of the attack.
Recommendations for Mitigation and Prevention:

Immediate Mitigation:

Rate Limiting: Configure the firewall to limit the rate of incoming SYN requests, preventing the server from being overwhelmed.
TCP SYN Cookies: Enable SYN cookies on the server to manage incomplete TCP connections more efficiently.
Long-term Preventative Measures:

Intrusion Detection and Prevention System (IDPS): Deploy an IDPS to detect and block suspicious traffic patterns before they impact the server.
Load Balancing: Use load balancers to distribute traffic across multiple servers, minimizing the impact of an attack on any single server.
Monitoring and Alerts: Implement advanced monitoring tools to detect unusual traffic patterns in real time and alert the security team immediately.
Geo-blocking: Restrict access from IP ranges that are not part of the company’s expected customer base.
Conclusion: This SYN flood attack highlights vulnerabilities in the company’s current network defenses. While the immediate threat was mitigated by temporarily blocking the attacking IP address and taking the server offline, a more robust, multi-layered security strategy is needed to prevent future incidents and ensure business continuity. Implementing the recommendations outlined above will enhance the company’s resilience against such attacks.
