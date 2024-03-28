

CORS need to be enabled for core-server as requests would be coming from varying places. Typical command to start core server:  
```shell
rasa run --enable-api --cors "*" --debug
```

----
# Integrating with Telegram
`RASA 3.x`
## Create a telegram bot
1. Create a new telegram bot using BotFather.
2. Get access token and unique bot username, that you have set.

## Set configs in Rasa
1. Create a rasa bot.
2. Start core server(with CORS enabled) and other(action, nlg, etc) as required.
3. Host the core-server to public internet.
	1. Using ngrok: `ngrok http 5005`, assuming core server is running on 5005.
4. In `credentials.yml` file, add:
```yaml
telegram:  
  access_token: "bot token from BotFather"  
  verify: "bot username"  
  webhook_url: "hosted-url/webhooks/telegram/webhook"
```
With this the rasa bot is connected to the telegram bot.

----
