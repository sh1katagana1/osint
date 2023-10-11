# Domain Threat Intel

## Cloudflair
https://github.com/christophetd/CloudFlair

**Description:**
CloudFlair is a tool to find origin servers of websites protected by CloudFlare who are publicly exposed and don't restrict network access to the CloudFlare IP ranges as they should. 
```
python3 cloudflair.py leroy.com --censys-api-id <API key> --censys-api-secret <Secret Key> -o cloudflair-8-8-2022.txt
```

--censys-api-id <id>
--censys-api-secret <secret>
-o output file

## Cloudmare
https://github.com/mrh0wl/Cloudmare

**Description:**
Cloudmare is a simple tool to find the origin servers of websites protected by Cloudflare, Sucuri or Incapsula with a misconfiguration DNS.
```
python3 Cloudmare.py -u ljenkins.com
```


## CloudUnflare
https://github.com/greycatz/CloudUnflare

**Description**
Reconnaissance Real IP address for Cloudflare Bypass.
```
bash cloudunflare.bash
```


## DnsRecon
https://github.com/darkoperator/dnsrecon

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
A pure python tool for finding and comparing typo-squatting, bytesquatting, and homoglyph domains for detecting brand impersonation \
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
## Subfinder
https://github.com/projectdiscovery/subfinder
Subfinder is a subdomain discovery tool that returns valid subdomains for websites, using passive online sources. It has a simple, modular architecture and is optimized for speed. subfinder is built for doing one thing only - passive subdomain enumeration, and it does that very well.
```
Usage:
  ./subfinder [flags]

Flags:
INPUT:
  -d, -domain string[]  domains to find subdomains for
  -dL, -list string     file containing list of domains for subdomain discovery

SOURCE:
  -s, -sources string[]           specific sources to use for discovery (-s crtsh,github). Use -ls to display all available sources.
  -recursive                      use only sources that can handle subdomains recursively (e.g. subdomain.domain.tld vs domain.tld)
  -all                            use all sources for enumeration (slow)
  -es, -exclude-sources string[]  sources to exclude from enumeration (-es alienvault,zoomeyeapi)

FILTER:
  -m, -match string[]   subdomain or list of subdomain to match (file or comma separated)
  -f, -filter string[]   subdomain or list of subdomain to filter (file or comma separated)

RATE-LIMIT:
  -rl, -rate-limit int  maximum number of http requests to send per second
  -rls value            maximum number of http requests to send per second four providers in key=value format (-rls "hackertarget=10/s,shodan=15/s")
  -t int                number of concurrent goroutines for resolving (-active only) (default 10)

UPDATE:
   -up, -update                 update subfinder to latest version
   -duc, -disable-update-check  disable automatic subfinder update check

OUTPUT:
  -o, -output string       file to write output to
  -oJ, -json               write output in JSONL(ines) format
  -oD, -output-dir string  directory to write output (-dL only)
  -cs, -collect-sources    include all sources in the output (-json only)
  -oI, -ip                 include host IP in output (-active only)

CONFIGURATION:
  -config string                flag config file (default "$HOME/.config/subfinder/config.yaml")
  -pc, -provider-config string  provider config file (default "$HOME/.config/subfinder/provider-config.yaml")
  -r string[]                   comma separated list of resolvers to use
  -rL, -rlist string            file containing list of resolvers to use
  -nW, -active                  display active subdomains only
  -proxy string                 http proxy to use with subfinder
  -ei, -exclude-ip              exclude IPs from the list of domains

DEBUG:
  -silent             show only subdomains in output
  -version            show version of subfinder
  -v                  show verbose output
  -nc, -no-color      disable color in output
  -ls, -list-sources  list all available sources

OPTIMIZATION:
  -timeout int   seconds to wait before timing out (default 30)
  -max-time int  minutes to wait for enumeration results (default 10)
```
Install
```
go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
```
Its best to install API keys with it. You can get to the config file here:
```
$HOME/.config/subfinder/provider-config.yaml
```
Usage
```
subfinder -d leroyjenkins.com
```
## BBOT
https://github.com/blacklanternsecurity/bbot \
BBOT (Bighuge BLS OSINT Tool) is a modular, recursive OSINT framework that can execute the entire OSINT workflow in a single command. BBOT is inspired by Spiderfoot but takes it to the next level with features like multi-target scans, lightning-fast asyncio performance, and NLP-powered subdomain mutations. It offers a wide range of functionality, including subdomain enumeration, port scanning, web screenshots, vulnerability scanning, and much more. \
Installation
```
pipx install bbot
```
Perform a full subdomain enumeration on evilcorp.com
```
bbot -t evilcorp.com -f subdomain-enum
```
Perform a passive-only subdomain enumeration on evilcorp.com
```
bbot -t evilcorp.com -f subdomain-enum -rf passive
```
A basic web scan includes wappalyzer, robots.txt, and other non-intrusive web modules
```
bbot -t evilcorp.com -f subdomain-enum web-basic
```
Port-scan every subdomain, screenshot every webpage, output to current directory
```
bbot -t evilcorp.com -f subdomain-enum -m nmap gowitness -n my_scan -o .
```
Crawl www.evilcorp.com up to a max depth of 2, automatically extracting emails, secrets, etc.
```
bbot -t www.evilcorp.com -m httpx robots badsecrets secretsdb -c web_spider_distance=2 web_spider_depth=2
```
Subdomains, emails, cloud buckets, port scan, basic web, web screenshots, nuclei
```
bbot -t evilcorp.com -f subdomain-enum email-enum cloud-enum web-basic -m nmap gowitness nuclei --allow-deadly
```
You can clean up the output to just found subdomains per line like so:
```
cat /root/.bbot/scans/{scan_name}/output.txt | grep -F '[DNS_NAME]’ | awk '{print $2}'
```





## BGP ASN Search
Its a good idea to search ASNs of the target company to see if they are in any other IP ranges. Go to https://bgp.he.net/ and type in the name of a company name (not the .com added to it) and search. It will give you a list of ASNs and Routes for anything matching that name. Looking under ASN, you may find additonal domains under the Prefix IPV4 tab

## General Sites
[Dnsdumpster](https://dnsdumpster.com/) \
[Robtex](https://www.robtex.com/) \
[Hackertarget](https://hackertarget.com/reverse-dns-lookup) \
[Whois](https://who.is/) \
[AnalyzeID](https://analyzeid.com/) \
[Domain Check](https://centralops.net/asp/co/DomainCheck.vbs.asp) \
[Greynoise](https://viz.greynoise.io/) \
[ShortLinks](https://seintpl.github.io/osint/short-links-verification-cheatsheet) \
[UrlScan](https://urlscan.io/) \
[ViewDNSInfo](https://viewdns.info/) \
[What is my IP](https://whatismyipaddress.com/) \
[Whoxy](https://www.whoxy.com/) \
[I know what you download](https://iknowwhatyoudownload.com/en/peer/) \
[InfoByIP](https://www.infobyip.com/) \
[IP Fingerprints](https://www.ipfingerprints.com/) \
[IP Void](https://www.ipvoid.com/) \
[Live IP Map](https://www.liveipmap.com/) \
[URLQuery](https://urlquery.net/) \
[URLHaus](https://urlhaus.abuse.ch/) \
[WebCheck](https://web-check.as93.net/) \
[Is It Phishing](https://isitphishing.org/) \
[Chaos](https://chaos.projectdiscovery.io/#/) \
[Driftnet](https://driftnet.io/) A good attack surface analyzer


