# Domain Threat Intel

## Cloudflair

**Description:**
CloudFlair is a tool to find origin servers of websites protected by CloudFlare who are publicly exposed and don't restrict network access to the CloudFlare IP ranges as they should. 
```
python3 cloudflair.py leroy.com --censys-api-id <API key> --censys-api-secret <Secret Key> -o cloudflair-8-8-2022.txt
```

--censys-api-id <id>
--censys-api-secret <secret>
-o output file

## Cloudmare

**Description:**
Cloudmare is a simple tool to find the origin servers of websites protected by Cloudflare, Sucuri or Incapsula with a misconfiguration DNS.
```
python3 Cloudmare.py -u ljenkins.com
```


## CloudUnflare

**Description**
Reconnaissance Real IP address for Cloudflare Bypass.
```
bash cloudunflare.bash
```


## DnsRecon

**Description:** Basic DNS recon also using brute force
```
python3 dnsrecon.py -d wingnut.com
```


## Masscan

**Description:** This is an Internet-scale port scanner. It can scan the entire Internet in under 5 minutes, transmitting 10 million packets per second, from a single machine.
```
sudo masscan -p 80,8000-8100 10.2.2.2/22 --rate=10000
```


## Sublist3r

**Description:** Sudomain bruteforcer
```
python3 sublist3r.py -d wingnut.com -b
```

-b is for enabling bruteforcing

To list all the basic options and switches use -h switch:
``` 
python sublist3r.py -h
```

To enumerate subdomains of specific domain:
``` 
python sublist3r.py -d example.com
```

To enumerate subdomains of specific domain and show only subdomains which have open ports 80 and 443 :
``` 
python sublist3r.py -d example.com -p 80,443
```

To enumerate subdomains of specific domain and show the results in realtime:
``` 
python sublist3r.py -v -d example.com
```

To enumerate subdomains and enable the bruteforce module:
``` 
python sublist3r.py -b -d example.com
```

To enumerate subdomains and use specific engines such Google, Yahoo and Virustotal engines
``` 
python sublist3r.py -e google,yahoo,virustotal -d example.com
```


## Fierce: 

**Description:** DNS brute force
```
fierce --domain wingnut.com
```


## theHarvester
  **Description:** General OSINT tool on domains
  https://github.com/laramies/theHarvester \
  
  Recon scan for example.com. The -d is for the domain, the -l is to limit the results, the -b is for the source you want to use. You can also do -b all to use all of the sources, but you would need API keys for some of them. The -f is to write the reults to an XML file.
``` 
python3 theharvester.py -d example.com -l 500 -b google -f myresults.xml
```

## DNS Dumpster
**Description** A free domain search tool. They even let you download an XLSX output of it
 
https://dnsdumpster.com/

## HackerTarget
I generally use this inside of theHarvester tool, but you can also directly query their API. For example:
 https://api.hackertarget.com/reversedns/?q=trinet.com

 ## Censys Subdomain Finder
 **Description**
 This is a tool to enumerate subdomains using the Certificate Transparency logs stored by Censys. It should return any subdomain who has ever been issued a SSL certificate by a public CA.
 
 https://github.com/christophetd/censys-subdomain-finder
 
 Export your API Keys
 ```
export CENSYS_API_ID=
 ```
 ```
export CENSYS_API_SECRET=
 ```
 Basic Usage
 ```
 python3 censys-subdomain-finder.py wingnut.com
 ```

## DNSTWIST
https://github.com/elceef/dnstwist \
**Description** \
See what sort of trouble users can get in trying to type your domain name. Find lookalike domains that adversaries can use to attack you. Can detect typosquatters, phishing attacks, fraud, and brand impersonation. Useful as an additional source of targeted threat intelligence. \
**Install**
```
pip install dnstwist[full]
```
**Usage**
```
dnstwist --registered domain.name
```
## DNSRazzle
https://github.com/f8al/DNSrazzle \
**Description** \
A pure python tool for finding and comparing typo-squatting, bytesqatting, and homoglyph domains for detecting brand impersonation \
**Install**
```
git clone https://github.com/f8al/DNSrazzle.git
cd DNSrazzle
pip3 install -r requirements.txt
```
**Usage**
```
python3 DNSrazzle.py -d [Domain Name]
```

