## **💡 Lighting**

Rick-click, aah I’m getting sick of saying that, so it’s now **“Rick”**.
Rick on your map to place lights wherever ~~he~~ you like.

A wise man (named Rick?) once said lighting makes **90% of the atmosphere** in a map. He's wrong, but it shows you his passion. Take *Waterworks* for example:
![Waterworks Screenshot](https://steamuserimages-a.akamaihd.net/ugc/1026203002356987723/4FDD68D7CB5B1AB8A086F78464C3B409FE041E04/)

Beautiful.

Anyway, the placement is down to your judgment, but there are three critical settings for a light I can let you know about:

A light with **low radius** and **high brightness** will be like an orb of hope in the darkness, while one with **decent brightness** and **high radius** will provide good ambient light to a room.

UE light-ray tracing is pretty bad (*more like realllllly bad*), but if build lighting ends up compressing one of your lights way too much, just add more xD. I’ve seen other mappers stack multiple lights directly on top of each other, with different colours/radius/brightness. Official maps tend to spread multiple tiny light sources out to highlight certain spots, emulate more accurate tracing from the “light” static mesh, and add to the atmosphere.

> **THIS IS RUBBISH UNREAL ED NAMING OMG SO SAD**… The float property **Display → Scaleglow** is NOT to do with ambient glow! It allows you to scale exactly how lighting interacts with your static mesh as a whole (UV). Sooo, pipe or skybox SM too bright for adjacent BSP? Lower that number. Jeez, I thought the only solutions were material modifiers, super small lighting radius or Special Lit :c

**Honourable Mention:** Always use **RGB8 lighting** in the build settings — it looks better and is more optimised than DXT3.
Evidence: [Omnipotents Forum](https://www.omnipotents.com/forums/viewtopic.php?t=162&sid=f5a7eaaeac6f2dde0ab6c2171ab03341)

**Honourable Mention 2:** SDK permanently jacks up the gamma pretty high while launching. One workaround is typing `-nogamma` in Steam Game Properties → Launch Options.

You may notice properties for effects like *torchflicker* or *phase*, but don’t touch them:

<details>
<summary>Spoiler</summary>
they shouldn’t really exist…
</details>

```
If you want an actual flickering or pulsing light, go into the Actor Class Browser and search for "Trigger Light."  
Insert that with Rick, and then play around with 'Light Type', 'Phase', and 'Period' for the best results.  
As mentioned above, I haven’t ever got 'Light Effect' to work in-game, despite appearing otherwise in the SDK preview.
```

**Problems?** → [Beyond Unreal Wiki: Lightmap Errors](https://beyondunrealwiki.github.io/pages/lightmap-errors.html)

### Coronas

Coronas are light/lens flare textures (not to be mistaken for the disease or brand of beer). They can be applied to lights in properties to make the light mesh seem more alive — but are often overdone, so lots of players disable them in settings. :c

To add a corona to your map, you could use a preset in the actor browser, but I usually add in a normal light then do the following:

### Bloom

url=https://en.wikipedia.org/wiki/Bloom_(shader_effect)
Bloom is a common cheap but fancy lighting thing that KF has integrated as an optional display setting, migrated from TWI's Red Orchestra 2 code-base.
Credits to JK for digging up this old TWI forum snippet.
[quote=Red Orchestra: Adaptive Bloom Guide] https://forums.tripwireinteractive.com/index.php?threads/bloom-dev-adaptive-bloom-tutorial.22304/

> > Red Orchestra: Adaptive Bloom Guide
> 
> RO Adaptive Bloom is manipulated by 5 settings:
> **Contrast
> BlurMult
> Ratio
> RatioMaximum**
> **RatioMinimum**
> 
> These settings are level specific and should be set in each level's properties in the editor (Menu:View->Level Properties->Bloom). Bloom may also be tweaked and tested in practice mode using console commands.
> 
> *A note about gamma settings:*
> When tweaking your level settings to look right, make sure to be running with the game's default gamma/brightness/contrast settings. Do this by clicking default in the graphical settings menu (and then configure the rest of the settings to what you like). Even the slightest deviation can look good on your monitor but blown out or too low on everyone else's monitor. It is proper practice to construct with default settings.
> 
> **Contrast**
> 
> ConsoleCmd postfxbloom_bpcontrast x
> 
> Default 1.0
> Min 0.0
> Max Infinity (I recommend no farther than 3.0)
> 
> BPC multiplies the pre-blur blooming image. BPC scales the 'leveled' image from the previous MBL. Raising the BPC past 1.0 pushes lower-brightness colors to be more likely to visibly bloom. BPC is the second value to affect the way a render will bloom and is pre-blur.
> 
> **BlurMult**
> 
> ConsoleCmd postfxbloom_bpcontrast x
> 
> Default 1.0
> Min 0.0
> Max Infinity (I recommend no farther than 3.0)
> 
> BM multiplies the post-blur blooming image. BM affects how bright the overall bloom will be once it is applied/added onto the source render (thereby creating bloom). A BM of 1.0 will have the blooming image with illumination values from 0.0-1.0. To keep the original image from going supernova (whiting out) in areas of high detail but high illumination, it is a good idea to bring the BM down from 1.0 to create a softer bloom. BM is the third value to affect the way a render will bloom and is post-blur.
> 
> **Ratio**
> 
> ConsoleCmd postfxbloom_ratio x
> 
> Default 0.5
> Min 0.0
> Max 1.0
> 
> Ratio is used to determine what should bloom on the screen and what should not bloom on the screen. Basically, ratio represents the approximate ratio (0-1) of the screen that one wants to be blooming at any given time in their level. Ratio is adjusted per-frame based on an accumulated average screen illumination value. The screen illumination value is the average brightness (0-1) of every pixel on the screen. A ratio of 1.0 will have every pixel of the screen attempting to bloom, a ratio of 0.0 will have no pixels blooming, and a ratio of 0.5 will have approximately half the pixels on a given frame blooming. Ratio is capped by RatioMinimum and RatioMaximum before it is used.
> 
> **RatioMinimum**
> 
> ConsoleCmd postfxbloom_ratiomin x
> 
> Default 0.0
> Min 0.0
> Max 1.0 (One should make ratiomin no greater than ratiomax)
> 
> RatioMinimum limits the adjusted Ratio to be greater than or equal to this value. If Ratio is less than this value, Ratio will be changed to equal it. Adjust RatioMinimum to a higher value if your bloom vanishes when Ratio adapts to looking at bright objects that you still want to bloom. Setting RatioMinimum to a value of 0.2, for example, will cause approximately 20 percent of the screen to bloom, even if you're looking at a pure white object/scene.
> 
> **RatioMaximum**
> 
> ConsoleCmd postfxbloom_ratiomax x
> 
> Default 0.5
> Min 0.0 (One should make ratiomax no less than ratiomin)
> Max 1.0
> 
> RatioMaximum caps the adjusted ratio to be less than or equal to this value. If Ratio is greater than this value, Ratio will be changed to equal it. Adjust RatioMaximum when your level has spots in which objects will bloom that should never bloom at all. For example, maybe a part of the ground has pebbles. If these pebbles have a great amount of contrast, portions may bloom and other's not. Sometimes this effect would simulate a specular bloom, which is good, and other times this just looks funny. In this event you can lower the ratio maximum until the pebbles stop blooming. (Altering the Ratio value is another solution that would give similar results without forcibly lowering the entire scene's maximum bloom)

### Dynamic Lights

Apparently, I was mistaken; manually triggered lights do work, only players with “dynamic lights” disabled won’t see them.

Find a **TLight** in the actor browser, set it up how you would like, go into **Properties → Object** and enable **Trigger Toggles**.

Add a tag to the light (like for a mover) and trigger it with a corresponding event. Build Lighting and you're a happy camper. However, shadows won’t be nearly as prevalent as they are for other lights.

Example:
In *KFO-Transit*, the first keycard door has a small red light that turns off and a green one that turns on.
In *KFO-Foundry*, you’ll also see something extra, a scripted trigger that spawns a **corona headlight actor** (a preset corona).

**Where you’ll find them:** somewhere in the Actor Class Browser, xd.

---

I kinda wanna recreate the stereotypical parking lot one day — flip a switch and all the lights turn on with loud sound effects, row by row (Bruce Almighty?). But I guess the shadows and lighting would self-destruct in this engine.

---

### Bonus Fluff

For fog, **FIRST disable TWI’s buggy override** — it’s a broken setting in Zone Info, so use **SPLevelInfo** instead:
![Guide Thing](GuideThing.jpg)

```
Note: This also stops zeds from spawning (only in the editor quickplay, not solo/live).  
If this is inconvenient, re-enable that feature in Edit → Level Properties:  
![Level Properties](LvlProperties.png)
```

Now you can place a Zone Info actor, enclose the “room” you want with zone portal brushes (link zone section), and go into:
`ZoneInfo Properties → ZoneInfo → DistanceFog = True`

Then in `ZoneInfo Properties → Distance Fog`, edit **color**, **fog start**, and **fog end**.

It’s mainly for optimisation outdoors, but many maps use it for lighting too. You can tint ambience, darken scenes (try dark grey `1:24:24:24`), but test thoroughly — it can easily look bad.

Also note: fog boundaries between rooms are broken (based on player location, not line of sight).

<details>
<summary>Spoiler</summary>
Ambient light is covered under **ZoneInfo Properties → Lighting**, but it looks ugly — best not touch it.
</details>

`// ProTip:` Every light looks a little ugly without coronas, but even in small rooms it’s overwhelming if every light has one.
This is where artistic vision comes into play — which lights should be most impactful?

`// ProTip 2:` While somewhat excessive, Ferenos knows what he’s doing with lighting.
You have to simulate at least basic reflections/diffraction with smaller light actors everywhere, otherwise shadows look way too dark.

---
