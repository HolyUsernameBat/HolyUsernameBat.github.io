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

### Dynamic Lights

Apparently, I was mistaken — manually triggered lights do work. Only players with “dynamic lights” disabled won’t see them.

Find a **TLight** in the actor browser, set it up how you would like, go into **Properties → Object** and enable **Trigger Toggles**.

Add a tag to the light (like for a mover) and trigger it with a corresponding event. Build Lighting and you're a happy camper. However, shadows won’t be nearly as prevalent as they are for other lights.

Example:
In *KFO-Transit*, the first keycard door has a small red light that turns off and a green one that turns on.
In *KFO-Foundry*, you’ll also see something extra — a scripted trigger that spawns a **corona headlight actor** (a preset corona).

**Where you’ll find them:** somewhere in the Actor Class Browser, xd.

---

In *KFO-Foundry* they use scripted triggers to activate/spawn a headlight corona **Actor** based on an Event, usually triggered after the bonus objective is satisfied.
Learn how to do that and your trigger lights will look prettier :P

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
