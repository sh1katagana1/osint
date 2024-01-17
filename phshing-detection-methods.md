# Phishing Detection Methods
Phishing is and has been one of the main initial access attack vectors employed by threat actors. They will try numerous ways to fool their victims, but as a company looking to protect yourself from this, there are some things you can do to try and catch it before it becomes a disaster. One of the most common ways threat actors phish is to make lookalike domains similar to your companies websites. To combat this, we need to first understand the different ways they will try to mimic your name. \
Domain Name Variation Techniques: \
1. Keyword: The domain name contains an important keyword of the original domain (e.g., zelster.com-management.com).
2. hypened subdomain: Change the dot for a hyphen of a subdomain (e.g., www-zelster.com).
3. New TLD: Same domain using a new TLD (e.g., zelster.org)
4. Homoglyph: It replaces a letter in the domain name with letters that look similar (e.g., zelfser.com).
5. Transposition: It swaps two letters within the domain name (e.g., zelster.com).
6. Singularization/Pluralization: Adds or removes “s” at the end of the domain name (e.g., zeltsers.com).
7. Omission: It removes one of the letters from the domain name (e.g., zelser.com).
8. Repetition: It repeats one of the letters in the domain name (e.g., zeltsser.com).
9. Replacement: Like homoglyph but less stealthy. It replaces one of the letters in the domain name, perhaps with a letter in proximity of the original letter on the keyboard (e.g, zektser.com).
10. Subdomained: Introduce a dot inside the domain name (e.g., ze.lster.com).
11. Insertion: It inserts a letter into the domain name (e.g., zerltser.com).
12. Missing dot: Append the TLD to the domain name. (e.g., zelstercom.com)
13. Bitflipping: In the world of computing, everything is stored in bits (zeros and ones) in memory behind the scenes. This applies to domains too. For example, windows.com becomes 01110111... in the volatile memory of your computing device. However, what if one of these bits got automatically flipped due to a solar flare, cosmic rays, or a hardware error? That is one of the 0's becomes a 1 and vice versa. Applying this concept to DNS request, it's possible that the domain requested that arrives to the DNS server isn't the same as the domain initially requested. For example a 1 bit modification in the domain windows.com can transform it into windnws.com. Attackers may register as many bit-flipping domains as possible related to the victim in order to redirect legitimate users to their infrastructure. 

[DnsTwist](https://github.com/elceef/dnstwist) This is one of the most popular algorithms that will generate permutations of your domain and check whether they are registered or not. It also uses a technique called Fuzzy Hashing to compare the original site to the many different registered permutations and see if their are similarities. It does this using 2 popular fuzzy hashing methods called Ssdeep and TLSH. I always start by running this tool through all its many options, which you can find more details in my Domain OSINT entry https://github.com/sh1katagana1/osint/blob/main/domain-osint.md#dnstwist. \
[OpenSquat](https://github.com/atenreiro/opensquat) This is my second go to tool which acts similar to DNSTwist, and pulls all the latest domains registered and checks permutations of keywords. I also have details of usage here: https://github.com/sh1katagana1/osint/blob/main/domain-osint.md#opensquat \
[Phishy Domains](https://phishydomains.com) This is an online version of OpenSquat, with the caveat that it is only the last 24 hours (unlike the tool which can search back further in time) This is one I hit every day to check keywords related to my company to see if anyone registered any domains that could possibly be used for phishing. \
[DnsTwistIT](https://dnstwist.it) This is an online version of DNSTwist, with the caveat that it doesnt allow all the different options of the tool itself, just checks a domain against registered domains as well as possible unregistered permutations. It also allows you to download an csv or json report of its findings. \

## Certificate Transparency
With sites like Lets Encrypt, its easier now for threat actors to make the site look more legit with a valid certificate. Certificate Transparency (CT) is a project that collects the majority of certificates that were issued and provided this data to the public. By parsing CT logs, we can easily extract domain names (from Subject / SAN fields) and make a simple syntactic comparison of keywords inside these domain names. Firstly, we need to get access to Certificate Transparency logs. There are numerous services offering this, including certdb, Censys and crt.sh.We then need to gather a list of potential keywords we want to search. The most common keyword would be the full domain name of some company/service. 

[Cert.sh](https://crt.sh) This will let you search by keyword, domain,etc. For example to search for any certificates with the keyword 'pepsi'
```
https://crt.sh/?q=Pepsi
```
To search for certificates with pepsi.com:
```
https://crt.sh/?q=Pepsi.com
```
This is great because you can the most recent by date and you can easily see if the Issuer is someone like Let's Encrypt. Clicking on the cert.sh.id for any entry will give you the full certificate transparency details. \

[CertStream](https://certstream.calidog.io) This is another great realtime certificate site. You can see SSL certificates as they're issued in real time, allowing you to use it as a building block to make tools that react to new certificates being issued in real time. \
[Phishing Catcher](https://github.com/x0rz/phishing_catcher) Catch possible phishing domains in near real time by looking for suspicious TLS certificate issuances reported to the Certificate Transparency Log (CTL) via the CertStream API. "Suspicious" issuances are those whose domain name scores beyond a certain threshold based on a configuration file. So essentially, there is a configuration file and it has keywords that you can assign numbers to in order see if a certificate matches one or more of those keywords, thus driving the score up to be suspicious. It comes with an included keyword config file with the most common you would see. \
[Whoxy](https://www.whoxy.com/newly-registered-domains/) This is another site that gives you regsistered domain lists. 





