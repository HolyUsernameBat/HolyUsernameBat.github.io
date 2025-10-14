## **🎯Triggers**

I'll keep this section brief, using the actor browser, you can select an assortment of triggers to use. Just bear in mind that not all of them will work reliably in KF.

Now that that's over, triggers are blatantly simple, go into actor class browser > trigger. And you'll find an assortment. I like things simple, so the ones I've stuck to (and coincidentally most KF mappers have used) so far are:
actor class browser > trigger > trigger > **KFProxyTrigger**
actor class browser > trigger > Use Trigger > **KFUseTrigger**

> Usage:
>
> 1. Place it where convenient, if it's a KFUseTrigger, place them centrally in the door and a ProxyTrigger would be on or next to something important in your level.
> 2. **Go into properties → Events**, name the *event* of the trigger something simple and explanatory that you won't repeat ('Door1A' for example).
> 3. Make your trigger actually do something by giving your lucky chosen actor or mover (The Target) a *Tag* of the same name ('Door1A').
> 4. You're done. This can be used to play *sound effects*, activate a *scripted trigger*, complete/activate objectives and it works for movers with the corresponding Tag too.

–––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––

Rick / m2 on the border of your **3D viewport** -> **Actor** -> **Radii view**.
This brings up a red radius of your trigger's range, which is most useful for the KFProxyTrigger. The radius of a trigger can be edited in **properties -> Collision -> collision radius / collision height**.

–––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––––

Side Note: plenty of actors like movers can trigger events as they do their thing (look into sections of their properties), if I went into all of them it would be a pretty extensive and boring guide but just understand they work the same way. The trick is using them to link to different tags and cause "events" in a variety of different ways.
e.g. a given alarm sound effect event, triggered by a door opening.

SideSideNote: If there was a third trigger I'd like to learn how to use someday it would be the shoot trigger. It does work (KFO-RE-Mansion and KFO-WestLondon use one) but it looks finnicky so good luck.

4thSideNote (credits to ST): **KFMusicTrigger**. You can copy it from another custom map just to get an idea of how it works. Vanilla maps don’t use it.

---
