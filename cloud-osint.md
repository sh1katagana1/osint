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

