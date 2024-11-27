# Email OSINT

***

## General Tips
1. When starting an email investigation, consider focusing on the different parts of the email address. Those would be username, second-level domain and top-level domain. For example, in leroyjenkins@gmail.com, leroyjenkins is the username, gmail is the second-level and com is the top-level.
2. The username portion of the email address can sometimes give additional intel about the target. For example, if its bob1985, its can be inferred it is a male born in 1985. Similarly, pug_lover1 can infer the person is a dog lover, useful info for phish content. Some may also include their country, city, state, political affiliation, etc.
3. The second-level domain can also be used for intel. For example, a comcast one would indicate a home isp likely, while a gmail one would indicate its not likely a business email address. A yandex one can infer their geographical location. An ibm one could infer their place of employment. An icloud could infer their use of Apple products.
4. Top-level domains can infer things like country, state and employer. Like .nl for country, .gov for government and .nyc for state.
5. Start your email osint by putting them in popular search engines like Google and Bing inside quotation marks. This includes just searching the 3 specific portions I talked about above, like just the username, just the TLD, etc. Include dark web search engines for this as well as telegram.
6. Also search in Breach Data sources
7. Search the email in LinkedIn
8. Search the email in Reddit
9. Search the email in a public PGP key database. For that you could find a PGP public key, save it in notepad as a .asc file, then open it in Kleopatra https://www.openpgp.org/software/kleopatra/ and it will extract the username and email from it.
10. Search the email in Whoxy to see if that email registered any domains

## Ghunt
https://github.com/mxrch/GHunt \
**Description** GHunt (v2) is an offensive Google framework, designed to evolve efficiently.
It's currently focused on OSINT, but any use related with Google is possible. \

Help File
```
usage: ghunt [-h] {login,email,gaia,drive} ...

positional arguments:
  {login,email,gaia,drive}
    login   (--clean)         Authenticate GHunt to Google.
    email   (--json)          Get information on an email address.
    gaia    (--json)          Get information on a Gaia ID.
    drive   (--json)          Get information on a Drive file or folder.

options:
  -h, --help            show this help message and exit
  ```

## Holehe
**Description** Holehe checks if an email is attached to an account on sites like twitter, instagram, imgur and more than 120 others. \
https://github.com/megadose/holehe \
Install
```
pip3 install holehe
```
Usage
```
holehe test@gmail.com
```

  
## General Links
[Emailrep](https://emailrep.io/) Email reputation search \
[Epieos](https://epieos.com) Retrieve information linked to an email address \
[GuerillaMail](https://www.guerrillamail.com) Anonymous email \
[Hunter](https://hunter.io) Email Investigation \
[Email Dossier](https://centralops.net/co/emaildossier.aspx) Email Investigation \
[Email Hippo](https://tools.emailhippo.com/) Email Verification \
[Email Checker](https://email-checker.net/) \
[Email Formats](https://www.email-format.com/) Find the email address formats in use at thousands of companies \
[Email Header Analysis](https://www.iptrackeronline.com/email-header-analysis.php) \
[Emkei](https://emkei.cz) Online Fake Emailer \
[Eyepaste](https://www.eyepaste.com) Disposable Email \
[Peepmail](https://samy.pl/peepmail) a tool that allows you to discover business email addresses for users, even if their email address may not be publicly available or shared \
[Gaijin](https://www.gaijin.at/en/tools/e-mail-header-analyzer) Email Header Analysis \
[MXToolbox](https://mxtoolbox.com/blacklists.aspx) Email Blacklist Check \
[Thats Them](https://thatsthem.com/reverse-email-lookup) Reverse Lookup \
[List of Disposable Email Addresses](https://github.com/disposable-email-domains/disposable-email-domains/blob/master/disposable_email_blocklist.conf) \
[MailHeader](https://mailheader.org/) Analyze Email headers \
[Osint.sh Reverse Whois](https://osint.sh/reversewhois/) Allow you to find domain names owned by an email address \
[Reverse MX Record](https://osint.sh/reversemx/) Reveal all domains that use the same mail server \
[Email Security Check](https://emailsecuritycheck.service.ncsc.gov.uk/check)  Check the spf and dmarc of an email address domain \
[Tuta](https://tuta.com) German encrypted email service. \
[Email Header Analyzer](https://iplocation.io/email-header-analyzer) Trace ip by email header. \
[Castrick Clues](https://castrickclues.com/) General Email lookup. \
[Experte](https://www.experte.com/email-verification) Email reputation. \
[Google Toolbox Email Header Analyzer](https://toolbox.googleapps.com/apps/messageheader/) Email header analyzer. \
[DNS Checker](https://toolbox.googleapps.com/apps/messageheader/) This has a feature for email header analysis. \
[Digital Footprint Check](https://www.digitalfootprintcheck.com/free-checker.html) check an email against differnt sites its associated with. \
[Have I Been Sold](https://haveibeensold.app) check if your email has been sold.
