# CYBERSECURITY-FOOTPRINTING-RECONNAISSANCE-ATTACKS-WITH-MULTIPLE-KALI-TOOLS-WK2-PM1

Reconnaissance (also called as footprinting) is the first step in any real attack or security test. Before touching a target, an attacker quietly collects as much public information about it as possible.

Run whois to find the domain registration details

<img width="379" height="185" alt="image" src="https://github.com/user-attachments/assets/db67e354-17e5-4cdd-9891-7567c074676c" />

<img width="449" height="349" alt="image" src="https://github.com/user-attachments/assets/6035fdc3-b847-4470-af96-f878671b84d7" />

These are the standard public registration details returned by the query. The statuses indicate the domain is locked against deletion, renewal, transfer, and updates

This confirms the domain is registered through GoDaddy with full privacy/proxy protection enabled.

Run whatweb to fingerprint the web technologies.

Web technology fingerprinting is a reconnaissance method used in hacking and security testing
<img width="638" height="117" alt="image" src="https://github.com/user-attachments/assets/ee90d57f-433e-4322-88e2-3d05d5625bfe" />

An attacker looks these versions up in vulnerability databases to find known exploits. It also leaks the server IP and an email address.

Resolve the domain name to its IP address using DNS.

<img width="137" height="77" alt="image" src="https://github.com/user-attachments/assets/d92c4789-efcd-4805-8e20-aec0086109be" />

nslookup turns a domain name into its real IP address (192.232.216.135). Knowing the IP lets an
attacker scan the server directly, look up other sites on the same IP, and map the target's
infrastructure.

Read the HTTP response headers to see the server banner, status, cookies and redirects.
<img width="635" height="123" alt="image" src="https://github.com/user-attachments/assets/f97969a3-149a-4d10-9069-f74e784c7e94" />

HTTP headers leak the web server, caching stack and hidden endpoints (here the WordPress REST API at /wp-json/). Attackers read headers to fingerprint the stack and find entry points without even loading the full page.

Detect whether a Web Application Firewall (WAF) is protecting the target site.

<img width="332" height="170" alt="image" src="https://github.com/user-attachments/assets/418bc5f3-f6ab-4791-bfce-9228cba7febb" />

wafw00f tells an attacker if a firewall is watching. Here the site sits behind ModSecurity (SpiderLabs). Knowing a WAF is present shapes the whole attack: naive attempts will be blocked or logged, so the attacker must adapt or try to bypass it.

Enumerate all DNS records: name servers, mail servers, SPF, TXT and service (SRV) records.

<img width="467" height="285" alt="image" src="https://github.com/user-attachments/assets/92a0eb88-d7d9-4d2e-b68c-cef91f66b55b" />

dnsrecon maps the target's entire DNS footprint: mail servers, DNS software version (Bind 9.16.23), SPF policy and cPanel service records. Each record is a potential foothold and helps an attacker understand the email and hosting setup.

# SUMMARY REPORT ON FOOTPRINTING AND THE TOOLS USED

Footprinting is an important first stage in cybersecurity, ethical hacking, and penetration testing. It involves gathering information about a target website, domain, network, or organization before conducting further security assessments. Its importance lies in helping cybersecurity professionals understand a target's digital environment, identify publicly exposed information, discover potential vulnerabilities, and reduce security risks.

During my practical exercise, I used different tools to perform footprinting and gather information about a target domain. **WHOIS** was used to obtain domain registration details, such as the registrar, registration dates, and name servers. **WhatWeb** was used to identify the technologies and software running on the website. **Nslookup** helped retrieve DNS information, including IP addresses and name servers. **DNSRecon -d** was used to investigate the target domain's DNS infrastructure and discover available DNS records. Finally, **Curl -i** was used to inspect HTTP responses, including response status codes, headers, cookies, and server information.

Combining these tools provided a better understanding of the target's domain information, DNS configuration, website technologies, and server responses. The practical exercise improved my knowledge of reconnaissance and information gathering and demonstrated how footprinting helps identify possible security weaknesses before further penetration testing.

In conclusion, footprinting is essential because it provides the information needed to understand, assess, and improve the security of a target system. All footprinting activities should be conducted with proper authorization.
