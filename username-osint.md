# Username/People Threat Intel

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

## UserRecon

**Description:** 
Userrecon checks usernames against a massive list of social media sites

```
./userrecon.sh
```

## Maigret

**Description:** 
Collect a dossier on a person by username only, checking for accounts on a huge number of sites. This is a fork or Sherlock and produces way more content

```
python3 maigret wingnut
```

## WhatsMyName

https://github.com/WebBreacher/WhatsMyName

**Description**
This repository has the unified data required to perform user and username enumeration on various websites.


Check for the user yooper, print out in a table format into console

```
python whats_my_name.py -u yooper -c social
```

Check for the users yooper and maxim, defaults to outputing json to stdout, only returns the found results.

```
python whats_my_name.py -u yooper maxim
```

Check for the users yooper and maxim, defaults to outputing json to stdout, returns the not found and found results.

```
python whats_my_name.py -u yooper maxim -a
```

Check for the users yooper and maxim, defaults to outputing json to stdout, returns the sites where no matches were found.

```
python whats_my_name.py -u yooper maxim -n
```

Check for the user yooper, on social sites

```
python whats_my_name.py -u yooper -c social
```

Check for the user yooper, on social sites, using a different web browser agent

```
python whats_my_name.py -u yooper -c social --user_agent_platform 'Firefox on macOS'
```

Check for the user yooper, print out in a csv format into console

```
python whats_my_name.py -u yooper -c social --format csv
```

Check for the user yooper, print out in a json (default) format into console

```
python whats_my_name.py -u yooper -c social --format json
```

Check for the user yooper, capture errors for debugging purposes

```
python whats_my_name.py -u yooper -c social --capture_errors
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


## Family Tree
This is a good site for just general people searching

https://www.familytreenow.com/


## Social Searcher
This is useful for @mentions of people

https://www.social-searcher.com/

## WhatsMyNameWeb

The web version of WhatsMyName. This one is good and you can export the results too

https://whatsmyname.app/

## Namechk

This one is good to pop in a company name and see how many domains are registered with that keyword. 

https://namechk.com/







