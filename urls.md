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