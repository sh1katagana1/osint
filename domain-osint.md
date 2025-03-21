# Domain Threat Intel

***


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
Pipe results of subfinder subdomains to httpx to see if it has a web service
```
echo trinet.com | ./subfinder -silent | ./httpx -silent
```
Find subdomains for a TLD
```
./subfinder -d example.com -o mysubs.txt
```
Enumerate subdomains for a list of domains
```
./subfinder -dL domains.txt -o all-subs.txt
```


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

## shosubgo
https://github.com/incogbyte/shosubgo

**Description** Small tool to Grab subdomains using Shodan api.

Install
```
go install github.com/incogbyte/shosubgo@latest
```
Run
```
./shosubgo -d chucknorris.com -s <your shodan api key>
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
This will checked every possible domains similar to your domain. it will display all unregistered and registered domains. 
```
dnstwist domain
```
Display only the ones that are registered
```
dnstwist -r domain
```
Display only unregistered ones
```
dnstwist -u domain
```
This option -b will display the HTTP and SMTP service banners on which these services are running. 
```
dnstwist -r -b domain
```
If domain permutations generated by the fuzzing algorithms are insufficient, please supply dnstwist with a dictionary file. Some dictionary samples with a list of the most common words used in phishing campaigns are included. These lists are english.dict, french.dict, polish.dict and we can update these lists also. These lists are located in '/etc/dnstwist/dictionaries'.
```
dnstwist -r -d disctionaries/'dictionary file name' domain
```
This option allows exporting results to CSV and JSON format (only these two formats are supported).
```
dnstwist -r -f csv domain name > name-of-file.csv
```
This option will display the registrar and created date of domains from WHOIS database.
```
dnstwist -r -w domain
```
Another dnstwist feature allows to perform a simple test on each mail server (advertised through DNS MX record) in order to check which one can be used for such hostile intent. Suspicious servers will be marked with SPYING-MX string. MX result alsways display as default with every option.
```
dnstwist -r -m domain
```
This option display geographical location (approximated to the country,real-time lookup) of IPv4 addresses.
```
dnstwist -r -g domain
```
This option used fuzzy hashes to compare two inputs (HTML code) and determine a fundamental level of similarity. The unique feature of detecting similar HTML source code can be enabled with ssdeep argument. For each generated domain, will fetch content from responding HTTP server (following possible redirects), normalize HTML code and compare its fuzzy hash with the one for the original (initial) domain. If the percentage is high, then it indicates that the sites at the inputted domain and the generated domain are almost the same and possibly being used in a phishing attack.
```
dnstwist -r --lsh ssdeep domain
```
By default, ssdeep is used as LSH algorithm, but TLSH is also available and can be enabled like so:
```
dnstwist --lsh tlsh domain.name
```
This option display all the registered domains with different tld such as .edu, .eu, .org, .fr etc.
```
dnstwist -r — tld dictionaries/common_tld.dict domain
```
This option display the messages of dnstwist tool while its process. The messages shows DNS query time out, failed and success.
```
dnstwist -r — debug domain
```
This options specifies a number of concurrent execution flows making the tool faster. By default it’s calculated based on the available CPU cores
```
dnstwist -r domain -t 'number of threads'
```
Specified User-Agents to send with HTTP requests. by default tool user agent is 'Mozilla/5.0 (linux 64-bit) dnstwist/20220815)'. You can see user agent by capturing the packets.
```
dnstwist — useragent 'user agent' -s 'URL'
```
This option shows the domains having name server IPs specified by you.
```
dnstwist domain — nameserver 'name server IPs'
```
This option shows all DNS records releted to target domain.
```
dnstwist -a domain
```
This option save the output in a file.
```
dnstwist domain -o 'file name with path'
```

## Opensquat
https://github.com/atenreiro/opensquat \
**Decsription** \
openSquat is an opensource Intelligence (OSINT) security tool to identify cyber squatting threats to specific companies or domains \
Install
```
git clone https://github.com/atenreiro/opensquat
```
```
pip install -r requirements.txt
```
Lazy run with default options
```
python opensquat.py
```
Search for generic terms used in phishing campaigns (can lead to false-positives) The Opensquat folder has this generic.txt as well as a keywords.txt. These can be modified with keywords you want to look for
```
python opensquat.py -k generic.txt
```
With DNS validation (quad9)
```
python opensquat.py --dns
```
Subdomain search
```
python opensquat.py --subdomains
```
Check for domains with open ports 80/443
```
python opensquat.py --portcheck
```
With Phishing validation (Phishing Database)
```
python opensquat.py --phishing phish_results.txt
```
Save output as JSON
```
python opensquat.py -o example.json -t json
```
Save output as CSV
```
python opensquat.py -o example.csv -t csv
```
Conduct a certificate transparency (ct) hunt
```
python opensquat.py --ct
```
Period search - registrations from the last month (default: day)
```
python opensquat.py -p month
```
Tweak confidence level. The lower values bring more false positives (0: very high, 1: high (default), 2: medium, 3: low, 4: very low
```
python opensquat.py -c 2
```
All validations options
```
python opensquat.py --phishing phishing_domains.txt --dns --ct --subdomains --portcheck
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

## BBOT
https://github.com/blacklanternsecurity/bbot \
BBOT (Bighuge BLS OSINT Tool) is a modular, recursive OSINT framework that can execute the entire OSINT workflow in a single command. BBOT is inspired by Spiderfoot but takes it to the next level with features like multi-target scans, lightning-fast asyncio performance, and NLP-powered subdomain mutations. It offers a wide range of functionality, including subdomain enumeration, port scanning, web screenshots, vulnerability scanning, and much more. \

It appears that you have to run it from its venv location, which by default in Kali is .local/share/pipx/venvs/bbot/bin. Then from there do ./bbot

Installation
```
pipx install bbot
```
Perform a full subdomain enumeration on evilcorp.com, along with cloud enumeration
```
bbot -t evilcorp.com -f subdomain-enum cloud-enum
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
API keys: I did note that when I modified the secrets.yaml file with my API keys, it did not seem to want to load them. However, there is a way to do it in your command itself. You would do your normal commaand but then do -c then the name of the module, then the API key. To get the names of the modules, go here: https://www.blacklanternsecurity.com/bbot/modules/list_of_modules/  A command example would be:
```
./bbot -t leroyjenkins.com -f subdomain-enum email-enum cloud-enum -c modules.shodan_dns.api_key=<api key> modules.builtwith.api_key=<api key> modules.binaryedge.api_key=<api key>
```

## Scilla

**Description** Information Gathering tool - DNS / Subdomains / Ports / Directories enumeration

https://github.com/edoardottt/scilla

**Install**
```
go install -v github.com/edoardottt/scilla/cmd/scilla@latest
```
**Usage**
```
scilla subdomain -target target.domain
```

## Robots.txt
Append robots.txt to the end of any site to see if they show paths and domains. Much of this content would not be found in a search engine because of the "Disallow" setting. These Disallow instructions are telling the search engines to avoid scanning the folders. You can also use Archive.org to search previous versions of a site to see if they had one in the past.

## Naabu
https://github.com/projectdiscovery/naabu \
**Description** Naabu is a port scanning tool written in Go that allows you to enumerate valid ports for hosts in a fast and reliable manner. It is a really simple tool that does fast SYN/CONNECT/UDP scans on the host/list of hosts and lists all ports that return a reply. \
Install
```
go install -v github.com/projectdiscovery/naabu/v2/cmd/naabu@latest
```
Basic Usage (default does nmap top 100 ports)
```
naabu -host hackerone.com
```
Scan a list of domains
```
naabu -list hosts.txt
```
Scan all ports
```
naabu -list hosts.txt -p -
```
Pipe to httpx to find running servers
```
echo hackerone.com | naabu -silent | httpx -silent
```


## BGP ASN Search
Its a good idea to search ASNs of the target company to see if they are in any other IP ranges. Go to https://bgp.he.net/ and type in the name of a company name (not the .com added to it) and search. It will give you a list of ASNs and Routes for anything matching that name. Looking under ASN, you may find additonal domains under the Prefix IPV4 tab

## General Sites
[Certificate Transparency Search](https://ui.ctsearch.entrust.com/ui/ctsearchui) Certificate Transparency (CT) Searching gives organizations an opportunity to review SSL/TLS certificates that have been issued in their name \
[Dnsdumpster](https://dnsdumpster.com/) dns recon & research, find & lookup dns records \
[Crunchbase](https://www.crunchbase.com/) Good corporate information on a company, like acquisitions \
[Robtex](https://www.robtex.com/) Robtex is used for various kinds of research of IP numbers, Domain names, etc \
[Hackertarget](https://hackertarget.com/reverse-dns-lookup) A number of different tools \
[Whois](https://who.is/) Original Whois \
[AnalyzeID](https://analyzeid.com/) Find Other Websites Owned By The Same Person \
[Domain Check](https://centralops.net/asp/co/DomainCheck.vbs.asp) See if a domain is available \
[Greynoise](https://viz.greynoise.io/) Search Internet Noise \
[ShortLinks](https://seintpl.github.io/osint/short-links-verification-cheatsheet) Short links verification cheatsheet \
[UrlScan](https://urlscan.io/) A sandbox for the web \
[ViewDNSInfo](https://viewdns.info/) Multiple DNS Tools \
[What is my IP](https://whatismyipaddress.com/) Check what your actual IP address is \
[Whoxy](https://www.whoxy.com/) Great Domain lookup tool \
[I know what you download](https://iknowwhatyoudownload.com/en/peer/) Torrent downloads search \
[InfoByIP](https://www.infobyip.com/) IP address information \
[IP Fingerprints](https://www.ipfingerprints.com/) Geolocate by IP \
[IP Void](https://www.ipvoid.com/) A vast range of IP address tools to discover details about IP addresses.  \
[Live IP Map](https://www.liveipmap.com/) LiveIPMap.com allows you to lookup or report an IP abuse case.  \
[URLQuery](https://urlquery.net/) urlquery is a service for URL and domain scanning, identifying and categorizing potentially harmful elements on a webpage, checking for malware infections and assessing overall reputation.  \
[URLHaus](https://urlhaus.abuse.ch/) URLhaus is a project from abuse.ch with the goal of sharing malicious URLs that are being used for malware distribution. \
[WebCheck](https://web-check.as93.net/) Good details on a website \
[Is It Phishing](https://isitphishing.org/) Put an organization name in and check if its a victim of phishing \
[Chaos](https://chaos.projectdiscovery.io/#/) Live and comprehensive internet data API, this dataset is actively updated with DNS entries across the entire internet. \
[Driftnet](https://driftnet.io/) A good attack surface analyzer \
[Have I Been Squatted](https://www.haveibeensquatted.com) Domain squatting lookup \
[DNSTwister](https://dnstwister.report/) Good site for checking domain infringement \
[Osint.sh Subdomain Finder](https://osint.sh/subdomain/) Finds subdomains \
[Osint.sh Reverse IP lookup](https://osint.sh/reverseip/) Pop in an ip address and get a result of A records associated \
[Osint.sh DNS Lookup](https://osint.sh/dns/) Provides a report on DNS records for a specified domain or hostname \
[Osint.sh Whois History](https://osint.sh/whoishistory/) Lets you see all the historical WHOIS records of a domain name \
[Osint.sh GeoIP lookup](https://osint.sh/ip/) Find a geolocation of an IP address or a domain including city, region and country. \
[Osint.sh](https://osint.sh/reversens/) Reveal all domains that use the same name server \
[Dig Web Interface](https://digwebinterface.com/?hostnames=&type=&showcommand=on&colorize=on&sort=on&compare=on&location=on&ns=resolver&useresolver=8.8.4.4&nameservers=) online version of Dig. \
[Domain Tools](https://whois.domaintools.com) General Whois domain searching. \
[Dnslytics](https://dnslytics.com/
[DNS Security](https://check.merox.io/) This checks a domains dmarc and spf settings. \
[Where Goes](https://wheregoes.com/) Put a domain >in and it will analyze all the redirects of where it goes. \
[Domain History](https://completedns.com/dns-history/) Checks the history of DNS changes for a domain. \
[BGP Info](https://bgp.tools) Get info on BGP things. \
[URLDna](https://urldna.io/)  Recon on a domain \
[Website Informer](https://website.informer.com) Basic information about a website. \
[FOFA](https://en.fofa.info/) A basic web scanner \
[White Intel](https://whiteintel.io) Interesting info on a domain. \
[Full Hunt](https://fullhunt.io/) Discover, monitor, and secure your attack surface. FullHunt delivers the best platform in the market for attack surface security. \
[Netlas](https://app.netlas.io/host/) Domain Scanner \
[Hypestat](https://hypestat.com/) Statistics on a site. \
[Netcraft](http://toolbar.netcraft.com/site_report?url=undefined#last_reboot) A good all around domain intel scan. \
[Redirect Detective](https://redirectdetective.com/) See what redirects a URL has. \
[StatCrop](https://www.statscrop.com/) Statistics on a site. \
[Tiny Scan](https://www.tiny-scan.com/) Another powerful URL scan tool that provides comprehensive information about any given URL. Get insights into IP address, location, screenshots, technology stack, performance metrics, and more. \
[Who Is Hosting This](https://whoishostingthis.com/) Find out who is hosting a URL. \
[BuiltWith](https://builtwith.com) You can use BuiltWith Relationships tab to find subdomains based on similar analytic tags \
[Pentest-Tools](https://pentest-tools.com/information-gathering/find-subdomains-of-domain?view_report=true) This has a limited free light scan for subdomains. \
[Whatsmydns](https://www.whatsmydns.net/dns-tools.html) Really good DNS tools \
[Subdomainfinder](http://subdomainfinder.c99.nl/) A really good one that also shows which ones have an IP and which ones are behind Cloudflare. \
[Shared Count](https://www.sharedcount.com/) This website provides one simple yet unique service. It searches your target domain and identifies its popularity on social networks such as Facebook and Twitter. It tells me that several people are talking about the website on these services. \
[SEOTools Backlinks](https://smallseotools.com/backlink-checker/) Find backlinks linking to your site. \
[MerkleMap](https://www.merklemap.com/) A good subdomain finder \
[Site24x7](https://www.site24x7.com/tools/) Good all around domain tools.




