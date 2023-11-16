# Telegram
This is a repo of any tooling or techniques to search Telegram for information

## Telepathy
https://github.com/proseltd/Telepathy-Community \
For this one, you have to first get a Telegram API. You do that by going to https://my.telegram.org and creating an app (not the bot token api). xI just made an app and called it telepathy and it gave me an ApiID and an App api_hash. When you first run Telepathy it will ask for this as well as the phone number. Put the phone number in using this format +1 555 5555. This will have a code sent to your telegram app that you will need to put in and then you can run your queries. \
Install (I recommend doing this in a venv python virtual environment)
```
pip3 install telepathy
```
Usage. Search a username for information
```
telepathy -t durov
```
A more comprehensive search
```
telepathy -t durov -c
```
