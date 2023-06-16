# Web Based OSINT

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
 
 
