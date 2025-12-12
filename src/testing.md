## **🧪 Testing**

Testing is **Hella Important**. If you release a map you haven’t tested, it’s garbage. 100%.

What’s more, if you don’t have any friends (:c), you’ll probably be relying on solo testing for now and that’s fine.
Up at the top of SDK there’s a game controller icon for quick tests, and it’s great for hopping in there on a whim.
But for important times, testing directly in a **Killing Floor → Solo** game is ideal because of two reasons:

1. You can easily apply different **mutators** like *fakedplus* to check spawn scaling in your map. *(Balancing your map is important!)*
2. You’ll be playing at perk levels that are familiar to you.

> **Tip:**
> Be a neat-freak **and write down notes**, change things up too. You’re testing, not playing Biolabs.
> Swap perks, hold spots, observe.
> Once you near release versions do **bump-tests** as well, walk along walls and railings to see where u get stuck. Can you fix it with blocking volumes?

---

### Server Testing 🌐

If testing in-game is 50% better than testing via SDK, then **server testing** (in private servers ideally) would be *300% better*.
If you know how to set up a local dedicated server, go for it. Learn how port forwarding works, whatever.
If you have friends, nag them and test together! They’ll grow to hate you… Muahahaha.

Anyway, server testing is so brilliant because:

1. Some bugs only appear in dedicated servers.
2. Assuming your map is successful, 90% of players will play it on a dedicated server anyway.
3. It automatically checks for compatibility issues with common mutators in use (rare but possible).
4. You’ll experience your map with a team.
5. People who test there WILL nag you, issues with collision, spawns, pathing, whatever. It'll all pile up on top of you.

> 📦 **Recommended Resources:**
>
> * [Server Setup Guide](https://steamcommunity.com/sharedfiles/filedetails/?id=3053854807)
> * [48hr Free Server Trial – PingPerfect](https://pingperfect.com/gameservers/kf-killing-floor-game-server-hosting-rental)
> * [Cheap VPS Hosting – Contabo](https://contabo.com/en/vps/)

---

### Testing with Bots 🤖 

Anything else about how you test is up to you, but for the loners or considerate ones out there, I’d specifically recommend this mutator:
[https://forums.tripwireinteractive.com/index.php?threads/mutator-kf-bots.44969/](https://forums.tripwireinteractive.com/index.php?threads/mutator-kf-bots.44969/)

^*Extract in Killing Floor → System Folder*^

These bots aren't as dumb as official ones so learn how they work, use them, and most importantly have fun!

---

### *Relevant Console Commands*

Open up the console in game and there're some handy game commands for testing things efficiently, or debugging, in solo or as a server admin. Listed here:

> *enablecheats - greylists the game and allows the next few cheats.
> *loaded - Gives infinite ammo.
> *god - You won't take damage (same command to disable god mode).
> *fly - self explantory.
> *ghost - fly and no clip through everything in game.
> *walk - Get out of fly or ghost mode.
> *slomo2 - run the game in 2x (number customisable) speed.
> *causeevent 123 - Trigger any event of any name (123 in this example).

---

### *Custom Commands:*

> *HugeGnome - collectibles go about 20x bigger
> *MopUp - killzeds but pastes number of zeds in console.
> *Arsenal - gives all weapons.
> *FreeCamera - Doesn't really work for me so might be broken.
> *ViewSelf - how to UnFreeCamera I would imagine.
> *Backup - spawn bots.
> *Horde - spawns random zeds (maybe useful for testing pathing from volumes without waiting for higher wave or before designing waves in KFO).

If you’re struggling to open the console… **git gud.**

---
