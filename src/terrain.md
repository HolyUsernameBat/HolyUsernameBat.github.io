## **🏔️ Terrain**

### *Getting it to Work:*

When adding terrain to a map, first thing you want to do is follow this here URL:
[https://docs.unrealengine.com/udk/Two/CreatingTerrain.html](https://docs.unrealengine.com/udk/Two/CreatingTerrain.html)

> **Summary:**
> It’ll say you need a “room” closed off with zone portals (or just a room on its own), and then put a **ZoneInfo** actor inside there.
> Go into ZoneInfo → Properties → mark the zone as **TerrainZone = True** *(without this step your terrain will never work)*

Then you should first pick a texture you want for terrain, highlight it, then click the terrain tool on the left side of your screen → **make new terrain** (the little new page icon).
Then label your new terrain (heightmap texture) as you like, in the *myLevel* package.
This will make a **TerrainInfo** actor where your camera currently is…

Next stay on the terrain tool → GoTo “Layers” tab → make new layer (new page icon on the right side this time).

It’s explained in that URL that you should leave properties of the new layer as default, but one thing that KF REALLY loves to do is set “**U Scale**” and “**V Scale**” to 0 by default when you make the new layer.
^This is the scale of your repeating texture applied to terrain, so it should absolutely **NOT** be set to 0. Otherwise, your terrain will work but appear invisible D:<

---

### *Moulding Terrain:*

If you follow that advice, your terrain will work and appear in the map.
Now you can start playing with the terrain tools explained here:
[https://docs.unrealengine.com/udk/Two/EditingTerrainMaps.html](https://docs.unrealengine.com/udk/Two/EditingTerrainMaps.html)

> **Additional Notes:**
> I usually use paint brush (followed by smoothing) because it’s easiest.
> Set strength to a little under 50,
>
> * Ctrl + Left Click (M1) to paint mountains/hills,
> * Ctrl + Rick (M2) to carve valleys.
>   If you make a good hilltop but it’s too small, you can try selecting it all with vertex edit (Ctrl + M1, then Ctrl + M1 + M2), shifting your mouse upwards — this raises all terrain nodes, so you’ll then need to go into smoothing + paint to fix transitions.

This is when you should be practicing terrain shapes a LOT and my God I hate it, it’s always *10× laggier* than normal SDK and crashes *3× as much.*

---

### *TERRAIN USER/BUG FIXES (FOR EMPHASIS) 🚨*

When getting terrain to work, your **TerrainZone** setting in ZoneInfo actor should always be set to **True** like this:

![Terrain Zone Example](https://imgur.com/iauvvpR.jpg)

And your **TerrainInfo actor → Properties → TerrainInfo → Layers → Layer 0** MUST have:

* An applied texture for the terrain,
* A heightmap AlphaTexture for that layer (SDK updates this automatically)
* Positive values for **U Scale** and **V Scale**, like shown below:

![Terrain Info Example](https://imgur.com/WDVWiBS.jpg)

If your terrain is built, you’ve followed the previous steps, and it’s still invisible — go into your **terrain tool**, select your layer under the Layers tab, select “paint,” and paint the texture of your layer onto the terrain with **Ctrl + M1.**

---

### *Terrain Layers:*

After you’re happy with your terrain shape, you can apply different texture layers that blend into each other by looking at this link:
[https://docs.unrealengine.com/udk/Two/EditingTerrainLayers.html](https://docs.unrealengine.com/udk/Two/EditingTerrainLayers.html)

As you can see I rely on UDK Two Site Map a lot because it’s usually accurate to KF SDK.

To do:
- Deco layers... Anyone reading can just reference UDK-Two for now.

---
