# Image OSINT
## Exiftool
**Description** Great tool to extract metadata
Install
```
apt install exfiltool
```
Usage
```
Syntax:  exiftool [OPTIONS] FILE
```
## Favihunter
https://github.com/eremit4/favihunter \
**Description** Find assets on the internet using favicon hashes on search engines such as FOFA, Shodan, Censys, Zoomeye, Criminal IP, and ODIN. The program returns a table with the custom queries of each search engine and their shortened URL with the query applied. \
Install
```
git clone https://github.com/eremit4/favihunter.git
```
Install dependencies
```
pip3 install -r requirements.txt
```
Basic Usage
```
python3 favihunter.py --url <url address>
```

## Favicons Tips
Once you have the favicon ID you can see if other IP addresses are associated with it by using the Shodan CLI:
```
shodan search org:"Target" http.favicon.hash:116323821 --fields ip_str,port --separator " " | awk '{print $1":"$2}'
```


## General Links
[Google](https://images.google.com/?gws_rd=ssl) \
[Bing](https://www.bing.com/images/feed) \
[TinEye](https://tineye.com/) \
[Yandex](https://www.yandex.com/images/) \
[Imgur](https://imgur.com/search) \
[Flickr](https://www.flickr.com/) \
[PimEyes](https://pimeyes.com/en) \
[Verexif](https://www.verexif.com/en/) \
[Forensically](https://29a.ch/photo-forensics/#forensic-magnifier) \
[Baidu](https://www.baidu.com/) \
[Bing Image Trending](https://www.bing.com/images/trending?form=Z9LH) \
[Fotoforensics](https://fotoforensics.com/) \
[Reverse Image Analyzer](https://www.osintcombine.com/reverse-image-analyzer) \
[Favihash](https://github.com/m4ll0k/Bug-Bounty-Toolz/blob/master/favihash.py) A script to extract favicon hashes \
[Criminal IP](https://www.criminalip.io) This will give you Favicon IDs as well 
[FindFont](https://www.whatfontis.com/) \
[What the Font](https://www.myfonts.com/pages/whatthefont) \
[Facecheck](https://facecheck.id/) \
[Face Eagle](http://faceagle.com/)

