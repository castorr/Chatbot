# Chatbot
[Dowload Chatbot](https://www.streamlabs.com/chatbot)  
[Chatbot Discord](https://discordapp.com/invite/J4QMG5m)  
[Changelog](https://streamlabs.com/chatbot-changelog)  
[Suggest new Features](https://ideas.streamlabs.com)  
[Streamlabs Website](https://www.streamlabs.com)  
  
Documentation:  
[Twitch](https://cdn.streamlabs.com/chatbot/Documentation_Twitch.pdf) | [YouTube](https://cdn.streamlabs.com/chatbot/Documentation_Youtube.pdf) | [Mixer](https://cdn.streamlabs.com/chatbot/Documentation_Mixer.pdf)  
## Messages show in console/chatbot but not stream chat   
You most likely connected the bot to the wrong channel.  
1. Go to connections (the human silhuette in the bottom left corner of the bot)  
2. Go into bot connection (mixer or twitch bot)  
3. Make sure Streamer Channel is the same as your actual stream name  

## Songrequest by artist/name
- To enable this feature go into the `Songrequest` tab in the bot then press the `gear icon` in the top right corner and change `mode` from `$id` to either of the two other options

## Songrequests on Spotify is playing random songs after the first one
- You can disable this in Spotify under `edit` -> `preferences` -> `Advanced settings` -> `Autoplay` -> `Autoplay similar songs when your music ends` 

## SFX aren't playing  
> If preview works you can skip these
- Wrong `audio output` is selected in `settings` -> `general`  
- `audio enging` is set to waveout in `settings` -> `general`  
- File/filepath doesn't exist
- Soundfile format isn't supported (.mp3 only)
- The Chatbot is muted in windows audio mixer

> Preview working but not commands
- `Only play Sound Files when stream is live` is checked in `Commands tab` -> `settings`
- Global sound file user cooldown is in minutes `commands tab` -> `settings` Restart the Chatbot to clear cooldowns
- 

## Bot crashes / doesn't launch
Most likely you don't have microsoft `visual c++ redistributables 2013` installed, note that both `x64` and `x86` needs to be installed. If you have both installed you can still visit [this link](https://www.microsoft.com/en-us/download/details.aspx?id=40784) to download and repair them both. If you need a step to step tutorial for this you can find that [here](https://support.streamlabs.com/hc/en-us/articles/115004407613-Repair-C-Redistributables-2013-x86-and-x64).  

> Running as admin  

- It's always a good option to run the bot as admin to make sure it got all permissions needed. In order to do that you right click your Chatbot Shortcut -> `run as administrator`

> If all else failed it might be MSI afterburner  

- First check if the bot does launch with MSI turned off (If it does not it is a different problem and this solution is not for you) With the bot closed and afterburner open, go into afterburner `settings` > `User Interface` and make sure `Single tray icon mode` is `OFF`. Then go to your tray, right click `RivaTunerStatisticsServer`, and click `show`.  Click `Add`, then find the Streamlabs `Chatbot.exe`.  Making sure the Streamlabs Chatbot profile is selected, turn Application Detection Level to None.  Open the chatbot and it should work fine now.

## Minigames aren't working
Minigames require you to enable currency before they can be used, this still applies even if the cost is 0.
> Heist  

- Command needs to be followed by a value (!heist 10)
- Heist will show a message saying that it's open and people can join
- People joining won't get a message unless enabled in heist message settings
- Start delay needs to be at least 1 to give users the time to join in
- If not enough people (lower than min entries) enters it get cancelled

> Duel

- Command needs to be followed by a target (!challenge must13)
- Users competing in a duel need to have enough currency (same or above the cost)
- A message will be triggered and the target must answer with the original user (!challenge castorr91)
- Expiry time needs to be at least 1 or the target got 0 minutes to accept the challenge

> Free for All  

- Only the first one starting the game will get a response
- Users competing in the Free for All need to have enough currency (same or above the cost)
- Start delay needs to be at least 1 to give users the time to join in
- If not enough people (lower than min entries) enters it get cancelled

> Boss
- Only the first one starting the game will get a response
- Users competing in a duel need to have enough currency (same or above the cost)
- Start delay needs to be at least 1 to give users the time to join in
- When the timer runs out the needs to be a boss that got the interval as the amount of praticipants. If no boss is found for the group size it gets cancelled.  

If minigames still aren't working make sure that `settings` -> `usage` -> `minigames` are set to match where you try to use them. Minigames can only be either discord or stream chat and not both.

## Can't generate token  

This is due to a connection issue between the bot and the site it needs to generate the token. 
- Make sure there's an expcetion for the bot in your firewall
- Make sure there's an exception for the bot in your antivirus/windows defender
- Disabling ipv6 have resolved the issue for some users [Guide Here](https://support.streamlabs.com/hc/en-us/articles/115004232954-How-to-solve-IPv6-issues)
- Use a VPN to get around recaptcha to generate tokens.  

If nothing else work you can manually generate some tokens through these links  
[Twitch Bot Token](https://api.twitch.tv/kraken/oauth2/authorize?response_type=token&client_id=dve7ifeawf0xeegigqamnvqy9qqm2y&redirect_uri=https%3A%2F%2Fstreamlabs.com%2Fchatbot-auth%3Fservice%3Dtwitch&scope=chat_login+user_read&force_verify=true) | 
[Twitch Streamer Token](https://api.twitch.tv/kraken/oauth2/authorize?response_type=token&client_id=dve7ifeawf0xeegigqamnvqy9qqm2y&redirect_uri=https%3A%2F%2Fstreamlabs.com%2Fchatbot-auth%3Fservice%3Dtwitch&scope=chat_login+user_read+channel_check_subscription+channel_commercial+channel_editor+channel_subscriptions&force_verify=true) | 
[Spotify Token](https://accounts.spotify.com/en/authorize?client_id=681722a742874f1295455870c2da4d36&response_type=code&redirect_uri=https:%2F%2Fstreamlabs.com%2Fchatbot-auth%3Fservice%3Dspotify&scope=user-read-private%20playlist-read-private&show_dialog=true) | 
[Streamlabs Token](https://www.streamlabs.com/login?r=https%3A%2F%2Fwww.streamlabs.com%2Fapi%2Fv1.0%2Fauthorize%3Fclient_id%3DWwQemCiJEhLTnk9mBvPCGWIUvbYWNzpuEG6wxkHJ%26redirect_uri%3Dhttps%253A%252F%252Fstreamlabs.com%252Fchatbot-auth%253Fservice%253Dstreamlabs%26response_type%3Dcode%26scope%3Dlegacy.token%2520donations.read%2520alerts.write%2520credits.write%2520jar.write%2520socket.token%2520points.write%2520points.read%2520wheel.write) | 
[Gamewisp Token](https://api.gamewisp.com/pub/v1/oauth/authorize?client_id=fa5358299f20fc03b66e7df1833235169341caf&redirect_uri=https://streamlabs.com/chatbot-auth?service=gamewisp&response_type=code&scope=read_only&state=SLCB) | 
