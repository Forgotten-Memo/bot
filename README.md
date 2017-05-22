# AG-bot Guide

AG-bot is a Discord bot programmed and serviced by [Forgotten_memo](https://myanimelist.net/profile/Forgotten_Memo) for the [Anime Guild](https://myanimelist.net/clubs.php?cid=63899). Its purpose is to integrate MyAnimeList (MAL) with Discord and derive statistics from the lists of members who join the guild's Monument Project. This guide for the bot serves to help users better understand the bot and its various commands.

## Contents

- [Bot Overview](#bot-overview)
- [Getting Started](#getting-started)
  - [Linking your MAL account](#linking-your-mal-account)
  - [Some Basic Commands](#some-basic-commands)
  - [Monument Project](#monument-project)
  - [Further Help](#further-help)
- [Command Cheat Sheet](#command-cheat-sheet)
  - [Basic Commands](#basic-commands)
  - [Mod Commands](#mod-commands)
  - [Admin Commands](#admin-commands)
  - [Music Commands](#music-commands)
- [Detailed Commands](#author)
- [FAQ](#license)
- [Credits](#license)
- [License](#license)


## Bot Overview

The bot currently features over 100 commands. The bot's current functionalities include, but are not limited to:
- Anime Database
- Manga Database
- Character Database
- Ability to search for top affinities with other members in Monument Project
- Guild exclusive top anime, manga and character lists
- Guild exclusive seasonal lists
- Basic Recommendation Generator
- Fetching MAL details from MAL and graphs from Graph Anime Plus
- Spoiler command 
- Quote command
- Music commands
- Moderation Tools
- Polarity Stat for anime and manga.

The bot is hosted on the following system:
``` 
== Main System == 
CPU: Ryzen 7 1700 CPU
RAM: 32 GB (2666 MHz)
Storage: Samsung 960 Pro 512GB
```

``` 
== Backup System == 
Raspberry Pi 3b
```

## Getting Started

### Linking your MAL account
The most important command to start with would be **!setMal [username].** Using this command will link your MAL list to the bot's database. *Remember to exclude the square brackets '[]' and replace username with your own MAL username.
> E.g. !setMal Forgotten_Memo

### Some Basic Commands
Now that you’ve linked your MAL list to the database, it’s time to try out some basic commands. In bot-realm, try out the following commands:

> **!malProfile** | Returns your MAL profile details and link.

> **!agTop** | Displays the top 10 anime in the AG leaderboard based on the Monument Project participants’ lists.

> **!agAffinities** | Displays your top 10 affinities out of all the Monument Project participants.

> **!update** | Use this whenever you make significant changes to your MAL list to ensure that your list in my database is in sync with your list on MAL.

### Monument Project
By now, you are probably wondering what this Monument Project thing is. 

It is in essence the database aspect of the bot. While using !setMal will link your list to the database and allow you to use database commands, your scores will not be reflected in the top leaderboards or top affinities until you become an approved member of the Monument Project.

If you would like to join the project or find out more about it, please head over to the main thread at: https://myanimelist.net/forum/?topicid=1592927. 

### Further Help
If you need more help regarding the commands, you can use !help on Discord or check out the rest of this document. (use !guide on Discord if you ever need a link to this doc.)




## Command Cheat Sheet
The following is a quick reference for what each command does and how to use them. For a detailed guide on how to use each individual command, either refer to the next section or use **!help {command_name}** / **!!modHelp {mod_command_name}** / **!!!adminHelp {admin_command_name}**

### Syntax notes
> **u**: malUsername

> **@m**: @discord_mention

> Square brackets []: Variables that are mandatory. (Do not include the actual brackets in your command)

> Curly brackets {}: Variables that are optional. (Do not include the actual brackets in your command)



### Basic Commands
> Basic commands use the prefix '!'

> Use **!help {command_name}** for details on a particular command.

> Most commands will require you to use **!setMal** before they may be used.

#### Info Commands

| Command |  Description |
| ------------- | ------------- |
| `!help {command_name}` | Retrieves the list of standard commands or a specific command.  |
| `!guide` | Returns a link to the bot guide (this page).  |
| `!prc` | Returns details regarding the Power Ranking Committee (PRC) and links to the various threads. |
| `!mp` | Returns details regarding the Monument Project (MP) and sign-up thread.|
| `!oped` | Returns the latest two threads for the seasonal OP or ED competitions. |
| `!guild` | Returns a link to the guild's home page. |
| `!guildHistory` | Returns a link to the guild's halls of History. |
| `!sotw`  | Returns a link to the current SOTW thread. |
| `!faq {faq_id}`  | Returns some answers to frequently asked questions. |
| `!formulas`  | Returns the formulas for some of the bot's score calculation algorithms. |
| `!botinfo`  | Returns basic information on the bot such as version and the system it is running on. |

#### Profile Commands

| Command | Description |
| ------------- | ------------- |
| `!setMal` | Links your MAL profile to the bot. |
| `!update` | Updates the bot's database with your latest lists. |
| `!malProfile {u_OR_@m}` | Retrieves the MAL profile and anime stats of a user. Returns your own by default. |
| `!malProfile-m {u_OR_@m}` | Retrieves the MAL profile and manga stats of a user. Returns your own by default. |
| `!user {@m}` | Returns the user details of a discord user. Returns your own by default. |
| `!recent {u_or_@m}` | Returns the recent anime watched by a user (based on MAL list). Returns your own by default.|
| `!recent-m {u_or_@m}` | Returns the recent manga watched by a user (based on MAL list). Returns your own by default.|
| `!seasonList {u_or_@m}` | Returns a list of anime from the current season that a user is watching. Returns your own by default.|
| `!seasonSummary {u_or_@m}` | Returns a summary of a user's seasonal stats. Returns your own by default.|
| `!random {filter1} {filter2}` | Returns a random anime in the database that you have yet to watch. Filters: `s: weighted score` `n: number of raters` e.g. !random s>7.6 n>20. |
| `!random-m {filter1} {filter2}` | Returns a random manga in the database that you have yet to read. Filters: `s: weighted score` `n: number of raters` e.g. !random s>8. |
| `!randomPtw` | Returns a random anime in your Plan to Watch list. Filters: `s: weighted score` `n: number of raters` e.g. !random s>7 n>30. |
| `!randomPtr` | Returns a random manga in your Plan to Read list. Filters: `s: weighted score` `n: number of raters` e.g. !random s>8. |

#### Utility Commands

| Command | Description |
| ------------- | ------------- |
| `!ping` | Checks whether the bot is alive and if so, how long it takes to respond. |
| `!pingMal` | Checks whether the bot is able to connect to MAL and if so, how long it takes to establish a connection. |
| `!spoiler | [spoiler_title] | [message]` | **USE THIS IN A PM TO THE BOT** This command allows you to share a spoiler without spoiling the fun for those who don't wish to see the spoiler.|
| `!quote [message_id]` | Quotes a message using the id of a message. |
| `!database` | Returns statistics on the sizes of the bot's databases. |
| `!status` | Returns information on the bot's last update and current node. |
| `!scoreCalc [array_of_values]` | Simulates the calculation of the weighted score for an anime or manga with the set of ratings provided. Array of values format: ` 10x2 9x3 8x5 7x4 6 2`|
| `!feedback` | Returns a Google Form link for providing feedback/suggestions regarding the bot. |

#### Anime Commands

| Command | Description |
| ------------- | ------------- |
| `!malGraph {u_or_@m}` | Retrieves the Graph Anime Plus graph of a user.|
| `!affinity [u1_or_@m1] {u2_or_@m2}` | Retrieves the affinity between two users. If only one user is specified, your affinity with them will be returned by default.  |
| `!agAffinities {u_or_@m} {sort_method}` | Retrieves the top affinities (with members in the Monument Project) for a user. Returns your own by default. Sort method: `<affinity> OR <shared>` (sorts by score by default) |
| `!agScore [anime_name]` | Returns the AG score and stats for an anime. |
| `!agscore-id [anime_id]` | Returns the AG score and stats for an anime with the MAL anime ID specified. |
| `!agTop {int}` | Returns the top anime in AG based on the lists of those in the Monument Project. An integer may be added to retrieve subsequent pages of entries. |
| `!agPop {int}` | Returns the most popular anime in AG based on the lists of those in the Monument Project. An integer may be added to retrieve subsequent pages of entries. |
| `!agPolarity {int}` | Returns the anime with the highest polarities in AG based on the lists of those in the Monument Project. An integer may be added to retrieve subsequent pages of entries. |
| `!dbsearch [search1] {search2} {int} {filter}` | Returns entries from the database based on your search entries. Search entries: ` s: rating` `i: anime id ` `u: malUsername` Filters: `<Ranked>` `<Unranked>` e.g. !dbSearch i=9756 s>5 2 \<Ranked\> |
| `!userList {sort_method}` | Returns a list of users in the database sorted by anime statistics. Sort method: `<completed>` `<dropRate>` `<avgRating>` Defaults to total rated anime. |
| `!seasonTop {year season}` | Returns the top anime that started airing in a season. Defaults to the current season. |

#### Manga Commands

| Command | Description |
| ------------- | ------------- |
| `!malGraph-m {u_or_@m}` | Retrieves the Graph Anime Plus manga graph of a user.|
| `!affinity-m [u1_or_@m1] {u2_or_@m2}` | Retrieves the manga affinity between two users. If only one user is specified, your affinity with them will be returned by default.  |
| `!agAffinities-m {u_or_@m} {sort_method}` | Retrieves the top manga affinities (with members in the Monument Project) for a user. Returns your own by default. Sort method: `<affinity> OR <shared>` (sorts by score by default) |
| `!agScore-m [manga_name]` | Returns the AG score and stats for a manga. |
| `!agscore-id-m [manga_id]` | Returns the AG score and stats for a manga with the MAL manga ID specified. |
| `!agTop-m {int}` | Returns the top manga in AG based on the lists of those in the Monument Project. An integer may be added to retrieve subsequent pages of entries. |
| `!agPop-m {int}` | Returns the most popular manga in AG based on the lists of those in the Monument Project. An integer may be added to retrieve subsequent pages of entries. |
| `!agPolarity-m {int}` | Returns the manga with the highest polarities in AG based on the lists of those in the Monument Project. An integer may be added to retrieve subsequent pages of entries. |
| `!dbsearch-m [search1] {search2} {int} {filter}` | Returns manga entries from the database based on your search entries. Search entries: ` s: rating` `i: manga id ` `u: malUsername` Filters: `<Ranked>` `<Unranked>` e.g. !dbSearch i=55215 s=9 \<Unranked\> |
| `!userList-m {sort_method}` | Returns a list of users in the database sorted by manga statistics. Sort method: `<completed>` `<dropRate>` `<avgRating>` Defaults to total rated manga. |

#### Character Commands

| Command |  What it does |
| ------------- | ------------- |
| `!agScore-c [character_name]` | Returns the AG score and stats for a character. |
| `!agScore-id-c [character_id]` |  Returns the AG score and stats for a character with the MAL character ID specified |
| `!agTop-c {int}` | Returns the top characters in AG based on the favorite characters of those in the Monument Project. An integer may be added to retrieve subsequent pages of entries. |
| `!dbsearch-c [search1] {search2} {int} {filter}` | Returns character entries from the database based on your search entries. Search entries: ` p: position` `i: manga id ` `u: malUsername` Filters: `<Ranked>` `<Unranked>` e.g. !dbSearch i=24417 p\<5 |



### Mod Commands
> Mod Commands use the prefix '!!'

> Use **!!modHelp {mod_command_name}** for details on a particular mod command.

> All mod commands require an access rank of 2 or higher. Some commands may require an access rank of 3 or higher. 

#### Bot Settings

| Command |  Description |
| ------------- | ------------- |
| `!!settings` | Returns a list of the bot's current settings. |
| `!!sleep` | Sets the bot to sleep mode. (Will only respond to mod and admin commands) |
| `!!wake` | Wakes the bot up. (Bot will respond to all commands again) |
| `!!setSeason [year season]` | Changes the settings for the current season. |
| `!!setUsername [bot_username]` | Changes the bot's username.|
| `!!setAvatar [image_url]` | Changes the bot's avatar. Must be a jpg or png file. |
| `!!setGame [game_name]` | Changes the game status of the bot. |
| `!!setStatus [status]` | Changes the bot's presence status. Status: `1: Online` `2: Idle` `3; Do not Disturb` `4: Invisible` |

#### Moderation

| Command |  Description |
| ------------- | ------------- |
| `!!block [@m] | {reason}` | Blocks a user from using the bot's commands. |
| `!!unblock [@m] | {reason}` | Unblocks a user from using the bot's commands. |
| `!!lock [@m] | {reason}` | Prevents the user from changing his/her MAL username with !setMal. |
| `!!unlock [@m] | {reason}` | Allows the user to change his/her MAL username with !setMal. |
| `!!mute [@m] | {reason}` | Adds the mute role to a user. |
| `!!unmute [@m] | {reason}` | Removes the mute role from a user. |

#### URL Settings

| Command |  Description |
| ------------- | ------------- |
| `!!setMusic` | Sets the link to the current seasonal OP/ED thread. |
| `!!setPrcCasual` | Sets the link to the PRC casual class thread. |
| `!!setPrcTitan` | Sets the link to the PRC Titan class thread. |
| `!!setPrcCharacter` | Sets the link to the PRC Character class thread. |
| `!!setPrcSignup` | Sets the link to the PRC Sign Up thread. |
| `!!setSotw` | Sets the SOTW youtube link |

#### Utility

| Command |  Description |
| ------------- | ------------- |
| `!!nickname [nickname] [@m]` | Assigns a Discord nickname to a user. |
| `!!delHistory {int}` | Brings up the history of deleted messages. An integer may be added to retrieve subsequent pages of entries. |
| `!!editHistory {int}` | Brings up the history of editted messages. An integer may be added to retrieve subsequent pages of entries. |
| `!!sotwSchedule` | Brings up the schedule of SOTW duties. |

#### Database

| Command |  Description |
| ------------- | ------------- |
| `!!update [u_OR_@m]` | Updates the database with the latest lists of a user. |
| `!!exportAffinities [u_OR_@m]` | Exports the affinities of a user. |

#### PRC
> The following commands require an access rank of 3 or above.

| Command |  Description |
| ------------- | ------------- |
| `!!importPrc {class}` | Starts the wizard for updating the PRC status for those in the database. Class: `Casual` `Titan`|
| `!!assignPrc` | Assigns the PRC role to those who have the PRC status in the database. |
| `!!clearPrc` | Removes the PRC status from those in the database. |
| `!!clearPrcRole` | Removes the PRC role from all users in the Discord Server (for a fresh start at the end of a season) |



### Admin Commands
> Admin Commands use the prefix '!!!'

> Use **!!!adminHelp {admin_command_name}** for details on a particular admin command.

> All admin commands require an access rank of 4 or higher. Some DEV commands may require an access rank of 5.

#### DB Administration

| Command |  Description |
| ------------- | ------------- |
| `!!!setProfile [u] {@m}` | Adds a MAL profile to the bot's registry. A Discord user may be mentioned to tag that MAL profile to them (this would be similar to the mentioned user using !setMal) |
| `!!!remove [u or @m]` | Removes a user from the bot's databases. |
| `!!!userSettings [u or @m]` | Starts the wizard for changing the settings of a user. |
| `!!!editAccess [@m]` | Starts the wizard for changing the access rank of a user. The maximum rank that can be assigned through the wizard is 4. |
| `!!!register [u or @m]` | A shortcut to add a member to the Monument Project (anime) |
| `!!!register-m [u or @m]` | A shortcut to add a member to the Monument Project (manga) |

#### DB Update

| Command |  Description |
| ------------- | ------------- |
| `!!!dbFixId` | Scans the registry and fixes any id issues. | 
| `!!!dbClean` | Retrieves users who are not in the Monument Project, PRC or Discord (users who should not be in the database). |
| `!!!updateAll` | Updates the database with the latest anime lists of all users in the database. AdminMode/DevMode must be enabled. |
| `!!!updateAll-m` | Updates the database with the latest manga lists of all users in the database. AdminMode/DevMode must be enabled.|
| `!!!updateAll-c` | Updates the database with the latest character favorites of all users in the database. AdminMode/DevMode must be enabled.| 
| `!!!scoreAll` | Updates the scores of all anime in the database. AdminMode/DevMode must be enabled.|
| `!!!scoreAll-m` | Updates the scores of all manga in the database. AdminMode/DevMode must be enabled.|
| `!!!scoreAll-c` | Updates the scores of all characters in the database. AdminMode/DevMode must be enabled.| 

#### Admin Settings

| Command |  Description |
| ------------- | ------------- |
| `!!!adminMode-on` | Sets the bot to only recognise commands from those with the admin role. |
| `!!!adminMode-off` | Sets the bot to recognise all commands. |
| `!!!scheduleSotw` | Starts the wizard for setting up the SOTW schedule | 
| `!!!devMode-on` | Sets the bot to only recognise commands from devs. (Access rank 5 required) |
| `!!!devMode-off` | Sets the bot to recognise all commands. (Access rank 5 required) |
| `!!!setCores [int]` | Sets the number of cores that the bot will use for executing multithreaded commands. Recommended range: `1 - 4` (Access rank 5 required) |
| `!!!setSpeed [int]` | Sets the speed that the bot will execute CPU intensive commands. Recommended range: `100 - 150 based on number of cores` (Access rank 5 required) |
| `!!!audioQuality [int]` | Sets the audio quality of the bot. Recommended range: `1 - 6` (Access rank 5 required) |

#### Bot Override

| Command |  Description |
| ------------- | ------------- |
| `!!!kill` | Ends the main bot process if the bot is malfunctioning. The program may still be restarted using the overseer bot. | 
| `!!!suicide` | Ends all bot processes. The program may not be restarted using the overseer bot. (Access rank 5 required) |


## Author

**Forgotten_memo**
- <https://github.com/Forgotten-Memo>
- <https://myanimelist.net/profile/Forgotten_Memo>


## License

Open sourced under the [MIT license](LICENSE.md).
