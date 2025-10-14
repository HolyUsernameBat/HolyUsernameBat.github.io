## ☁️ **Zone Info** *(Sky, Terrain, Fog)*

Hi,

If you're starting with KF SDK mapping I recommend not touching the zone info actor at all, since it can cause issues (**Edit: Those issues are mostly due to TWI, consult SuperTip1**)
So grab your actor from Info? -> ZoneInfo..

> In short: ZoneInfo is an actor that lets you **edit the properties of a “zone”** in your map. A zone is any enclosed space you’ve cut off from others with **portals**.
> (Portal usage discussed in Optimisation LINK; They are hidden actors, not to be mistaken for teleporters, (although they technically can function as one it's not at all seamless lol))
> If you don’t add ZoneInfo, the game just applies default settings to the zone/area.

---

### ✨ Why Even Bother?

There are technically a bunch of reasons. Controlling ambient brightness, setting up multiple skyboxes, or applying universal mesh cull distances — but since UE2 is a *temperamental baby*, I’d just use ZoneInfo for three things:
**terrain, skyboxes, and distance fog.**

---

### 🟩 Terrain

If your terrain isn’t showing up in a certain zone, you’ll need to set the property **ZoneInfo → terrain zone = True**.

Now, even if your terrain cuts through other zones (through an entranceway or cave maybe), it’ll render properly there.
Without? Invisible. Non-solid. No more need to smash your keyboard.

---

### 🌌 Skyboxes

A **skybox** is an isolated room that provides a live 360° camera feed of the sky around your map.

To make one work, insert the ZoneInfo child actor:

```
SkyZoneInfo
```

Sounds kind of like what Skyfall is for James Bond right?
This is the *camera* for your skybox. Once you’ve built and positioned it inside the skybox, you usually don’t need to tweak its properties. Yay! 🎉

<details><summary>Spoiler</summary>
The “camera” is just *really zoomed in*… so have fun with that :)
</details>

---

### 🌫️ Distance Fog

Yep. it’s exactly what it sounds like.

Enable with:

```
ZoneInfo → DistanceFog=True
```

Then tweak:

```
DistanceFogStart
DistanceFogEnd
DistanceFogColor
```

A smaller gap between Fog Start and End = thicker fog.
You can even set a *negative* Start value if you want to get creative.
And for colour (yes, colour, not color), use byte values **0–255** for hue, saturation, and brightness.

---

### 💀 KillZ (Don’t)

If you somehow end up with a massive void under your terrain, please **don’t** rely on:

```
ZoneInfo → KillZ
```

Sure, it’ll kill anything that falls below a certain Y coordinate… but I wouldn’t trust it.
Use **vertex editing** or a **KillVolume** (or both) instead. KillZ is a last resort for desperate mappers watching zeds sink into the abyss, eating performance as they rave it out beneath your map. 🙃

---

### ⚠️ Known Hiccups

Translucent meshes can block emitters and other translucent materials in your skybox when viewed through BSP — especially fog or clouds.
There’s no known fix (thanks, UE2). So test early, preview often, and maybe the SDK gods will bless you.

---

*That’s all folks (for this section)* 👋
...

---
