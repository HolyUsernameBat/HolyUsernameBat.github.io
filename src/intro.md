## **🧠 Intro**

Hiya, this website was converted from my [steam guide](https://steamcommunity.com/sharedfiles/filedetails/?id=2115290403) for making maps in the Killing Floor 1 SDK (Unreal Engine 2.5).
**I HATE KF SDK,** I despise it, it’s awful but I’m here because I love KF. If that’s the case for you, you’ll learn to despise KF SDK as well.  

Ofc, there is at least a certain charm in this SDK because it’s based on a version of Unreal Editor 2.5 which just **breathe’s** simplicity.  
Sure, the tools may not be intuitive for beginners, but with the help of guides you’ll at least realise they’re not hidden behind a million hotkeys or tabs.  
Unless you get inventive there’s usually 1 or 2 ways to do something, and that’s that.  

I might as well address the elephant in the room: 
This game is soo dead you’re prob here because you’re REALLY bored, or clicked one of my links to this guide, by mistake?! Meh, well have fun skimming through.  

> ### CRITICAL PATCH ALERT / IMPORTANT ADD ON (24/02/25 Edit):  
> metallicafan212 has released their slow-selection fix for the Killing Floor Editor, this means no more waiting 10sec++ for almost every actor selection to register in SDK!  
> [GitHub Release – metallicafan212/UE2SelectionFixes v0.3-Alpha-KF](https://github.com/metallicafan212/UE2SelectionFixes/releases/tag/v0.3-Alpha-KF)  

> If you **JUST** started with KF SDK and you don’t like my *Basics* section, here’s a video which isn’t terrible for beginners:  

 <iframe width="560" height="315" 
src="https://www.youtube.com/embed/basbB5NzTzU?list=PLsHIUYkkz0G6J9_BHc5fD7PEY97TUyLsD" 
title="Unreal Editor 2.5 Tutorial" 
frameborder="0" 
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
allowfullscreen>
</iframe>

> If you’re only interested in SDK but don’t **EVEN** know how to open it yet, this guide would be better to start with:  
> [Steam Guide – Getting Started with SDK](https://steamcommunity.com/sharedfiles/filedetails/?id=117622426)

> If you’re dying for a community to chat with there’re at least a few semi-active KF1 mappers in this (Siren Torturers) Discord server:  
> [Join Siren Torturers on Discord](https://discord.gg/wK9sDGa)

> ST also offers an edited SDK (KFEd) application which **beefs a 2GB RAM cap to 4GB** :O  
> Makes you wonder what kind of PCs TWI were rocking am I right..?  
> Anyway, I’ve used it, everyone at ST uses it, and it works grand, so consider it highly recommended .
> [KFEd-4gb.zip Download](http://sirentorturers.site.nfoservers.com/downloads/KFEd-4gb.zip)  
> *P.S: If the download makes you nervous you can also try edit the .exe yourself. Briefly discussed here:*  
> [Steam Guide – 4GB Patch Discussion](https://steamcommunity.com/sharedfiles/filedetails/?id=3554292897)

> If you prefer to mod you could consult my guide but [Lazy KF Wiki](https://insultingpros.github.io/LazyKFWiki/#/UnrealScript/ModdingSetup) is a better place to start.
>Community: [Official KF Modders discord.](https://discord.gg/rzNpaD3) (KF2 modders expanded their discord for us, and help with favours from time to time so play nice please).

> For an unofficial KF1 modder discord (Bungalow), ping a message my way and I'll see if I can get you an invite, same as before, play nice, read their rules.

> As an aside, here is a tutorial of me developing a small map to completion, without the decorating unfortunately: 

 <iframe width="560" height="315" 
src="https://www.youtube.com/embed/zl2e_5K6OS4" 
frameborder="0" 
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen>
</iframe>

>Last of all, if you hate my style feel free to instead rely on some of my extensive references listed at the end of the guide.  

Otherwise let’s get started…
