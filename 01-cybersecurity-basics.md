                                                       Cybersecurity Fundamentals

1. The CIA Triad
                 CONFIDENTIALITY
                  (who can see it)
                        /\
                       /  \
                      /    \
                     /      \
                    /________\
          INTEGRITY            AVAILABILITY
        (is it accurate)      (can I reach it)

Confidentiality	Only authorized people can see the data	A hospital lets only the treating team open a patient's records. Receptionists can book appointments but not read histories.
Integrity	Data stays accurate and unaltered	A bank logs every transaction and uses checksums, so no one can quietly change a balance from ₹5,000 to ₹50,000.
Availability	Systems work when people need them	An online store runs backup servers so checkout keeps working during a festival sale even if one server fails.

Every attack below hits at least one of these three, which is why the triad is the foundation of the field.

2. Threats

Phishing

What it is: A fake email, SMS, or website posing as a trusted source.
How it works: The attacker creates urgency ("Your account will be blocked today!") so the victim clicks a link and types credentials into a lookalike login page.
Defense: Multi-factor authentication, plus checking the sender and hovering over links before clicking.
Real incident: In 2020, attackers phoned Twitter employees pretending to be IT staff, got internal access, and took over high-profile accounts to run a Bitcoin scam.

CIA impact: Confidentiality.

Malware

What it is: Software designed to damage, spy on, or control a device.
How it works: It arrives through infected downloads, pirated software, or malicious attachments, then runs quietly to steal data, log keystrokes, or open a backdoor.
Defense: Updated antivirus/EDR, regular patching, and downloading only from trusted sources.
Real incident: Stuxnet (discovered 2010) was a worm that spread via USB drives and Windows flaws, and sabotaged industrial equipment at Iran's nuclear facilities.
CIA impact: Confidentiality, Integrity, and Availability, depending on the type.

DDoS (Distributed Denial of Service)

What it is: Flooding a service with traffic until it can't serve real users.
How it works: The attacker controls a botnet of hijacked devices and makes them all hit one target at once.
Defense: Rate limiting and traffic filtering, ideally via a DDoS-protection service or CDN that absorbs the flood.
Real incident: In 2016, the Mirai botnet, built from infected cameras and routers, attacked DNS provider Dyn and temporarily disrupted sites like Twitter, Netflix, and Reddit.
CIA impact: Availability.

SQL Injection

What it is: Tricking a website's database into running commands the attacker typed in.
How it works: If a login or search box passes user input straight into a database query, crafted input can change the query's meaning, letting the attacker read, change, or delete data.
Defense: Parameterized queries (prepared statements) plus input validation, so input is treated as data and never as code.
Real incident: The 2008 Heartland Payment Systems breach, linked to SQL injection, exposed an estimated 130 million card numbers.
CIA impact: Confidentiality and Integrity.

Brute Force

What it is: Guessing credentials by trying huge numbers of combinations.
How it works: Automated tools cycle through common passwords and leaked password lists until one works. Exposed remote-access services are frequent targets.
Defense: Lockouts or rate limits after failed attempts, long unique passwords, and MFA.
Real incident: The 2021 Colonial Pipeline attack began with a single compromised VPN password on an account without MFA. It's technically credential theft rather than pure guessing, but it shows how one weak login can lead to disaster.
CIA impact: Confidentiality, since it leads to unauthorized access.

Ransomware

What it is: Malware that encrypts files and demands payment for the key.
How it works: It typically enters via phishing or an unpatched flaw, spreads through the network, locks files, and shows a ransom note. Many groups also steal data first and threaten to leak it.
Defense: Regular offline, tested backups, plus timely patching.
Real incident: WannaCry (2017) exploited an unpatched Windows flaw and spread worldwide, severely disrupting the UK's NHS, with hospitals turning away patients. Colonial Pipeline (2021) shut down a major US fuel pipeline for days.
CIA impact: Availability, and often Confidentiality through data theft.

3. Attack Vectors
Social Engineering
What it is: Manipulating people instead of hacking machines, using trust, fear, or urgency.
Examples: A caller posing as bank or IT support, tailgating through a secure door, phishing.
Real incident: The 2020 Twitter breach above, which was a social-engineering attack first and a technical one second.
Countermeasure: Awareness training and a rule to always verify by calling back on an official number.
Wireless Attacks
What it is: Exploiting the open nature of Wi-Fi signals.
Examples: An "evil twin" hotspot with a legitimate-looking name (like a fake café Wi-Fi) that captures traffic, or cracking weak Wi-Fi encryption.
Real incident: The KRACK research (2017) showed a flaw in how WPA2 handled its handshake, allowing attackers in range to potentially read protected traffic. Vendors then issued patches.
Countermeasure: WPA3 (or WPA2 with a strong passphrase), up-to-date router firmware, and a VPN on public Wi-Fi.
Insider Threats
What it is: Risk from people who already have legitimate access, such as employees or contractors, acting maliciously or by accident.
Examples: An employee selling customer data, or someone emailing a sensitive file to the wrong person.
Real incident: Edward Snowden (2013), a contractor who used his authorized access to copy and leak classified NSA documents.
Countermeasure: Least-privilege access, activity logging and monitoring, and removing access immediately when someone leaves.

4. Summary Table
Threat	How it works (short)	Main defense	CIA impact
Phishing	Fake message tricks you into giving credentials	MFA + awareness	Confidentiality
Malware	Malicious software runs on your device	Antivirus/EDR + patching	C, I, A
DDoS	Botnet floods a service	Traffic filtering / CDN	Availability
SQL Injection	Input alters database queries	Parameterized queries	C, I
Brute Force	Automated password guessing	Lockouts + MFA	Confidentiality
Ransomware	Encrypts files for ransom	Offline backups + patching	Availability (+C)
Social Engineering	Manipulates people	Training + verification	C, I
Wireless Attacks	Fake/weak Wi-Fi intercepts data	WPA3 + VPN	Confidentiality
Insider Threat	Trusted user misuses access	Least privilege + monitoring	C, I, A

5. Conclusion: Defense in Depth

No single control stops everything. Phishing can bypass a firewall, and a strong password doesn't help if the software is unpatched. Good security layers several defenses (people, processes, and technology) so that if one fails, another still protects the data. The CIA Triad keeps those layers focused on what matters: keeping data private, accurate, and available.

6. References
NIST Cybersecurity Framework (nist.gov)
OWASP Top 10 (owasp.org), especially for SQL injection
CISA guidance on ransomware and phishing (cisa.gov)
UK NCSC reports on WannaCry (ncsc.gov.uk)
