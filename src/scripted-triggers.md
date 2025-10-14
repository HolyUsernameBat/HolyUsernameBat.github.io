## **⚙️ Scripted Triggers** 

These handy little things are scary, but simple — and you can find them in the actor browser:
**Keypoint → AI_Script → Scripted Sequence → Scripted Triggers**

Rick on them to bring up their properties, navigate to **AI Script → Add.**
Use the little dropdown menu and you’ll get an idea of everything an ST (Scripted Trigger) can do.

```
**These actors allow map developers greater manoeuvrability mostly in story/obj maps** 
due to the nature of how complicated they can get. 
But the way they work is like simple code or *blueprinting*.
```

Add some commands into a chain of “actions” to get STs to interact or do anything you want around players mid-game.
Here are the important commands you can practice with:

| Command              | Description                                                                                                                                                                                                                                                                                      |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Wait_For_Event**   | Start with this 99% of the time. Any trigger gives off an event due to player presence or whatever… Bam, this thing **detects** it and initiates the next scripted trigger action(s).                                                                                                               |
| **Display_Message**  | Displays a white message like story maps do, very good for debugging! <br>Set `bBroadcast = True`, `importance = Critical` to display to all players.                                                                                                                                           |
| **Spawn_Actor**      | Spawns actors at the ST (story maps use this to spawn specimens at set times). <br>Use the dropdown to pick `kfmod.Gorefast_STANDARD` or similar. <br>⚠️ Don’t pick any specimen names *without* “_standard” or they won’t work!                                                                 |
| **Go_to_Action**     | When done with the chain, you usually tell it to go to action 0. <br>Can be used for loops, but obviously, loop it infinitely without timers/delays and KF will crash.                                                                                                                                           |
| **Trigger_Event**    | If one trigger isn’t enough, you can link multiple STs, or use a timer with this command to trigger a new event (e.g. collectible rewards).                                                                                                                                                      |
| **Play_Sound**       | Plays sound files (like explosions) at given times/locations.                                                                                                                                                                                                                                    |
| **Play_Local_Sound** | Same as above, but commands the client to play the sound locally at a fixed volume.                                                                                                                                                                                                              |
| **IfCondition**      | Your “if” statement. Navigate to **Triggers → triggeredCondition** to find an actor that toggles a condition when triggered. <br>If the tagged condition is disabled, the script skips to the next `EndSection`. <br>**Note:** Works only if all Condition settings are `True` (starts enabled). |
| **IfRandomPct**      | Enter a number between 0 and 1 — the probability that the next actions execute. <br>If false, the ST skips to your next `EndSection`. *(Seems to return true more often — test it yourself :c)*                                                                                                  |
| **EndSection**       | Used with “If” actions, tells the ST which action to skip too if the 'IfCondition' wasn’t met.                                                                                                                                                                                                                 |

---

💡 **Important Note:**
All hidden actors are destroyed by the host on game start (idk how other triggers work but…), meaning the host reads and saves ST *scripts* before gameplay.
So, destroying an ST actor (for instance) mid-game won’t do anything.
If you set up a loop using **GoTo**, it either loops forever, or you’ll need to manually end it using “If” commands or by disabling the script.

For an example of use, check out my [KFO-BossArenaNerf](https://steamcommunity.com/sharedfiles/filedetails/?id=2318348544) map and see if you understand what's going on there, (I've got to advertise my own stuffs at some point) lol. Otherwise storymaps are very good.

---

### 💢 TWI Strikes Again!!

`KFUseTriggers` are pretty much **exclusively** for `KFDoorMovers`, **STs ignore their events**, as does everything else.
Maybe it’s explained in the script, but still… specific naming like `KFDoorTrigger` would’ve been *much* clearer. 😤

**Workaround**: If you need a player's use key to activate an ST, use a standard Trigger actor (not a KFUseTrigger) and set its bUseTrigger property to True in the Object tab. Probably.

---
