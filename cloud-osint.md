# Cloud OSINT
Here are some resources for OSINT in the cloud

## Slurp
https://github.com/nuncan/slurp
**Description** Enumerate S3 buckets via certstream, domain, or keywords. \
### Enumerate the S3 domains for a specific target.
```
slurp domain <-t|--target> google.com
```
### Enumerate S3 buckets based on 3 key words.
```
slurp keyword <-t|--target> linux,golang,python
```
### Follow certstream and enumerate S3 buckets from each domain.
```
slurp certstream
```

## AWSBucketDump
https://github.com/jordanpotti/AWSBucketDump
**Description** AWSBucketDump is a tool to quickly enumerate AWS S3 buckets to look for loot. It's similar to a subdomain bruteforcer but is made specifically for S3 buckets and also has some extra features that allow you to grep for delicious files as well as download interesting files if you're not afraid to quickly fill up your hard drive. \
```
usage: AWSBucketDump.py [-h] [-D] [-t THREADS] -l HOSTLIST [-g GREPWORDS] [-m MAXSIZE]

optional arguments:
  -h, --help    show this help message and exit
  -D            Download files. This requires significant diskspace
  -d            If set to 1 or True, create directories for each host w/ results
  -t THREADS    number of threads
  -l HOSTLIST
  -g GREPWORDS  Provide a wordlist to grep for
  -m MAXSIZE    Maximum file size to download.

 python AWSBucketDump.py -l BucketNames.txt -g interesting_Keywords.txt -D -m 500000 -d 1
 ```
 
 ## Cloud_Enum
 https://github.com/initstring/cloud_enum
 **Description** Multi-cloud OSINT tool. Enumerate public resources in AWS, Azure, and Google Cloud. \
### Usage Case 1
Let's say you were researching "somecompany" whose website is "somecompany.io" that makes a product called "blockchaindoohickey". You could run the tool like this:
 ```
./cloud_enum.py -k somecompany -k somecompany.io -k blockchaindoohickey
```
### Usage Case 2
HTTP scraping and DNS lookups use 5 threads each by default. You can try increasing this, but eventually the cloud providers will rate limit you. Here is an example to increase to 10.
```
./cloud_enum.py -k keyword -t 10
```
### Full Help File
```
usage: cloud_enum.py [-h] -k KEYWORD [-m MUTATIONS] [-b BRUTE]

Multi-cloud enumeration utility. All hail OSINT!

optional arguments:
  -h, --help            show this help message and exit
  -k KEYWORD, --keyword KEYWORD
                        Keyword. Can use argument multiple times.
  -kf KEYFILE, --keyfile KEYFILE
                        Input file with a single keyword per line.
  -m MUTATIONS, --mutations MUTATIONS
                        Mutations. Default: enum_tools/fuzz.txt
  -b BRUTE, --brute BRUTE
                        List to brute-force Azure container names. Default: enum_tools/fuzz.txt
  -t THREADS, --threads THREADS
                        Threads for HTTP brute-force. Default = 5
  -ns NAMESERVER, --nameserver NAMESERVER
                        DNS server to use in brute-force.
  -l LOGFILE, --logfile LOGFILE
                        Will APPEND found items to specified file.
  -f FORMAT, --format FORMAT
                        Format for log file (text,json,csv - defaults to text)
  --disable-aws         Disable Amazon checks.
  --disable-azure       Disable Azure checks.
  --disable-gcp         Disable Google checks.
  -qs, --quickscan      Disable all mutations and second-level scans
  ```
  
  ## CloudBrute
  https://github.com/0xsha/CloudBrute
  **Description** A tool to find a company (target) infrastructure, files, and apps on the top cloud providers (Amazon, Google, Microsoft, DigitalOcean, Alibaba, Vultr, Linode). The outcome is useful for bug bounty hunters, red teamers, and penetration testers alike.
  ### Full Help
  ```
   ██████╗██╗      ██████╗ ██╗   ██╗██████╗ ██████╗ ██████╗ ██╗   ██╗████████╗███████╗
██╔════╝██║     ██╔═══██╗██║   ██║██╔══██╗██╔══██╗██╔══██╗██║   ██║╚══██╔══╝██╔════╝
██║     ██║     ██║   ██║██║   ██║██║  ██║██████╔╝██████╔╝██║   ██║   ██║   █████╗  
██║     ██║     ██║   ██║██║   ██║██║  ██║██╔══██╗██╔══██╗██║   ██║   ██║   ██╔══╝  
╚██████╗███████╗╚██████╔╝╚██████╔╝██████╔╝██████╔╝██║  ██║╚██████╔╝   ██║   ███████╗
 ╚═════╝╚══════╝ ╚═════╝  ╚═════╝ ╚═════╝ ╚═════╝ ╚═╝  ╚═╝ ╚═════╝    ╚═╝   ╚══════╝
                                                V 1.0.7
usage: CloudBrute [-h|--help] -d|--domain "<value>" -k|--keyword "<value>"
                  -w|--wordlist "<value>" [-c|--cloud "<value>"] [-t|--threads
                  <integer>] [-T|--timeout <integer>] [-p|--proxy "<value>"]
                  [-a|--randomagent "<value>"] [-D|--debug] [-q|--quite]
                  [-m|--mode "<value>"] [-o|--output "<value>"]
                  [-C|--configFolder "<value>"]

                  Awesome Cloud Enumerator

Arguments:

  -h  --help          Print help information
  -d  --domain        domain
  -k  --keyword       keyword used to generator urls
  -w  --wordlist      path to wordlist
  -c  --cloud         force a search, check config.yaml providers list
  -t  --threads       number of threads. Default: 80
  -T  --timeout       timeout per request in seconds. Default: 10
  -p  --proxy         use proxy list
  -a  --randomagent   user agent randomization
  -D  --debug         show debug logs. Default: false
  -q  --quite         suppress all output. Default: false
  -m  --mode          storage or app. Default: storage
  -o  --output        Output file. Default: out.txt
  -C  --configFolder  Config path. Default: config


```
### Usage Case 1
Please note -k keyword used to generate URLs, so if you want the full domain to be part of mutation, you have used it for both domain (-d) and keyword (-k) arguments
```
CloudBrute -d target.com -k target -m storage -t 80 -T 10 -w "./data/storage_small.txt"
```
### Usage Case 2
If a cloud provider not detected or want force searching on a specific provider, you can use -c option.
```
CloudBrute -d target.com -k keyword -m storage -t 80 -T 10 -w -c amazon -o target_output.txt
```

## Kaeferjaeger
The hacker collective kaeferjaeger scans all the major cloud providers every week. They pull down every IPs SSL certificate data. They offer it for download. We can search this cert data for our target. Visit http://kaeferjaeger.gay/?dir=sni-ip-ranges and download the data and search for the name you want.

## CloudRecon
https://github.com/g0ldencybersec/CloudRecon \
A tool from jhaddix to scan SSL certs to enumerate cloud assets for a given range \
Install
```
sudo apt install gcc
```
```
go install github.com/g0ldencybersec/CloudRecon@latest
```
For me in Kali, this put it in a folder called "go" in my home directory. You then run ./CloudRecon -h for help file
```
Usage: CloudRecon scrape|store|retr [options]

  -h    Show the program usage message

Subcommands: 

        cloudrecon scrape - Scrape given IPs and output CNs & SANs to stdout
        cloudrecon store - Scrape and collect Orgs,CNs,SANs in local db file
        cloudrecon retr - Query local DB file for results
```
```
scrape [options] -i <IPs/CIDRs or File>
  -a    Add this flag if you want to see all output including failures
  -c int
        How many goroutines running concurrently (default 100)
  -h    print usage!
  -i string
        Either IPs & CIDRs separated by commas, or a file with IPs/CIDRs on each line (default "NONE"                                                                                                                         )
  -p string
        TLS ports to check for certificates (default "443")
  -t int
        Timeout for TLS handshake (default 4)
```
```
store [options] -i <IPs/CIDRs or File>
  -c int
        How many goroutines running concurrently (default 100)
  -db string
        String of the DB you want to connect to and save certs! (default "certificates.db")
  -h    print usage!
  -i string
        Either IPs & CIDRs separated by commas, or a file with IPs/CIDRs on each line (default "NONE")
  -p string
        TLS ports to check for certificates (default "443")
  -t int
        Timeout for TLS handshake (default 4)
```
So after I got the CIDR of the company from an ASN search, I did ./CloudBrute -i <cider> to run the scraper.

## Lazys3
https://github.com/nahamsec/lazys3
**Description:** A Ruby script to bruteforce for AWS s3 buckets using different permutations. \
Usage
```
ruby lazys3.rb <COMPANY>
```

