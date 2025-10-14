## **🐞 Known Errors**

Things to look out for:

* Uninstalling KF SDK wipes all of your Killing Floor mutators (and binds). So erm...
  **Don’t Do That** xD

* Selection Delay is a UE2 issue due to modern GPUs, discussed here:
  [https://www.vogons.org/viewtopic.php?f=59&t=90041](https://www.vogons.org/viewtopic.php?f=59&t=90041)

* Selecting surfaces specifically has an even more ridiculously long delay.
  ***Zoom in and ensure the Editor is rendering as little as possible in the viewport.***

* Not really an error but KF hates spaces in imports so **NEVER** add them, especially for sounds (`.uax`).

* The config for saving Build settings is borked, and if you do it manually through `UnrealEd.ini` it breaks the editor (**BIG TIME so don’t ever lmfao**).

* **Static Mesh Limit:** Meshes exceeding **22,000 triangles** will warp.
    👉 [Static Mesh Import Errors](https://forums.tripwireinteractive.com/index.php?

* Modern 3DS Max and Blender 2.81+ have never successfully exported a SM into KF1 with multiple UVs/materials for me (I remember hearing it was an issue somewhere too).

* For broken build/terrain menus try the advice discussed here:
  [https://forums.tripwireinteractive.com/index.php?threads/solution-glitched-terrain-editor-menu.55403/](https://forums.tripwireinteractive.com/index.php?threads/solution-glitched-terrain-editor-menu.55403/)

* If you use textures or resources from the workshop or modded content, and send the map file for testing without including those resources — testers won’t be able to view the map in game as the title won’t appear at all.
  ***If this is causing issues you can ask a friend to open the map file in SDK, and it will give a detailed error report about which resources are missing, so you can narrow down your search.***

* If the map won’t appear in the Killing Floor map list, the most likely reason is because there’s a disallowed character in the map name (such as `"."`), or it doesn’t have a KF/KFO prefix.
  *(Another reason might be a dependency, so try convince yourself/them to monitor log real-time as they open the file in SDK.)*

* The Undo (`Ctrl+Z`) action is restricted, and can cause crashes when reverting projector movements.
  ***So be sure to save often if you use it anyway like I do ;D***

* Projector textures also tend to multiply their alpha values (by like 1–10%) with every build, eventually becoming completely transparent.
  ***Idrk what to do aside stay aware.*** I literally have to hop in game to see & adjust their position + scale lmfao.

* Animated decorations work sometimes (even on servers) but also stops some from loading the map at all (crashes SDK too). I think there’s a dependency somewhere that I need to find — although it works in KF-Foundry lol, maybe I’m stupid.

* Scale map / brush operation crashes SDK (unsurprisingly). **Just use vertex editor.**

* The grid alignment often breaks **if you consistently use BSP dimensions that aren’t powers of 2** (especially at sizes 1000+), or more often switching between grid 1–2 (often while something in grid 1 is still selected).
  This means brushes may place themselves in between grid lines, or suddenly gain (non-existent) width in the top/side/front views.
  **If you insist on using grid 1 for meshes (like I did/do a lot), make it a religious habit to always deselect the mesh before switching back to grid 2+.**

* Delay time can’t be properly edited with KFDoorMovers.
  ***Fall Trigger Pack’s DoorMoverPlus doesn’t fix this, or maybe I’m just that bad so meh...***

* Ordinary Movers, and routes movers take, can break KF specimen pathing. Whereas KFDoorMovers don’t (in my experience).
  ***Prob because path collision is enabled in Properties → Collision by default, so if you insist on using massive movers go ahead and set that to `False`.***

* There’s a hard limit on the effective number of portals and path navigation points.

* If you change to a language (like to Russian), RIP. I’ve noticed that it breaks UI Booleans such as True/False functionality feature in properties. Might just be if you download SDK then switch but may even be the same for other languages so ***gl hf.***

* I heard through the grapevine workshop has a 100 MB upload limit (don’t quote me on this, your map shouldn’t be getting that big and workshop sucks anyway, we all use manual DL links xd).

* KF SDK can cause you to run out of virtual memory from time to time, ***so be sure to hit the save button before closing the pop-up. At least use the basic hotkeys to toggle visibility, and reduce your graphics settings.***
  As it does auto-crash the software.

* Let’s not forget the most important error: why am I publishing a KF SDK guide in 2020?
  Well... **WHY THE HECK NOT!**
  *More like I’m disgusted at the lack of them, so who knows. Hopefully at least 1 person finds this useful.*

---

