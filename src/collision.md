## **💥Collision**

So, bumping against meshes or invisible walls that prevents players from breaking your map, and jumping out of bounds…
This can be a minor thing to worry about. But it’s also **essential** to a player’s in-game experience, so don’t be fooled into ignoring it.

First, it’s important that YOU recognise almost all the meshes come included with their own collision already set up for you.
By going into *Properties > Collision* you can directly edit what they collide with and what they don’t, under limitations:

Well, that’s it. Set those properties to True/False as you wish and see fit. Simple.

But, what if you want to block off an area to players but not zeds? What if the collision on a static mesh just doesn’t cut it?
We can’t just have people going wherever they want. Specimen pathfinding in KF1 is already bad enough without players jumping across rooftops or wandering into their spawn points!
So this is when you want collision volumes.

> It’s important to recognise where you use these. Usually you should place a static mesh or platform of some kind to seemingly “block” off the player.
> But extend a blocking volume (NonZero Collision) much higher up than someone can be expected to jump.
> Otherwise I’d walk up to a perfectly normal piece of ground and hit an invisible wall, get frustrated, cornered by zeds and killed. Don’t. Break. Immersion.

So without further ado:

### Blocking and ZedZone Volumes

Yup, those are what you want.
If you’re familiar with the cube, cylinder builders and brushes then all you need is to mould the shape of collision you want, and instead of hitting subtract, look further down for a **translucent blue cube** tool and Rick/Click it. (image or vid or gif?)
This should bring up plenty of options but for this section I’ll just highlight these two:

* **Blocking Volume** — Blocks both specimen and players (all NonZero extent).
  ^By navigating to *Properties → Collision → Class Blocker*, you can block specific “classes” like KFMonster (Zeds) or dosh actors. (quick example?)
* **ZedZone Volume** — Blocks players but NOT specimen by default. Useful for spawn points.

If you want an example of how you shouldn’t misuse these volumes if you can avoid it, check out some lesser-known custom maps or KF-Stronghold in SDK.
Whereas not using them enough generally turns into something like this:

![Example 1](https://steamuserimages-a.akamaihd.net/ugc/1020572650860965922/71BCD87E9BD3DE7300C216CCCFE8CBCF94BC4B3F/)
![Example 2](https://steamuserimages-a.akamaihd.net/ugc/1026202797501704432/0F84C378580049CF1DADAF818E670BABED4E8DBF/)

---