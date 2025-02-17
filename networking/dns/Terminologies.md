#### DNS Zone

the entire domain namespace with all its records and subdomains

Example: www.example.com, mail.example.com

Each DNS Zone has exactly one [[#DNS Zone]]

#### Zone Apex
root/naked domain of that zone

Example: example.com

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

#### Hosted Zone

A container for records, which include information about how you want to route traffic for a domain (such as example.com) and all of its subdomains (such as www.example.com, retail.example.com, and seattle.accounting.example.com). A hosted zone has the same name as the corresponding domain.

####  CIDR block

- A CIDR block is an IP range used with IP-based routing
- each number between dots represents 8 bits (called an octet)

In 10.0.0.0/16:

- 32 total bits in IPv4
- 16 bits for network
- Therefore 32-16 = 16 bits for hosts
- 2^16 = 65,536 addresses

