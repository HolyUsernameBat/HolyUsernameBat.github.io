## 🧰 **Workshop Release**

It couldn’t be more simple, navigate to **Tools → Upload files to Steam Workshop**.

![Workshop Tools Screenshot](https://images.steamusercontent.com/ugc/2411186208092595171/FF721A94B8CABD6D78111CF2F84E54A94E1E335A/) 

Since everyone *should* have the same Killing Floor file directories, the workshop will only upload files that are inside your **Killing Floor** folder, and it will install them into other players’ folders *exactly where it found yours*.

^
For example: if you accidentally put a `.rom` file in the **Textures** folder, the workshop might install it into another player’s **Textures** folder too.
And no one will play your map because **you stink.**

---

💡 **ProTip:**
The description box during upload has a strict *character limit*.
But once your item is uploaded, you can freely **edit the description on Steam Workshop** to format it however you like, bold text, sections, emojis, mid life crisis, it's yours to mutilate as you please.

But first…

---

### *Do you Stink?*

If you tick *every single tag* when uploading something simple, you **definitely stink**.
Tags are meant to make the workshop easier to navigate — but for KF, they’re basically pointless now.
There’s no moderation for lying tags, so everyone stinks, nobody browses properly, and it sure won’t help your views in the long run.

![Uploading Screenshot](https://images.steamusercontent.com/ugc/2411186208092603509/0BEC7D009369E289C841ACE848AAE4C89B28AA98/)

📖 *Reference:*
[Tripwire Wiki – Killing Floor Steam Workshop](https://wiki.tripwireinteractive.com/index.php?title=Killing_Floor_Steam_Workshop)

---

### Example Map release

 Here's a YouTube upload of me releasing a KF map, and the things I might consider beforehand, and post-release:
 
 <iframe width="560" height="315" 
src="https://www.youtube.com/embed/SzUIB1Ersa8" 
frameborder="0" 
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen>
</iframe>
 
---
### *Template*

Don’t underestimate your upload formatting — it’s the **main advertisement** for your map.
If you consider yourself semi-experienced, setting a good standard helps others follow suit (unlike 90% of Steam content creators 😏).

Even if you don’t upload a video, feel free to borrow from [this template](https://insultingpros.github.io/LazyKFWiki/#/Workshop/Workshop_Tmpl) or the version below (credits to the [doofus](https://steamcommunity.com/id/NikC-/)):

```
 [h1][b]General Information[/b][/h1]
This remake fixes some nasty original map [b][i]features[/i][/b].
[spoiler]for more info spam comments section[/spoiler]
[list]
[*] Patriarch's spawn in tested, delayed intervals (usually as pairs).
[*] Built-in voteable Hard Mode.
[*] Amounts of dosh given feels more balanced.
[*] There's a second level, with planks, cover and all your wildest dreams.
[*] Additional armour and high tier weapon pickups (with consistent spawn % for all difficulties).
[*] Scripted pipe bombs near blocked off Patty spawns.
[*] Addressed zed pathing issues.
[*] And more fun additions such as a replacement for the siren wave.
[/list]


[h1][b]Whitelist Status[/b][/h1]
[list]
[*] Dedicated server: all clients will level up, get achievs.
[*] Listened server: all clients will level up, get achievs.
[*] Solo: (and you guessed it) Still whitelisted.
[/list]


[h1][b]Technical Information[/b][/h1]
① This is simply a map, no embedded mutators or whatever. To edit/remove pipe bombs search for the tag "PipeSpawner" in the actor class browser and delete or navigate to the scripted triggers -> AI Script.
② 'SkipWave' event command will skip to next trader (but use at own risk on normal mode).
③ The optional Hard Mode features pat spawns without timed intervals, for the classic BossArena experience.
④ Pat spawns are storymap style, so if the probability works out (and you're a lucky bastard) you could have all of the patriarchs spawn in the same room.

[h3][b]Game Mode[/b][/h3]
[code]
Objective
[/code]

[h3][b]Download Link for evil people who refuse to like and subscribe, or admins[/b][/h3]
https://www.dropbox.com/sh/1zuch8rcbo6addy/AACmRci6wVgyAGQbvRzhtVeda?dl=0

[h3][b]Credits[/b][/h3] [/noparse][/noparse][/noparse][/noparse][/noparse][/noparse][/noparse][/noparse][/noparse][/noparse][/noparse]
Pathing, debugging - [url=steamcommunity.com/id/NikC-]FagC[/url]
```

This formats the page like so:
👉 [Example Workshop Page](https://steamcommunity.com/sharedfiles/filedetails/?id=2318348544)