## **🧱 Build and BSP holes**

So, there's something you need to realise about how KF SDK works:
The build button at the top right of your screen re-builds the whole map every time you ask it to, following the set of guidelines you give it.

Well duh. But this includes every brush you've ever added or subtracted.
Go into wireframe by clicking the hollow cube icon above your 3D viewport and you'll even observe any old brushes you may have 'added' over.

So to sum up, you can use a "brush" that **applies an effect and continues to persist even after you add or remove space with more brushes. Like a skeleton of sorts**.
To get fancy, this means when you edit a wall, you aren't moving the wall itself; you are moving the original, invisible brush primitive that created that wall. Now onto the juicy parts!

---

```
**<u>How can I use or abuse this feature</u>**?

Simple, this means to edit the walls and structures in your map, you only need to go into wireframe:

• Move a brush anywhere you want if a wall is in the wrong place.  
• **Ctrl+C, Ctrl+V to copy walls/floors (or Shift+D to duplicate, thank me later)**.  
• Perhaps even delete the brush entirely to redo that given space.  
• Rotate the brush as you please using the actor rotate tool.  
• Or go into Properties -> Brush, and change the brush type to add or subtract.

**All you need do is hit build geometry, or build all afterwards** to watch all those surfaces get remoulded as you please. Cool right?  
*Now to think it took me 250 hours to figure out how to copy-paste a corridor, lmao ><*
```

---

### General Build Scale

It's worth noting these examples of absolute minimum height dimensions:
• Standing Player - 108 units.
• Crouching Player - 76 units.
• Crawler - 56 units.
This chap has obtained slightly different (likely accurate) figures:
[https://steamcommunity.com/workshop/discussions/18446744073709551615/4520009742919820869/?appid=1250](https://steamcommunity.com/workshop/discussions/18446744073709551615/4520009742919820869/?appid=1250)

Info such as this is handy to me when working on small sections but we should also use it as a scale.
216 = twice a player's height for example, so that would be an ok roof height.
You don't even want to know minimum width because pathing just fails at these sort of dimensions so go 200+ :P

**Honourable Mention:** In regards to UE light-mapping it's directly tied to BSP brush size, so while it’s more optimised sometimes 1 big BSP brush isn't the answer.

---

### Patching up the map (BSP holes)

BSP holes, you may have seen them, you may have heard of them.
Tbh it got me so worried I almost gave up on a project.
See the dark screenshot below? They're simply holes in your map.

![Screenshot Example](https://steamuserimages-a.akamaihd.net/ugc/1665735725524539471/6AED5E9A0FCD2E3E627EF5A3FC500AB06B08617B/)

---

### CAUSE + SUMMARY

Happens when the editor gets confused by **overlapping brushes**. The best solution is prevention…
First, always always **always** grid 2+

> Second, if you want to create irregular shapes / transit style stairs -

[▶ YouTube Video](https://www.youtube.com/watch?v=PbhLoQxazgY?si=eSAY5VMbxpXMi46K)

**OR**

[▶ YouTube Video](https://www.youtube.com/watch?v=0s9TTUZ48pQ?si=neeFTb1dz8sL0zBW)

**OR** Vertex Editing (see guide section)

This tutorial also seems to have some juicy details:
[http://www.hourences.com/tutorials-ue1ue2-bsp/](http://www.hourences.com/tutorials-ue1ue2-bsp/)

A BSP hole won't show up every time you overlap BSP brushes.
In layman terms it's like Schrödinger's cheese — you can't cut into a part of cheese that you've already cut away, and you can't fuse different cheese molecules together.

BSP holes also tend to work in either x-y-z planes (with some deviation).
So the hole is not always adjacent to the cause.
My best explanation would be invisible tears in space (so yes, you're breaking physics, unless it's quantum entangled cheese, yum).
You may have created the BSP tear/hole years ago and made a super map since then!
Sometimes you're just unlucky and you tap into that tear. :c

---

### WHY DOES IT HAPPEN EVEN WHEN I DON'T OVERLAP BRUSHES

You are overlapping brushes, fractionally sized. The Editor is a [redacted insult] like that.
It should auto snap brushes on grid when the setting is enabled *(little grid icon at bottom)* but going in and out of grid 1, while working with brushes, can confuse it.
I think it breaks brush dimensions or pivot, and because UE2 is only capable of snapping a single brush vertex on grid at a time, it's stubbornly persistent.

Otherwise building fancy brush constructs with steep vertex editor angles, or freehand polygons can also do it.

---

### FINDING THE BUGGERS

The best way to locate BSP holes is the **portal view**.
Since BSP holes cut open the map they also split zones into fractions and you can see the change in colour, then **switch to wireframe** and there should be an overlapping BSP brush nearby in the x, y, z plane.

---

### CORRESPONDING FIX

You shouldn't get to this step, prevention is key.
If you're here anyway first ask **Do I Fix It?**
It's only a BSP hole if you see it.

Those wormholes dynamically change as you fix them if you've got a whole hive of them too (or new ones apply during build), so **at least keep track of file versions**, and if it's tiny or out of sight you can leave it alone…

Otherwise, if all brushes are still on grid ensure you perfectly line them up **surface to surface** or **re-scale** one for your purpose while deleting the other.
If your brush is on a half-grid or less, consider converting it into a **static mesh**, **Brush → Type → SemiSolid or NonSolid** through a right click.

Alternatively, your last resort is **Vertex Editor**. *Consult Guide section to enable grid snapping.*
You can then right click off-grid vertices in the 2D viewports to snap them on grid (credit: Broski).
It’s a last resort because the editor will just snap a different vertex off grid, so you're going to share in the trauma of spamming it over and over again.

You can also try typing `actor align` in the command box, or **Edit → Reset → Brush → All**,
but it's not as reliable.

*Consider using Ctrl + Middle Mouse Button to draw a ruler in 2D and just **replace the brush entirely** (assuming your builder/red brush is fine).*

*Remember you can check portal view which is good for spotting BSP holes and their causes.*

---

### Wider Community Tips

*In summary - act like a neat freak when designing your map, **Grid 1 is officially the plague**, and keep those file versions handy.
That way even if you do see a BSP hole it won't be as complicated and you can probably revert the file anyway.
Otherwise auto-save and go into portal view, then wireframe to find and edit the spot where you messed up.*

![Screenshot Example 2](https://imgur.com/PbYd14m.jpg)

```
// ProTip1 - Static meshes aren't BSP, so they will never cause a hole, and are a better option for decorations 99% of the time.
// ProTip2 - If a static mesh won't work, for example if good lighting on that decoration is important, consider using a semi-solid brush or non-solid + blocking volume via special brush tool, and then consider BSP last of all.
// ProTip3 - If a simple wall can be made with 2 large BSP brushes rather than 8, it can be better but I mention in Lighting that lightmapping is based on BSP size so keep cuts equally-ish sized if you can. Vertex/2D shape editing are still amazing tools.
// ProTip4 - Pick a big grid size that 90% of your map's BSP will be in, like 32 or 64 ish, and work in multiples of that number. You may be forced to make an exception at doorways by halving it but keep the rest as is.
```

---

