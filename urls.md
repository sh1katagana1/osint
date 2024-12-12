# URLS
OSINT for discovering URLs and other URL related information.

***


## Urlfinder
https://github.com/projectdiscovery/urlfinder \
**Description** A high-speed tool for passively gathering URLs, optimized for efficient web asset discovery without active scanning. \

Install
```
go install -v github.com/projectdiscovery/urlfinder/cmd/urlfinder@latest
```
Basic Usage
```
./urlfinder -d tesla.com
```
List all sources
```
./urlfinder -ls
```
Find Urls of a domain, specify specific sources and output to a text file (you can also pass a text file of domains)
```
./urlfinder -d example.com -s commoncrawl,alienvault,waybackarchive -o myoutput.txt
```
To include only URLs containing "shop" or "model":
```
urlfinder -d tesla.com -m shop,model
```
To exclude URLs containing "privacy" or "terms":
```
urlfinder -d tesla.com -f privacy,terms
```
To find URLs containing "support" but exclude those with "faq":
```
urlfinder -d tesla.com -m support -f faq
```

## HTTPX
https://github.com/projectdiscovery/httpx \
**Descripton** httpx is a fast and multi-purpose HTTP toolkit that allows running multiple probes using the retryablehttp library. It is designed to maintain result reliability with an increased number of threads. \

Install
```
go install -v github.com/projectdiscovery/httpx/cmd/httpx@latest
```
Find all favicons from list of domains/subs
```
./httpx -l mylist.txt -favicon
```
All response codes and redirect locations and first 100 words in the response body
```
./httpx -l /root/easm/all-subdomains-11-18-2024.txt -sc -location -bp
```
Find what CDN is in front of it
```
./httpx -l /root/easm/all-subdomains-11-18-2024.txt -cdn
```
TechStack
```
./httpx -l /root/easm/all-subdomains-11-18-2024.txt -td
```
Screenshots using headless chrome. Saves it in the go/bin/output/screenshot folder
```
./httpx -l all-urls.txt -ss
```
Follow all redirects and all host redirects and display the location and status code while using a random user agent
```
./httpx -l /root/easm/all-subdomains-11-18-2024.txt -sc -location -random-agent -follow-redirects -fhr
```
You can use a random user agent with 
```
-random-agent
```
You can follow redirects with 
```
-follow-redirects 
```
You can follow redirects on the same host
```
-follow-host-redirects
```
You can output to all supported formats
```
-oa
``
But it has to also include -o with file path of where you want it saved. No extension needed for the filename.
```
-o pathToFile
```
