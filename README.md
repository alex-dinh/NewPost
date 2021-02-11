# New Post & ModQueue alert
This script will monitor a list of subreddits for new posts and items in the modqueue. It can then send a message to a slack or discord channel or a telegram user and a private message to a list of users on reddit. 

# Setup
You then need to configure copy the `config.json.template` file to `config.json` and update it with the api keys and settings you want. 

With docker:
> `docker-compose up -d`

Without docker:
> `pip install -r requirements.txt` \
`python ./newpost.py`

### Reddit 
Create your bot / mod account and go to: https://www.reddit.com/prefs/apps/. Create a script app and it will give you the credentials you need. 

### Slack
Create a slack app and get a webhook for the channel you would like to post to: https://api.slack.com/incoming-webhooks#getting-started. 

### Discord
In your server settings create a webhook: https://support.discordapp.com/hc/en-us/articles/228383668-Intro-to-Webhooks

### Reddit PM's
Just fill in the usernames you want to be notified in the array. i.e `"users": [ "Isa", "Owen" ],`

### Telegram
In Telegram, message `/newbot` to @BotFather. Follow the steps and you will receive a token at the end, copy this token to your `config.json`.

To get the chat ID, send your bot a message and open https://api.telegram.org/bot[TOKEN]/getUpdates in your browser, you will find an ID there.

### Features
Then just set enabled to true on the notifications you want. You can also disable modqueue or post checking by setting mosqueue or new_posts to false. If you want to listen for only certain keywords you can add a list and enable that too. 

## ToDo
This is still a WIP and an ever evolving project:

* Write some tests for it
* Try and cover more error cases
* Modmail notifications
* Make into a PyPI module and or systemd service
