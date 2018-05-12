# Chatbot
[Dowload Chatbot](https://www.streamlabs.com/chatbot)  
[Chatbot Discord](https://discordapp.com/invite/J4QMG5m)  
[Changelog](https://streamlabs.com/chatbot-changelog)  
[Streamlabs Website](https://www.wstreamlabs.com)  

## Messages show in console/chatbot but not stream chat   
You most likely connected the bot to the wrong channel.  
1. Go to connections (the human silhuette in the bottom left corner)  
2. Go into bot connection  
3. Make sure Streamer Channel is the same as your actual stream name  

## Songrequest by artist/name
To enable this feature go into the `Songrequest` tab in the bot then press the `gear icon` in the top right corner and change `mode` from `$id` to either of the two other options

## Songrequests on Spotify is playing random songs after the first one
The most likely reason for this is due to a new option in Spotify. You can disable this in Spotify under `edit` -> `preferences` -> `Advanced settings` -> `Autoplay` -> `Autoplay similar songs when your music ends` 

## Bot crashes / does not launch
Most likely you don't have microsoft `visual c++ redistributables 2013 installed` Note that both `x64` and `x86` needs to be installed. If you have both installed you can still visit [this link](https://www.microsoft.com/en-us/download/details.aspx?id=40784) to download and repair them! If you need a step to step tutorial for this you can find that [here](https://support.streamlabs.com/hc/en-us/articles/115004407613-Repair-C-Redistributables-2013-x86-and-x64).  

> Running as admin  

- It's always a good option to run the bot as admin to make sure it got all permissions needed. In order to do that you right click your Chatbot Shortcut -> `run as administrator`

> If all else failed it might be MSI afterburner  

- First check if the bot does launch with MSI turned off (If it does not it is a different problem and this solution is not for you) With the bot closed and afterburner open, go into afterburner `settings` > `User Interface` and make sure `Single tray icon mode` is `OFF`. Then go to your tray, right click `RivaTunerStatisticsServer`, and click `show`.  Click `Add`, then find the Streamlabs `Chatbot.exe`.  Making sure the Streamlabs Chatbot profile is selected, turn Application Detection Level to None.  Open the chatbot and it should work fine now.
