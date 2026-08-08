# Discord Activity Honorific Template

This is my own personal [Scriban](https://github.com/scriban/scriban) Spotify template for the Final Fantasy 14 [Dalamud](https://github.com/goatcorp/Dalamud) plugin [Discord Activity Honorific](https://github.com/anya-hichu/DiscordActivityHonorific).

If you want to use it, paste the `template.scriban-txt` code into the Template (second) text box in your plugin configuration. The Filter (first) box should be empty.

*Note: The script is now updated to also work with the [SpotifyHonorific](https://valiice.github.io/SpotifyHonorific/) fork of Discord Activity Honorific. The track timer is slightly less reliable due to* `Activity.Elapsed` *no longer being provided. Personally I recommend using the original plugin unless you have a preference to not use Discord.*

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
  <• ♪ [Scrolling song info] ♪ •>
  ```

The song info can be displayed as:

- An infinite scrolling loop of *Artist Name* - *Song Title* - ...
- Alternating between *Artist Name* and *Song Title* individually

The song text can be displayed as FFXIV block letters (monospace, keeps your title a fixed width) or as regular text (increased readability, but makes your title change size with each update).

## Template Variables

DiscordActivityHonorific supports the following variables:
```
Activiy.Artists             Collection<string>
Activity.AlbumTitle         string
Activity.TrackTitle         string
Activity.StartedAt          <DateTimeOffset>
Activity.EndsAt             <DateTimeOffset>
Activity.Duration           <TimeSpan>
                            *.TotalSeconds is an int
Activity.Elapsed            <TimeSpan>
                            *.TotalSeconds is a double
Activity.Remaining          <TimeSpan>
Activity.TrackId            string
Activity.SessionId          string
Activity.AlbumArtUrl        string
Activity.TrackUrl           string
Activity.Name               string
Activity.Type               enum
Activity.Flags              enum
Activity.Details            string
Context.SecsElapsed         double
```

SpotifyHonorific supports the following variables:
```
Activity.Name			    string
Activity.Artists		    list
Activity.Artists[0].Name	string
Activity.Album.Name		    string
Activity.DurationMs		    int
Activity.Popularity		    int
Context.SecsElapsed		    double
```
and still provides access to some others that aren't documented like `Activity.Type`





## External Documentation

Activity types implementation located at [Discord.Net/src/Discord.Net.Core/Entities/Activities/SpotifyGame.cs](https://github.com/discord-net/Discord.Net/blob/de8da0d3b998d32e248e5e438039d266139e4776/src/Discord.Net.Core/Entities/Activities/SpotifyGame.cs)

More info at [docs.discordnet.dev/guides/int_framework/intro.html](https://docs.discordnet.dev/guides/int_framework/intro.html)

[TimeSpan](https://learn.microsoft.com/en-us/dotnet/api/system.timespan?view=net-10.0) contains at least some the following:
- Days
- Hours
- Minutes
- Seconds
- Milliseconds
- TotalDays, -Hours, etc.
- Ticks
