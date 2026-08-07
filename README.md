# Discord Activity Honorific Template

This is my own personal [Scriban](https://github.com/scriban/scriban) template for the Final Fantasy 14 [Dalamud](https://github.com/goatcorp/Dalamud) plugin [Discord Activity Honorific](https://github.com/anya-hichu/DiscordActivityHonorific).


*Note: It is not tested with the [SpotifyHonorific](https://valiice.github.io/SpotifyHonorific/) plugin but I've replaced the `Context.SecsElapsed` timer in favor of the `Activity.Elapsed` and other `Activity`-based timers in the hopes that that will help with compatibility until I have a chance to install and test the Spotify-only fork.*

## Capabilities

This template displays your current Spotify song in one of the following formats based on the values configured in the template:

- Timers
  ```
               Player Name
  <• 0:12 [Scrolling song info] 3:45 •>
  ```
- No Timers
  ```
            Player Name
  <• ♪ [Scrolling song info] ♪ 3:45 •>
  ```

The song info can be displayed as:

- An infinite scrolling loop of *Artist Name* - *Song Title* - ...
- Alternating between *Artist Name* and *Song Title* individually

The song text can be displayed as FFXIV block letters (monospace, keeps your title a fixed width) or as regular text (increased readability, but makes your title change size with each update).

## External Documentation

Activity types implementation located at [Discord.Net/src/Discord.Net.Core/Entities/Activities/SpotifyGame.cs](https://github.com/discord-net/Discord.Net/blob/de8da0d3b998d32e248e5e438039d266139e4776/src/Discord.Net.Core/Entities/Activities/SpotifyGame.cs)

More info at [docs.discordnet.dev/guides/int_framework/intro.html](https://docs.discordnet.dev/guides/int_framework/intro.html)

[TimeSpan](https://learn.microsoft.com/en-us/dotnet/api/system.timespan?view=net-10.0) contains the following:
- Days
- Hours
- Minutes
- Seconds
- Milliseconds
- TotalDays, -Hours, etc.
- Ticks
