# Google Hacks
**Description** \
These are common Google Hacks I use for OSINT. Just replace the chucknorris.com value with whatever site your searching for
## General All Around Extension Search
```
site:"example.com" ext:log | ext:conf | ext:txt | ext:cnf | ext:ini | ext:env | ext.sh | ext:bak | ext:backup | ext:swp | ext:old | ext:~ | ext:git | ext:svn | ext:htpasswd | ext:htaccess
```
## Open Redirects
```
site:chucknorris.com inurl:redir | inurl:url | inurl:redirect | inurl:return | inurl:src=http | inurl:r=http
```
## Password Files
```
site:chucknorris.com 'password' filetype:doc | filetype:pdf | filetype:docx | filetype:xls | filetype:dat | filetype:log
```
## Directory Listings
```
site:chucknorris.com intitle:index.of  | 'parent directory'
```
## Database Stuff
```
site:chucknorris.com intext:'sql syntax near' | intext:'syntax error has occurred' | intext:'incorrect syntax near' | intext:'unexpected end of SQL command' | intext:'Warning: mysql_connect()' | intext:'Warning: mysql_query() | intext:'Warning: pg_connect()' | filetype:sqlext:sql | ext:dbf | ext:mdb
```
## Config Files
```
site:chucknorris.com ext:xml | ext:conf | ext:cnf | ext:reg | ext:inf | ext:rdp | ext:cfg | ext:txt | ext:ora | ext:ini | ext:log
```
## Backups
```
site:chucknorris.com ext:bkf | ext:bkp | ext:bak | ext:old | ext:backup
```
## Login Pages
```
site:chucknorris.com inurl:login | inurl:signin | intitle:Login | intitle: signin | inurl:auth
```
## Exposed phpInfo
```
site:chucknorris.com ext:php intitle:phpinfo 'published by the PHP Group'
```
## Subdomain Search
```
site:*.chucknorris.com
```
## S3 Buckets
```
site:.s3.amazonaws.com 'chucknorris.com'
```
## Stack Overflow Search
```
site:stackoverflow.com 'chucknorris.com'
```
## Paste Sites
```
site:pastebin.com | site:paste2.org | site:pastehtml.com | site:slexy.org | site:snipplr.com | site:snipt.net | site:textsnip.com | site:bitpaste.app | site:justpaste.it | site:heypasteit.com | site:hastebin.com | site:dpaste.org | site:dpaste.com | site:codepad.org | site:jsitor.com | site:codepen.io | site:jsfiddle.net | site:dotnetfiddle.net | site:phpfiddle.org | site:ide.geeksforgeeks.org | site:repl.it | site:ideone.com | site:paste.debian.net | site:paste.org | site:paste.org.ru | site:codebeautify.org  | site:codeshare.io | site:trello.com 'chucknorris.com'
```
## Wordpress Contents
```
site:chucknorris.com inurl:wp- | inurl:wp-content | inurl:plugins | inurl:uploads | inurl:themes | inurl:download
```
## (Not a Google Hack, but similar) Wordpress Deep Search
http://wwwb-dedup.us.archive.org:8083/cdx/search?url=chucknorris.com/&matchType=domain&collapse=digest&output=text&fl=original,timestamp&filter=urlkey:.*wp[-].*&limit=1000000&xx=

## Vulnerable Search String (parameters generally seen being used for parameter pollution as well as a number of other web vulnerabilities)
```
site:chucknorris.com inurl:php?=id1 | inurl:index.php?id= | inurl:pageid= | inurl:.php?
```

## Tools
[DorkGPT](https://dorkgpt.com/) Site to use AI to generate google dorks 
