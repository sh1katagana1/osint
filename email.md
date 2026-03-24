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

***


## MOSINT
https://github.com/alpkeskin/mosint \
Email OSINT This tool gives a good summary via emailrep, hunter, HIBP, etc. \
Install
```
go install -v github.com/alpkeskin/mosint/v3/cmd/mosint@latest
```
You need to setup your API keys in .mosint.yaml. I did not find that file when I installed it, so their page has an example one located at https://github.com/alpkeskin/mosint/blob/master/example-config.yaml  I just went to the go/bin folder and made a file called .mosint.yaml and pasted their example in and added my keys. When you run the tool you need to point to this file with --config like so:
```
./mosint leroyjenkins@gmail.com --config <path to your file>
```

***

## Protonmail OSINT
If you need to verify if someone has a proton mail account: \
https://api.protonmail.ch/pks/lookup?op=get&search=notmyemail@protonmail.com 

If your browser prompts you to download a file titled "pubkey.asc", this indicates that the address exists. If you receive a message of "No Key Found", then it does not. If the address exists, navigate to the following URL: \
https://api.protonmail.ch/pks/lookup?op=index&search=notmyemail@protonmail.com \
It will look like:
```
info:1:1
pub:74ecf3959bac5eba2bd636e204fac101b757d18f:1:2048:1623879788::
uid:notmyemail@protonmail.com <notmyemail@protonmail.com>:1623879788::
```
The last set of digits (1623879788) represents an Epoch Unix timestamp. We can convert that number into a date and time at
https://www.unixtimestamp.com/index.php. This tells me that the account was created on or before Wednesday, June 16, 2021 at 21:43:08 GMT.

***

  
## General Links
[Breach Directory](https://breachdirectory.org) Similar to Leak Peek but this one will give you a SHA1 hash beside the partial password. A lot of times you can go to https://md5decrypt.net/en/Sha1/ put the SHA1 in and it will decrypt the full password. \
[Breach VIP](https://breach.vip) Multiple categories including email to check for breach or leak data. \
[Castrick Clues](https://castrickclues.com/) General Email lookup. \
[CleanTalk](https://cleantalk.org/) A reputation service. https://cleantalk.org/email-checker/acidicloop@gmail.com will show if its valid and clean. \
[Digital Footprint Check](https://www.digitalfootprintcheck.com/free-checker.html) check an email against differnt sites its associated with. \
[DNS Checker](https://toolbox.googleapps.com/apps/messageheader/) This has a feature for email header analysis. \
[Email Checker](https://email-checker.net/) \
[Email Dossier](https://centralops.net/co/emaildossier.aspx) Email Investigation \
[Email Formats](https://www.email-format.com/) Find the email address formats in use at thousands of companies \
[Email Header Analysis](https://www.iptrackeronline.com/email-header-analysis.php) \
[Email Header Analyzer](https://iplocation.io/email-header-analyzer) Trace ip by email header. \
[Email Hippo](https://tools.emailhippo.com/) Email Verification \
[Email Security Check](https://emailsecuritycheck.service.ncsc.gov.uk/check)  Check the spf and dmarc of an email address domain \
[Emailrep](https://emailrep.io/) Email reputation search \
[Emkei](https://emkei.cz) Online Fake Emailer \
[Epieos](https://epieos.com) Retrieve information linked to an email address \
[Experte](https://www.experte.com/email-verification) Email reputation. \
[Eyepaste](https://www.eyepaste.com) Disposable Email \
[Gaijin](https://www.gaijin.at/en/tools/e-mail-header-analyzer) Email Header Analysis \
[Google Toolbox Email Header Analyzer](https://toolbox.googleapps.com/apps/messageheader/) Email header analyzer. \
[GuerillaMail](https://www.guerrillamail.com) Anonymous email \
[Have I Been Pwned](https://haveibeenpwned.com) Breach data lookup. \
[Have I Been Sold](https://haveibeensold.app) check if your email has been sold. \
[Hunter](https://hunter.io) Email Investigation \
[LeakIX](https://leakix.net) This service indexes various areas of the internet looking for data leaks which may contain sensitive information. We can query through the site or directly via the following URL structure: https://leakix.net/search?scope=leak&q=%22test@test.com%22  \
[LeakPeek](https://leakpeek.com) The benefit of this service is that it displays a partial view of passwords associated with email addresses within a breach. \
[List of Disposable Email Addresses](https://github.com/disposable-email-domains/disposable-email-domains/blob/master/disposable_email_blocklist.conf) \
[MailHeader](https://mailheader.org/) Analyze Email headers \
[MXToolbox](https://mxtoolbox.com/blacklists.aspx) Email Blacklist Check \
[OSINT Rocks](https://osint.rocks) has a great email search. \
[Osint.sh Reverse Whois](https://osint.sh/reversewhois/) Allow you to find domain names owned by an email address \
[Peepmail](https://samy.pl/peepmail) a tool that allows you to discover business email addresses for users, even if their email address may not be publicly available or shared \
[Reverse MX Record](https://osint.sh/reversemx/) Reveal all domains that use the same mail server \
[Synapseint](https://synapsint.com) has a good email search. \
[Thats Them](https://thatsthem.com/reverse-email-lookup) Reverse Lookup \
[Tuta](https://tuta.com) German encrypted email service. \
[Whoxy](https://www.whoxy.com/email/) This will let you search by email for any domains owned by the email address.
