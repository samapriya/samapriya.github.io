# Slack Notifier-CLI Addon

[![DOI](https://zenodo.org/badge/102524939.svg)](https://zenodo.org/badge/latestdoi/102524939)

For those working with team collaborations and notifications slack is a quick alternative to group emails and chats. The need for a notification tool was also met with the use of the API which could be neatly tied up in clients. This CLI add-on was developed simply to function as an additional tool which can reside in an application folder and which can be called upon within a program and act as a notifier for events and updates. The tool combines simple methods in building channels and application bots and uses backends to send messages, files and to handle message history. The notifier was based on a comparison between available methods in tools such as pushbullet, pushover among a few for being able to have cross platform compatibility. Though this was designed as a means for getting process update for specific tools this CLI is essentially a plug and play into any system which can talk and pass arguments to this tool. In time additional and more refined implementation control might be included to handle specific functions.

## Table of contents
* [Getting started](#getting-started)
    * [Slack Credential](#slack-credential)
    * [Slack-Bot Credential](#slack-bot-credential)
    * [Slack Messages](#slack-messages)
    * [Slack Message with Attachment](#slack-message-with-attachment)
    * [Slack Delete All](#slack-delete-all)

## Getting started
To get started you need a Slack account and you can create one [here](https://slack.com/create). Once you create the slack team you can further create an application and a bot within your team. This will allow you to get two API keys that you need for your tool. To access both these API tokens [go to](https://api.slack.com). On the features, tab should be an option called OAuth & Permissions and should provide you with *OAuth Access Token* and *Bot User OAuth Access Token*. Note that the bot can only post in those channels where you have given it permission. If you add the bot to multiple channels you can specify the channel when posting messages or files.

Just browse to the folder and perform `python slack_addon.py -h`:

```
usage: slack_addon.py [-h] { ,smain,sbot,botupdate,botfile,slackdelete} ...

Slack API Addon

positional arguments:
  { ,smain,sbot,botupdate,botfile,slackdelete}
                        -------------------------------------------
                        -----Choose from Slack Tools Below-----
                        -------------------------------------------
    smain               Allows you to save your Slack Main API Token
    sbot                Allows you to save your Slack Bot API Token
    botupdate           Allows your bot to post messages on slack channel
    botfile             Allows you to post a file along with comments
    slackdelete         Allows users to delete all messages and files posted
                        by bots

optional arguments:
  -h, --help            show this help message and exit
```

### Slack Credential
This tool allows the user to save slack credential(OAuth Access Token) into ```users/.config/slackkey``` making sure that they are user specific and are not shared on a system resource or location. It uses a getpass implementation and writes the password as a CSV and the other tools first try to read this and if not present asks for your password.

```
usage: slack_addon.py smain [-h]

optional arguments:
  -h, --help  show this help message and exit
```

### Slack-Bot Credential
This tool allows the user to save slack bot credential(Bot User OAuth Access Token) into ```users/.config/slackkey``` making sure that they are user specific and are not shared on a system resource or location. It uses a getpass implementation and writes the password as a CSV and the other tools first try to read this and if not present asks for your password.

```
usage: slack_addon.py sbot [-h]

optional arguments:
  -h, --help  show this help message and exit
```

### Slack Messages
The slack messaging application is the primary tool which uses the [slacker](https://pypi.python.org/pypi/slacker/0.9.60) backend and allows the user to send messages as a bot to specific channel(s). The messaging service reads your Bot User OAuth Access Token and allows you to send messages to all channels where the bot has been added or has permission to post. If you do not specify the channel the bot posts to the general channel.

```
usage: slack_addon.py botupdate [-h] [--channel CHANNEL] [--msg MSG]

optional arguments:
  -h, --help         show this help message and exit
  --channel CHANNEL  Slack Bot update channel
  --msg MSG          Slack Bot update message
```
Incase you have already saved your password sending a message is as simple as 
```
python slack_addon.py --channel "#general" --message "Hello world"
```
The application can simple be added by a call command with any process running as a system and the bot can update you about system processes, about usage, about application status and file sizes. The possibilities are endless.


### Slack Message with Attachment
One of the most interesting applications for me was to check that not only can I sent system and application updates but I could send snapshots or process outputs such as excel files and zip files and even error logs as needed. This tool allows the slack bot to not only send a message but only to include a file with the message. The filepath points to the location of the file, the fname allows you to name the file accordingly and the cmmt option is used to add a coment of message along with the file. The channel option allows you to choose a specific channel you want to post the message and as earlier it will post to general channel. 

```
usage: slack_addon.py botfile [-h] [--channel CHANNEL] [--filepath FILEPATH]
                              [--cmmt CMMT] [--fname FNAME]

optional arguments:
  -h, --help           show this help message and exit
  --channel CHANNEL    Slack Bot channel
  --filepath FILEPATH  Slack Bot file path to upload
  --cmmt CMMT          Slack Bot file comment
  --fname FNAME        Slack Bot filename
```
Incase you have already saved your password a setup would be simply
```
python slack_addon.py --channel "#general" --filepath "/users/myfilepath.csv" --cmmt "Check the error logs" --fname "errorlog"
```

### Slack Delete All
One of the current non existent methods within Slack is the capability to delete all messages. This is built using a backend [cli tool](https://pypi.python.org/pypi/slack-cleaner/0.3.0) to delete all messages and files if needed and I integrated that in the current CLI. The current tool is primarily related to deleting all messages and files for cleaning up a channel as needed. The tool uses your main slack channel API token and uses that to delete all messages from all users but can be modified to delete messages from specific bots if needed. For now the tool deletes all messages and files in the general channel.

```
usage: slack_addon.py slackdelete [-h]

optional arguments:
  -h, --help  show this help message and exit
```

to use this tool simple type ```python slack_addon.py slackdelete```
