# Social Media Threat Intel

# Twitter

## Basic Dorks

Find Tweets from a specific account:

```
from:Sh1kataganai
```

Find direct replies to a specific account

```
to:Sh1kataganai
```

Find all Tweets mentioning an account

```
@Sh1kataganai
```

Find Tweets containing and exact phrase

```
"Leroy Jenkins"
```

Find Tweets containing all of a set of terms

```
skyrim nord dragon
```

Find tweets containing any of a set of terms

```
#skyrim OR "skyrim"
```

Find Tweets linking to a specific website

```
url:sh1katagana1.com
```

Find tweets excluding a specific term

```
from:Sh1kataganai -gaming
```

Find tweets containing images or video

```
skyrim filter:media
```

Find tweets containing images

```
skyrim filter:images
```

Find tweets in a specific language

```
pizza lang:en
```

Find tweets from a specific account mentioning any of a set of terms

```
from:Sh1kataganai hacking OR security OR pop
```

Find tweets from a specific account containing an exact phrase

```
from:Sh1kataganai "pop pop pop"
```

Find tweets that are part of a thread (self replies)

```
from:Sh1kataganai to:Sh1kataganai
```

Find tweets from a specific account from a date range

```
from:Sh1kataganai since:2021-01-01 until:2022-01-01
```

Find tweets from a specific account tagging another account

```
from:Sh1kataganai @dabluezpreacher
```

Find tweets linking to a specific website containing a given search term

```
url:sh1katagana1.com security
```


## Twitter Advanced Search

More granular search from twitter.com\
https://twitter.com/search-advanced

## Foller

This is a really good Twitter account investigation tool\
https://foller.me/

## Twitter Analytics

https://socialbearing.com/

## TwitterID

You put in a username and it gives you the Twitter ID associated with that account\
https://tweeterid.com/

## Tips
1. if your target has their Twitter set to private, you can infer some intel based on replies. If you go to search and do "to: sh1katagana1" this will show all replies to that user. Sometimes it would infer things about the target. You can also search @sh1katagana1 for similar results.
2. if your target used to have their account set to public and is now private, it is possible that search engines cached content when it was public. Try "site:twitter.com/sh1katagana1" to see if any cached results show up. Searching archive.org may show content as well.

# Instagram

## Instaloader

https://instaloader.github.io/

**Description:** 
Grab all pictures and items from an Instagram account\

General grab

```
instaloader leroyjenkins
```

To later update your local copy of that profiles, you may run

```
instaloader --fast-update profile leroyjenkins
```

Instaloader can also be used to download private profiles. To do so, invoke it with

```
instaloader --login=your_username profile <Private Profile>
```


## Gramhir

Analysis on any Instagram account\
https://gramhir.com/

## Instagram Story Viewer

Download any stories from Instagram accounts\
https://storiesdown.com/


# Reddit

A good all around Reddit search\
https://camas.unddit.com/#{%22resultSize%22:100} \
[Reddit User Analyzer](https://reddit-user-analyser.netlify.app) A search for information on a Reddit username.

# Pinterest

Not a tool, but rather an article on how to do OSINT on Pintrest\
https://www.aware-online.com/en/osint-investigation-on-pinterest/

# Tik Tok

General search\
https://www.osintcombine.com/tiktok-quick-search


# Facebook

Get a users Facebook ID\
https://whopostedwhat.com/

If the one above isnt working try this one\
https://lookup-id.com/#


# Telegram

General Tip: In the IOS app, under Settings/Language, you can turn on a Translater. Then when you visit a post that is in a different language, press and hold on the post and Translate it\

General search\
https://lookup-id.com/#

Programmable Google Search\
https://cse.google.com/cse?q=+&cx=006368593537057042503:efxu7xprihg#gsc.tab=0&gsc.q=%20&gsc.page=1

Telegram Statistics. It also has one of the best channel searches I have seen\
https://tgstat.com/

Another great Telegram search\
https://telemetr.io/en/channels

Statistics\
https://telemetr.me/

General Telegram links\
https://github.com/ItIsMeCall911/Awesome-Telegram-OSINT


# Pastebin

https://psbdmp.ws/ 

## General Links
[Blackbird](https://blackbird-osint.herokuapp.com/) Plug a username in and have it check across over 500 sites


