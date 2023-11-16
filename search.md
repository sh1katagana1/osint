# Search Engines
**Description** \
A list of resources for general searching. This does not include Dark Web engines as that is covered in my Dark Web section. Something to keep in mind is some search engines may curate the results differently depending on where the search query is coming from. If you want to do OSINT on a subject in a specific state, connect to a VPN there and you may get more curated results. 

[Google](Https://www.google.com) The obvious juggernaut \
If you click Tool at the Google Search page you will see some additional things you can use. One is searching based on a time range, like only from past 4 months. The other one is how you want your results, do you want Google to make an educated guess or do you want them to return results verbatim to what you ask it. \
[Bing](https://www.bing.com/) This one has the second largest dataset outside of Google. \
One issue is they got rid of their Advanced Search page where you can make use of their "dorks" in a GUI format. You can still do the normal Bing Dorks directly, but not in GUI format like Google has. \
[Yahoo](https://www.yahoo.com/) This one utilizes Bing's dataset \
The interesting piece of this one is that it does have a GUI Advanced Search and as it utiizes the Bing dataset, its almost a defacto Bing GUI Advanced Search. \
[DuckDuckGo](Https://www.duckduckgo.com)  A more privacy minded search \
[Searx](https://searx.space/) Grab a hosted instance at this site, but you can also host your own for the ultimate privacy centered search \
[Yandex](https://yandex.com/) This one may give a more international result than its search counterparts that are based in the US \
[StartPage](https://www.startpage.com/) \
[SwissCows](https://swisscows.com/en) Another privacy centered search, primarily Bing results \
[OCCRP](https://data.occrp.org/) The global archive of research material for investigative reporting. \
[PDF Search](http://findpdfdoc.com/)  A PDF Search Engine \
[Investigator](https://abhijithb200.github.io/investigator/) A good all around recon tool. You put in a domain and then choose one of the panes, like open redirects, robots, etc \
[Napalm FTP](https://www.searchftps.net/) An FTP search engine \
[Marmont](https://www.mmnt.ru/int/) An FTP Search engine \
[Shodan Dorks](https://github.com/humblelad/Shodan-Dorks) A list of Shodan dorks to better utilize its search \
[GHDB](https://www.exploit-db.com/google-hacking-database) Google Hacking DB \
[Carrot2](https://search.carrot2.org/#/search/web) Carrot2 organizes your search results into topics \
[BlogSearch](http://www.blogsearchengine.org/) A blog search engine \
[Search Engine Colossus](https://www.searchenginecolossus.com/) A massive database of all different search engines \
[Google Dork Cheatsheet 2023](https://usersearch.org/updates/2023/02/05/the-ultimate-google-dorking-cheatsheet-2023/?amp=1) Google Dork cheat sheet
[Shodan](https://shodan.io) \
[Onyphe](https://onyphe.io) \
[Censys](https://search.censys.io/) \
[Urlscan](https://urlscan.io) \
[Netlas](https://app.netlas.io/host) \
[PulseDive](https://pulsedive.com) \
[BVSG](http://bvsg.org/) If you want to look at the results of both Google and Bing in the same window, this site will do that. \
[Wolfram Alpha](https://www.wolframalpha.com/) Academic focused search engine, math and computational tools \
[BoardReader](https://boardreader.com/) A search engine for forums \
[isearchfrom](http://isearchfrom.com/) Search From: custom location, language, device & personalization Google Search tool to preview ads & results \
[Advangle](http://advangle.com/) A GUI Advanced search engine for Google and Bing \
[Archive.org](https://archive.org/) Look up cached web pages and content \
[Archive.is](https://archive.is/) Archived web pages \
[CachedView](http://cachedview.com/) Look up Google cached webpages \
[CachedPages](http://www.cachedpages.com/) Look up Cached webpages \
[Mojeek](https://www.mojeek.com/) No tracking, just search \
[ETools](https://www.etools.ch/) eTools.ch searches major Swiss and international search engines and offers you the best results in full privacy \
[Qwant](https://www.qwant.com/) Another privacy focused search. Mostly pulls Bing results \
[Baidu In English](http://www.baiduinenglish.com/) An engine that takes Baidu results (Chinese) and automatically translates it to English 


## Translater Sites
[Google Translate](https://translate.google.com/) \
[Bing Translate](https://www.bing.com/translator) \
[DeepL Translate](https://www.deepl.com/translator) \
[2Lingual](https://www.2lingual.com/) 

## Downloaders
[Wayback Machine Downloader](https://github.com/hartator/wayback-machine-downloader) \
Install
```
gem install wayback_machine_downloader

```
Usage
```
wayback_machine_downloader http://example.com
```
Help
```
Usage: wayback_machine_downloader http://example.com

Download an entire website from the Wayback Machine.

Optional options:
    -d, --directory PATH             Directory to save the downloaded files into
				     Default is ./websites/ plus the domain name
    -s, --all-timestamps             Download all snapshots/timestamps for a given website
    -f, --from TIMESTAMP             Only files on or after timestamp supplied (ie. 20060716231334)
    -t, --to TIMESTAMP               Only files on or before timestamp supplied (ie. 20100916231334)
    -e, --exact-url                  Download only the url provided and not the full site
    -o, --only ONLY_FILTER           Restrict downloading to urls that match this filter
				     (use // notation for the filter to be treated as a regex)
    -x, --exclude EXCLUDE_FILTER     Skip downloading of urls that match this filter
				     (use // notation for the filter to be treated as a regex)
    -a, --all                        Expand downloading to error files (40x and 50x) and redirections (30x)
    -c, --concurrency NUMBER         Number of multiple files to download at a time
				     Default is one file at a time (ie. 20)
    -p, --maximum-snapshot NUMBER    Maximum snapshot pages to consider (Default is 100)
				     Count an average of 150,000 snapshots per page
    -l, --list                       Only list file urls in a JSON format with the archived timestamps, won't download anything
```



