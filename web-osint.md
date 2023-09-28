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

 [Link Extractor](https://coveryourtracks.eff.org/) \
 [BuiltWith](https://builtwith.com/)

