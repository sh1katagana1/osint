# Web Threat Intel

## FinalRecon

**Description:** FinalRecon is an automatic web reconnaissance tool written in python

Check headers
```
python3 finalrecon.py --headers <url>
```

Check ssl Certificate
```
python3 finalrecon.py --sslinfo <url>
```

Check whois Information
```
python3 finalrecon.py --whois <url>
```

Crawl Target

`python3 finalrecon.py --crawl <url>`

Directory Searching
```
python3 finalrecon.py --dir <url> -e txt,php -w /path/to/wordlist
```

Full scan
```
python3 finalrecon.py --full <url>
```
```
python3 finalrecon.py https://wingnut.com --full -o finalrecon-results.txt
```


## Eyewitness

**Description:** EyeWitness is designed to take screenshots of websites provide some server header info, and identify default credentials if known. 
```
./EyeWitness -f urls.txt --web
```
```
./EyeWitness -x urls.xml --timeout 8 
```
```
./EyeWitness.py -f urls.txt --web --proxy-ip 127.0.0.1 --proxy-port 8080 --proxy-type socks5 --timeout 120
```


## Photon

**Description:** Photon is a Web Crawler

Crawl a single website.
```
python3 photon.py -u "http://example.com"
```

Clone the website locally
```
python photon.py -u "http://example.com" --clone
```

Choose the depth of crawling
```
python photon.py -u "http://example.com" -l 3
```

Choose number of threads used
```
python photon.py -u "http://example.com" -t 10
```

Add cookies
```
python photon.py -u "http://example.com" -c "PHPSESSID=u5423d78fqbaju9a0qke25ca87"
```

Specify output directory
```
python photon.py -u "http://example.com" -o "mydir"
```

Specify User Agents
```
python photon.py -u "http://example.com" --user-agent "curl/7.35.0,Wget/1.15 (linux-gnu)"
```

Export options
```
python photon.py -u "http://example.com" --export=json
```

## Gobuster
**Description** Scans for directories using wordlists \
https://github.com/OJ/gobuster \
Basic directory scan using a wordlist:
```
gobuster dir -u https://www.example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
```


## WPScan

**Description** Scans Wordpress sites

Scan for vulnerable plugins
```
wpscan --url https://www.example.com/benefits -e vp --api-token <api key> --random-user-agent --force
```

Enumerate users
```
wpscan --url https://www.example.com/benefits -e u --api-token <api key> --random-user-agent --force
```


## LogSensor
https://github.com/Mr-Robert0/Logsensor
**Description** A Powerful Sensor Tool to discover login panels, and POST Form SQLi Scanning \
Multiple hosts scanning to detect login panels
```
python3 logsensor.py -f <subdomains-list>
```
```
python3 logsensor.py -f <subdomains-list> -t 50
```
```
python3 logsensor.py -f <subdomains-list>  --login
```

Targeted SQLi Form Scanning
```
python logsensor.py -u www.example.com/login --sqli 
```
```
python logsensor.py -u www.example.com/login -s --proxy http://127.0.0.1:8080
```
```
python logsensor.py -u www.example.com/login -s --inputname email
```
Help File
```
python logsensor.py --help

usage: logsensor.py [-h --help] [--file ] [--url ] [--proxy] [--login] [--sqli] [--threads]

optional arguments:
  -u , --url           Target URL (e.g. http://example.com/ )
  -f , --file          Select a target hosts list file (e.g. list.txt )
  --proxy              Proxy (e.g. http://127.0.0.1:8080)
  -l, --login          run only Login panel Detector Module
  -s, --sqli           run only POST Form SQLi Scanning Module with provided Login panels Urls 
  -n , --inputname     Customize actual username input for SQLi scan (e.g. 'username' or 'email')
  -t , --threads       Number of threads (default 30)
  -h, --help           Show this help message and exit
 ```
## Katana
A next-generation crawling and spidering framework. To install grab the binary here: https://github.com/projectdiscovery/katana/releases \
Usage
```
./katana -u <url>
```
Multiple URLs
```
./katana -u https://tesla.com,https://google.com
```
Runs headless chrome browser with no-sandbox option, useful when running as root user.
```
./katana -u https://tesla.com -headless -no-sandbox
```
Option to define the depth to follow the urls for crawling, the more depth the more number of endpoint being crawled + time for crawl.
```
./katana -u https://tesla.com -d 5
```
Option to enable JavaScript file parsing + crawling the endpoints discovered in JavaScript files, disabled as default.
```
./katana -u https://tesla.com -jc
```
Here is an example of adding a cookie to the request:
```
./katana -u https://tesla.com -H 'Cookie: usrsess=AmljNrESo'
```

## Headerpwn
https://github.com/devanshbatham/headerpwn \
A fuzzer for analyzing how servers respond to different HTTP headers. You put in a URL and choose a list of headers you want to test. The github site has a headers.txt file which is fairly decent. \
Install (dont forget as it is golang, after running this command the executable will be in the "go" folder):
```
go install github.com/devanshbatham/headerpwn@v0.0.3
```
Usage. This will fuzz the headers found in headers.txt against leroyjenkins.com:
```
 ./headerpwn -url https://leroyjenkins.com -headers headers.txt
```
I can also proxy it through Burp so I can review the output:
```
./headerpwn -url https://example.com -headers my_headers.txt -proxy 127.0.0.1:8080
```

## FFUF
https://github.com/ffuf/ffuf \
This is the best directory enumeration tool I have found, or at least the fastest. Its way faster than dirbuster and gobuster. \
Directory enumeration. -c is to colorize the output, -w for wordlist, u for URL and -r true to follow redirects
```
ffuf -c -w /path/to/wordlist -u https://target/FUZZ -r true
```

## Lazyegg

**Description** LazyEgg is a powerful tool for extracting various types of data from a target URL. It can extract links, images, cookies, forms, JavaScript URLs, localStorage, Host, IP, and leaked credentials. Additionally, it includes a Chrome extension to log real-time JavaScript files as they are loaded.

https://github.com/schooldropout1337/lazyegg

Install
```
git clone https://github.com/schooldropout1337/lazyegg.git
```
Usage
```
python3 lazyegg.py https://example.com
```

## General Links
 [Link Extractor](https://coveryourtracks.eff.org/) \
 [BuiltWith](https://builtwith.com/) \
 [Project Discovery List of Public Bug Bounty Programs](https://github.com/projectdiscovery/public-bugbounty-programs) \
 [Osint.sh Tech Stack](https://osint.sh/stack/) View the technology stack of any website \
 [CMS Analyzer](https://hackertarget.com/wordpress-security-scan/) Checks things like Wordpress on a site, plugins, if user enumeration is possible, etc. \
 [Web Check](https://web-check.xyz/) A good all around web page OSINT tool. \
 [Wordpress Scanner](https://hackertarget.com/wordpress-security-scan) Online wordpress scanner by hackerTarget. Free version only does passive scan \
 [Information Laundromat](https://informationlaundromat.com/content-search) Interesting site to search for similarities in sites as well as similar text on different sites. \
 [WhatCMS](https://whatcms.org/) Checks for what CMS a site is running. \
 [Blacklight](https://themarkup.org/blacklight) An interesting site that will check if a site is doing session tracking, ad trackers,etc. \
 [Tiny Scan](https://www.tiny-scan.com) Effortlessly Dive into URL Details. \
 [Stored Website](https://stored.website/) A site for cached webpages. \
 [Wappalyzer](https://www.wappalyzer.com) See what technology is on a site. \
 [CRXcavator](https://crxcavator.io) Submit a Chrome Extension ID to scan

 

