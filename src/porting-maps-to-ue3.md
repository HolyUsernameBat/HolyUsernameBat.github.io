## **🧱 Porting Maps to UE3** 

UE3 includes a polygon limit when importing maps lol.
**65535** of them to be exact.
So—batches, batches, *batches.*

And ofc you can check out this [TWI forum post](https://forums.tripwireinteractive.com/index.php?threads/wip-kf-dd-tavernsiege.2277096/#post-2277504).

> The process of porting games can vary a lot depending on what game it is and what engine it supports. Preferably games that have a Modding kit supported like an SDK, Hammer, etc.
>
> In short:
> For **Dungeon Defenders**, I grab all the assets related to the map I want to work with in DD’s DDDK and move them into a custom new package.
> Moving assets instead of copying will auto-assign MAT directory references to the new package.
> Just **do NOT save** the package changes from the game’s default UPK packages.
>
> Dungeon Defenders is built off an older version of UDK (UE3), so it’s a bit easier to grab similar MATs/Textures/UPKs—but the procedure’s the same.
> Categorise everything you grab or you’ll lose progress *fast*.
>
> Since **KF2** is built off a newer and heavily modified version of UE3, it’d be nice if we could just grab the packages and load them in, right?
> *Yeah nah.* KF2 SDK will crash with a **crap ton of errors** — UPK structure mismatches, bad mesh renders, particle FX crashes, etc.
>
> The main culprit? **Old mesh renders.**
> You’ll need to extract the UPK raw, grab the PSKX, import it into 3DS Max (ActorX plugin), and export it as **FBX (2014/2015)** — that’s **critical** for KF2 SDK or it *will crash.*

Once you’ve packaged everything, build your map slowly.
Export selected meshes from DDDK as a **.t3d** file so they auto-place correctly in KF2 SDK.
If it crashes? One of those meshes is bad.

This is why you import **a few at a time**, not all at once, unless you enjoy watching the SDK implode under memory allocation errors.

After that, rebuild all the usual stuff — **Lighting**, **Pathing**, **Volumes**, etc.
Porting isn’t easy.
It takes *patience, stubbornness, and caffeine*, but it’s rewarding in the end.

---

Alternatively, there’s a slightly more efficient method.
**For all further advice/tutorials — massive thanks to [Steven](https://steamcommunity.com/id/KlLLMaster/).**
Join the **[KF Modders Discord](https://discord.gg/rzNpaD3)** for support.

📄 **WordDoc Tutorial:**
[https://1drv.ms/w/c/27e2d51aa2ebaadd/EdVUVo-W0XZPrTVYohFBNUgBqv3IWB--7woFLt2rDCmICQ?e=apbd7e](https://1drv.ms/w/c/27e2d51aa2ebaadd/EdVUVo-W0XZPrTVYohFBNUgBqv3IWB--7woFLt2rDCmICQ?e=apbd7e)

▶ **YouTube Video:**
<iframe width="560" height="315" 
src="https://www.youtube.com/embed/sVbDvROecKA" 
title="KF1 - Map Export" 
frameborder="0" 
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
allowfullscreen>
</iframe>

---

**Notes:**
*(Space for future updates.)*

---
