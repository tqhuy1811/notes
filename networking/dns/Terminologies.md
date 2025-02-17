#### DNS Zone

the entire domain namespace with all its records and subdomains

Example: www.example.com, mail.example.com

Each DNS Zone has exactly one [[#DNS Zone]]

#### Zone Apex
root/naked domain of that zone

Example: example.com

Supports these records

- A records
	- points to ivp4 
- AAAA records
	- points to ivp6
- MX records
	- specify which mail servers handle email for a domain. They include a priority number - lower numbers have higher priority E.g example.com MX 10 mail1.example.com example.com MX 20 mail2.example.com
- TXT records
	-  Domain verification
	- SPF records for email security
	- DKIM authentication
	- General text notes about the domain Example: example.com TXT "v=spf1 include:_spf.google.com ~all"
- [[#NS]] records
- [[#Start of Authority]] records

#### Start of Authority 

Mandatory DNS records that contains information about a [[#DNS Zone]]. Including

- Primary nameserver
- Administrator email
- Zone serial number
- Time intervals for:
    - Zone refresh
    - Retry attempts
    - Record expiration
    - Negative caching

#### Name server

A name server that has definitive information about one part of the Domain Name System (DNS) and that responds to requests from a DNS resolver by returning the applicable information. For example, an authoritative name server for the .com top-level domain (TLD) knows the names of the name servers for every registered .com domain. When a .com authoritative name server receives a request from a DNS resolver for example.com, it responds with the names of the name servers for the DNS service for the example.com domain

####  CIDR block

- A CIDR block is an IP range used with IP-based routing
- each number between dots represents 8 bits (called an octet)

In 10.0.0.0/16:

- 32 total bits in IPv4
- 16 bits for network
- Therefore 32-16 = 16 bits for hosts
- 2^16 = 65,536 addresses

#### CNAME

CNAME creates an alias, pointing one domain name to another. 

At the [[#Zone Apex]], it must has NS and [[#Start of Authority]]records. Since DNS standards don't allow a domain name to have both a CNAME and other record types simultaneously, CNAME can't exist at the apex where NS/SOA records are required.

#### NS
name server record points to an authoritative name server 

#### ALIAS 
is resolved to IP addresses by the DNS provider before responding, so no additional lookup is needed. This avoids the conflict