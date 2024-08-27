# Username/People Threat Intel

***

## Tips
1. Try searching keybase.io for usernames as they may have some PGP profile. site:keybase.io "username"

## Sherlock

**Description:** 
Sherlock can be used to search usernames

To search for only one user:

```
python3 sherlock user123
```

To search for more than one user:

```
python3 sherlock user1 user2 user3
```


## Blackbird

https://github.com/p1ngul1n0/blackbird

**Description**
An OSINT tool to search fast for accounts by username across 574 sites.

Search by username

```
python blackbird.py -u username
```

Run WebServer

```
python blackbird.py --web
```
Access http://127.0.0.1:9797 on the browser


Read results file

```
python blackbird.py -f username.json
```

List supported sites

```
python blackbird.py --list-sites
```

Use proxy

```
python blackbird.py -u crash --proxy http://127.0.0.1:8080
```

Show all results

By default only found accounts will be shown, however you can use the argument below to see all of them.

```
python blackbird.py -u crash --show-all
```

## Maigret
https://github.com/soxoj/maigret \
**Description** Maigret collects a dossier on a person by username only, checking for accounts on a huge number of sites and gathering all the available information from web pages. No API keys required. Maigret is an easy-to use fork of Sherlock. \
Installation
```
pip3 install maigret
```
Usage
```
python3 maigret <username>
```





## Mailcat
The only cat who can find existing email addresses by nickname.

https://github.com/sharsil/mailcat

After cloning, setup python venv and install requirements
```
pip3 install -r requirements.txt
```
Usage
```
python3 mailcat.py <username>
```
Use Tor
```
python3 mailcat.py --tor username
```
Use Proxychains
```
proxychains4 -q python3 mailcat.py username
```
```
python3 mailcat.py username --proxy http://1.2.3.4:8080
```


## General Links

[Family Tree](https://www.familytreenow.com)   This is a good site for just general people searching \
[Social Searcher](https://www.social-searcher.com) This is useful for @mentions of people \
[WhatsMyNameWeb](https://whatsmyname.app) The web version of WhatsMyName. This one is good and you can export the results too \
[namechk](https://namechk.com) This one is good to pop in a company name and see how many domains are registered with that keyword \
[Namecheckr](https://www.namecheckr.com/) Username search \
[Name Checkup](https://namecheckup.com/) Username search \
[Fast People Search](https://www.fastpeoplesearch.com/) People Search \
[Instant Username](https://instantusername.com/#) Username Search \
[192](https://www.192.com/) UK People Search \
[Canada 411](https://www.canada411.ca/) Canada People Search \
[Classmates](https://www.classmates.com) \
[Find a grave](https://www.findagrave.com) \ 
[Red Notice](https://www.interpol.int/en/How-we-work/Notices/Red-Notices/View-Red-Notices) View Red Notices \
[Yellow Notices](https://www.interpol.int/en/How-we-work/Notices/Yellow-Notices/View-Yellow-Notices) View Yellow Notices \
[Open Sanctions](https://www.opensanctions.org) Sanctions search \
[SSN Lookup](https://ics.uci.edu/~dan/genealogy/Miller/javascrp/ssn.htm) Social Security Number location origin search \
[Spokeo](https://www.spokeo.com/?s1=a5425d5a5e3911ee806ca18c0a1eba22&g=phone_12670531_100085299_A4822843475) \
[Checkuser](https://checkuser.vercel.app/) Another username search. \
[Digital Footprint Check](https://www.digitalfootprintcheck.com/free-checker.html) Another username search. \
[Id Crawl](https://www.idcrawl.com/username) Username search. \
[Usersearch](https://www.usersearch.org/) Find someone by username, email, phone number or picture across Social Networks, Dating Sites, Forums, Crypto Forums, Chat Sites and Blogs \
[User Searcher](https://www.user-searcher.com/)  User-Searcher is a powerful and free tool to help you search username in 2000+ websites.









