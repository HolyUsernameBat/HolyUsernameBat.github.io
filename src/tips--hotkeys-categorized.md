## **🧱 Tips & Hotkeys (Categorized)**

How could a guide named **“SDK General Tips”** not have a section on tips!

### I. Stability & Setup (Essential Fixes and Downloads)

* **Save copies often.** The software *will* crash.
    ↳ The SDK is way more resource-heavy than the game itself, which makes it super demanding on your PC.
    If you’re getting memory crashes: **Lower the graphics in-game** to reduce them.
* **Log Viewer:** View → Log. Keeps track of SDK errors and warnings — super useful for debugging.
* **Autosave:** SDK keeps *10 files* from the last 2 hours in your maps directory, named `auto0` → `auto9`.
* Steam's KF SDK permanently jacks gamma up pretty high. Fix = add **-nogamma** to Steam game properties -> launch options. Alt Fix = Manually open KfEd.exe file.
* Change `KFEd.exe` compatibility mode for better stability.
* Try **800x600** resolution to fix cutoff UI windows.
    [previewicon=35503155;sizeOriginal,inline;KFEdCompatibility.png][/previewicon]
* **4GB SDK (KFEd)** – removes RAM cap.
    👉 [Download](http://sirentorturers.site.nfoservers.com/downloads/KFEd-4gb.zip)

***

### II. UI Navigation & Workflow (Time-Savers)

* **Ctrl + Alt + M1** = Selection box *(only in top/front/side views)*.
    //ProTip: Try combining with *SuperTip3.*
* A lot of stuff can only be moved/interacted with **while holding Ctrl** — try that if you’re stuck.
* **Texture Info:** Right-click a wall/surface → `Properties` → top of window = texture name + path.
* **Actor Info:** `Properties → Display → Mesh` shows the *name + directory* of a selected actor (static mesh).
* **Apply Skins:**
    `Display → Mesh → Skins → Use` lets you apply graffiti or overlays on existing meshes (like grime/glass).
* Obvious in retrospect, but for *graffiti or reskinned meshes*, don’t forget this boolean:
    [previewimg=35573290;sizeFull,floatLeft;graffitiTip.png][/previewimg]
* **Big maps = laggy editor.** Use orthographic views (top/side/front) to edit more efficiently. When using the 3D view zoom in to render as little as possible
* **Ruler Tool:** **Shift + MMB**. I'm overzealous because I wasted years of my life counting tiny squares.
    👉 [Extra Tricks Thread](https://forums.tripwireinteractive.com/index.php?threads/a-few-tricks-ive-learned-killing-floor-sdk-tips.46360/)
* **Shift + D > Copy + Paste.** Always.
* **Selection Time Savers (be smart):**
    [previewimg=35383871;sizeOriginal,floatLeft;Select.png][/previewimg]
    [previewimg=35383873;sizeOriginal,floatLeft;InvSelect.png][/previewimg]
    You can also select *all actors of type*, *all adds/subtracts*, *all brushes* or *grouped actors* via the Group Browser.
* **Reveal All Hidden Actors:**
    Use this tool: [previewicon=35503135;sizeThumb,inline;ShowAllActors.png][/previewicon]
* You can right-click the *viewport headbar* to customize visibility:
    [previewimg=35503112;sizeFull,floatLeft;SDK ShowCustomisation.png][/previewimg]

***

### III. Niche Tips / Advanced Fixes (Technical Workarounds)

* For *really tricky* BSP holes:
    Rick-click the problem brush → Type → **Convert to Semi-Solid / Non-Solid (+ Blocking Volume)**. You can also try **Build Options → Lower BSP Cuts**.
threads/static-mesh-import-errors.113852/)
* **Test specifics regularly.** Most issues aren’t visible at first glance.
* **Slippery floors:**
    👉 [Forum Tip](https://forums.tripwireinteractive.com/index.php?threads/how-do-you-make-slippery-floor-in-kf.56290/)
* **Be wary of scaling static meshes**, it creates duplicates in `myLevel`. Discussed in **Optimisation**.
* **KFUseTrigger** only works with doors:
    👉 [Proof](https://forums.tripwireinteractive.com/index.php?threads/kfusetrigger-to-activate-scripted-trigger.113151/)
    Use Trigger, ProxyTrigger or Mover → MoverEvent instead.
* **Launch Pads / Knockback FX:**
    👉 [Forum Guide](https://forums.tripwireinteractive.com/index.php?threads/launch-pads.51938/)
* **Custom Lobby Camera Setup for your map:**
    👉 [TWI Forum Tutorial](https://forums.tripwireinteractive.com/index.php?threads/setting-up-the-lobby-camera.110362/#post-2019092)
* There is a hard limit to actors such as lights/navigation points lmfao. all are capped at ambiguous large values. Compare yourself to big story maps like *KF-Hive* to stay safe.
* **Tripwire Oversight (Also mentioned in 'Lighting'):**
    > ST’s Broski explains how color correction is borked and how to fix it:

    > [previewimg=35350377;sizeFull,floatLeft;GuideThing.jpg][/previewimg]
    Original Post (by Siren Torturer's Broski):
    "There is code to disable KF's color correction in the standard KFLevelRules, but due to a typo (KFLevelRule.) and an oversight in KFLevelRules code (its missing this boolean entirely) It's not usable. And the color correction options in ZoneInfo does nothing. Same exact code.

    Welp, turns out, there is one thing that actually has the code for it still. The story mode actor. And it works. And it has MASSIVE impacts on how maps look.
    You can more accurately use different themes of lighting.

    If you want to see how massive of a difference this makes, drop KFSPLevelnfo () in a default map and set levelInfo->bUseVisionOverlay to false."

***

### IV. Community Advice & Resources

* Unless you have custom texture/mesh packages, always say no to tea (**Never save myLevel**).
    [previewimg=35572203;sizeFull,floatLeft;Package.png][/previewimg]
* **Asset Naming Conventions** (the decent kf creators used back in the day):
    👉 [Version mismatches & you](https://forums.tripwireinteractive.com/index.php?threads/version-mismatches-and-you.80355/)
* **Study official maps.** They know what’s stable and well-optimized.
* Maybe look at this for extra SDK functionality (Be v careful unrealed.ini sensitive lol): https://forums.tripwireinteractive.com/index.php?threads/customizing-popup-actor-list.101481/
* Don’t even *touch* this cursed SDK without good music or a podcast.
* **Holy Grail of BSP Basics:**
    [▶ YouTube Video](https://www.youtube.com/watch?v=0s9TTUZ48pQ?si=MRuGYagGGTmLB0CC)

***

### V. Hotkeys (Table Reference)

| Key | Function |
| :--- | :--- |
| Q | Toggle BSP |
| W | Toggle Static Meshes |
| O | Toggle Volumes |
| F | Toggle Distance Fog |
| H | Toggle Actors |
| B | Toggle Builder Brush |
| Ctrl + W | Align BSP Textures |
| Ctrl + S | Subtract Tool |
| Ctrl + A | Add Tool |
| Shift + L | Apply texture to all selected surfaces |
| F8 | Build Options *(always use RGB8 lighting)* |

Extended list:
👉 [UE3 Hotkeys](https://docs.unrealengine.com/udk/Two/UnrealEdKeys.html)

---

---
