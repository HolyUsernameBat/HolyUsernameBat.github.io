## **🧟 Spawn Points (Zombie Volume)**

For setup...
Similar to BSP, first **arrange the size + position of your active (builder) brush**. Then rick this tool to select your volume.

![Zombie Volume Properties Preview](https://images.steamusercontent.com/ugc/2411187472718903340/1D1E73FCCDA65BBC068C752D2EAD2C892CC734F5/)

Following on, unless you’re making a KFO map (**don’t xD**), leave the **Tag** alone and focus on
**Properties → ZombieVolume**:

![Zombie Volume Properties Panel](https://images.steamusercontent.com/ugc/2411187472718911553/E35E31A6C19819E4FCB9A475056E2BAA0F4CF9FB/)

---

### Custom Stuffs:

By default it works perfect, but there’re **5 properties** here I’ve edited for extra functionality:

**1. AllowPlainSightSpawns**
I’m only ~80% sure the code works, but enabling it never hurts during setup/testing.
I have it enabled in the final release because spawn volumes are rubbish at recognizing SMs as sight blockers **and** I know this spawn is always hidden from player view anyway so it’s mostly a precaution.

**2. MinDistanceToPlayer**
Self-explanatory ofc, this is the minimum distance (in straight-line x,y,z) between the ZVol and Player before proximity disables that spawn.

**3. NoZAxisDistancePenalty**
As mentioned in the actor’s script, this ZVol won’t factor height (y) as a disabling distance.
I have it enabled in this example because the zeds drop from a very high location.

**4. SpawnDesireability**
KF runs its own algorithm to decide which spawn gets priority (usually distance-based).
This property lets you influence that behavior.
Default is around `3000` — I might raise it to `4000` for neglected spawns during testing, but rarely go below default.
Take care, but experiment ofc. **Balance is important.**

**5. OnlyAllowedZeds**
It's self explanatory I simply wish to emphasise it works. No broken TWI code here xD
My example volume is small, but big enough for Stalkers :p
Sometimes I disallow Bloats if the pathing is bordering blue coloured.

---

💡 **Pro Tips:**

* Routes from ZVolumes should always be **green**. specimen are sensitive after spawning and need wide paths.
* Partial distance fog (even if not opaque!) or **blocking volumes** count as LOS blockers if visibility is a problem for spawns.

---

```
### <u>*Problems?*</u>
- Rick your viewport headbar -> view-> paths to make sure your path hasn't deleted itself (it happens).
- Increase CanRespawnTime (3.0 should be good absolute minimum).
- Use Default values for other settings such as SpawnDesireability.
- Use Vertex Editing to expand your ZVol (+room).
- Use Sightblockers or compress your ZVol (assume bAllowPlainSightSpawns doesn't work).
If problematic you can then explore force path as an option (discussed in pathing).
- Ofc if bored of debugging building a new volume very often works for me.
```

---
