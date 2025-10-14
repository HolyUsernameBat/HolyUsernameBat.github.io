## **🧩 Vertex Editor**

The Vertex Editor tool is way better than I originally gave it credit for (sorry).

**FIRST**, vector snap must be turned on:
![Vector Snap Screenshot](https://images.steamusercontent.com/ugc/2411186208092859423/3AC4B992E4395561262AD38F4DFA26FD5062071A/)*

---

**Hypothetical:**
Your existing BSP brush is too big, or shaped too regularly to pair with a different room or static mesh.

**Use:**

• Select brush.
• Ctrl + alt to drag select (not in 3D viewport :c) or Ctrl + click to select 1 corner/vertex.
• Ctrl + alt + shift to stack and continue selecting more vertices.
• Preferably use 2D viewport to edit the dimensions as you wish so use hide actors for extra visibility as mentioned in tips.

> ⚠️ **Warning:** As mentioned, don't go crazy with angles, and **NEVER** turn off vector snap or you can rightfully embrace BSP holes and fall through the gaps between dimensions.

---

**Bugs (if working with triangular BSP):**
![Triangular BSP Bug](https://steamuserimages-a.akamaihd.net/ugc/2411186841874352496/219BC661D052D89F38B1AEBCC290C75F70AB5F74/)

You can see this is likely related to jagged primitive collision, one solution in a similar case might be to break down the BSP into further horizontal subdivisions, I think I just remapped the pathing so they jumped outwards from each pillar, as opposed to in-between.

---
