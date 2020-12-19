Transcript for FAP18
====================

- [Link to Twitch VOD](https://www.twitch.tv/videos/274162622)
- [Link to YouTube video](https://www.youtube.com/watch?v=g976eKmFs9s)
- [Link to official GitHub Gist of questions, by Asherslab](https://gist.github.com/Asherslab/b071438a6503dd76d0cf09bf35804e56)

Participants
------------

- **LexManos**: Project lead and God of Forge.
- **cpw**: Co-lead maintainer of Forge and FML, king of the squirrels.
- **mezz**: Contributor to Forge, PR and Triage manager
- **TamasHenning** - Contributor and friend to Forge

Audio Transcript
----------------

> *Transcription starts at 9:38. Times are based on the YouTube video.*

__LexManos__: Alright, it's officially 3 o' clock.

__cpw__: It is! Hello! Good evening, everyone. Welcome to.. a big FAP party! This is the Forge Parley event for 2018; we might try and do this again if this one goes alright. <br>
I'm cpw, sometime Forge developer. And joining me in chat, we have LexManos who you probably all know-

__LexManos__: Hello everyone.

__cpw__: Sorry Lex, I talked over you.

__LexManos__: I was just saying hello.

__cpw__: We also have mezz, who is also a big contributor to Forge these days.

__mezz__: Hello, this is mezz.

__cpw__: And Tamas is hanging out in the background; he's been a long-time co-...pal of Forge. We hope to have some other people joining us later on, we'll see what happens. But right now, I'll switch the screen back to this _(screen switches to FAP18 logo)_, we'll go back to the code in a wee while. <br>
This was just mostly setup to give us a chance to talk to you about what's happening with Forge in 2018. It's become a very very big and public project over the last... 7 years now Lex, isn't it? Seven I think, yeah, 7.

__LexManos__: Somewhere around there.

__cpw__: _(chuckles)_ It's come from, like-

__LexManos__: Way too old for this.

__cpw__: Yeah, this whole thing is just completely nuts. But y'know, everyone is- Forge is very old, very old indeed, and a lot of what we're going to be talking about is related to that age. <br>
Forge was designed - and FML, the piece that I've been working on for the last long while, was designed in... 1.2.3? When Bukkit was still big, ModLoader was still _the_ standard for building mods and so we had to be 100% compatible with ModLoader. Java 1.6 was fresh and new, and we had to be compatible with Java 5. Spritesheets was still a thing. <br>
So, this was very, very different world back in those days, and the... technical debt has been huge. We've accumulated cruft from the time that ModLoader died back in 1.6.4, the time Bukkit died. Y'know, we've got code that still does stuff from before we split out the classloader and gave that to the Mojang team.

__LexManos__: We've got code that has existed before the client and server were merged together.

__cpw__: Yes, yes we do. That's right, that was the first big thing we did. _(chuckles)_ Dealing with that client and server merge, that was a whole world of fun. So, yeah. <br>
For the last, I'm-a say the last two years, I've been on a mission to try and clean up the mess. Originally, I'd hoped to target 1.12; that was a very, very naïve hope, which was a year ago by the way - 1.12 came out a year ago now. I was hoping to target 1.12 with this work, but there was no way it was ever going to be ready in time, so we deferred it. And 1.13 has taken a very long time to come out. As we all know, it's still not gonna be out, probably for another, another 2 or 3 weeks maybe? And so, we've taken this opportunity to redo a lot of how mods load. <br>
Yes, yes it is Grum. Hey Grum, hello! _(laugh)_

__LexManos__: Is that actually Grum, or is that some fake...

__cpw__: I believe that is actually Grum. Do you want an invite into the voice? _(brief moment of silence)_ <br>
Yeah, that's actually Grum.

__LexManos__: Let's have the account in question verify that they are not a fake account.

__cpw__: "oh god please not" _[from Grum\_]_, he doesn't actually want to go on voice anyway, so that's fine. "Only a fake grum would say hes the real grum" _[from The_CodedOne]_.

__mezz__: Yeah, we should try to get a fake Grum in chat.

__cpw__: _Hang on a minute... yeah that's no one I care about._ We can get an easy verification from Grum. _[keyboard clacking]_ <br>
I've put a request in, Grum, you know where to answer it. _(moment of silence)_

__LexManos__: Cuz if that it the real Grum, toss him a moderation thing.

__cpw__: That's what I was gonna do, I was gonna mod him.

__LexManos__: I love you all in channel, but I prefer- I like to filter people out based off on icons cuz there's a lot of people.

__cpw__: "2 kittens" _[from Grum\_]_, yes indeed , that's right. Yes indeed. Ah, yeah, there you go. _(laughs)_ Fine, whatever. How do I give you moderation... _ban, timeout, mod user!_ There we go, he's now a mod. Alright, _(clears throat)_ you did. Let's carry on talking about what's going on. Do do do..., where's that bloomin' list of questions, cuz I think that's probably a good place to start, wouldn't you agree?

__LexManos__: Yup, that's why we had them collate it.

__cpw__: Yeah, indeed. _Yeah, that's good... that one! Okay, so if I do this... [screen switches to list of questions]_ We have a list of question, yay! _We'll do that... Don't need to see that!_ <br>
So, we've been asking for questions on, _(chuckles)_ on Discord for the last week; this is a collation of obvious questions from there, and myself and the others will go attempt to answer them while on the stream. Then hopefully once we've got these answered, if we can throw it open for more questions 'cause no doubt there'll be more. I will be showing a little bit of what the new mod system looks like; it's not complete, the status is still very much... yeah, there's still a lot to be done to get it to same state as we had in 1.12, but I'm confident that we can deliver that fairly shortly. Yeah, looks like we can mark it all. <br>

> **1.13 General**: What's the progress on 1.13?

__cpw__: So, "What's the progress?" _[from the questions]_. We still have a lot of work to do... I have- We have agreed that we're going to be merging in all of the functional changes from my branch of FML, which means we are completely redoing the mod loader, we are completely redoing how mods load, and we are completely redoing probably some of the network stuff as well. We'll talk about that a little bit more later, but that's still being in discussion, so... There's still a lot of work to be done but I'm confident that we can get it going, I think we've crossed all the big serious hurdles to making it all work, which is the key. Do you have anything to add, Lex?

__LexManos__: So, for those who don't know, basically Forge is two different projects, well, three different projects. There is the LaunchWrapper, which was donated to Mojang; it's what allows their old versions to work on their new launcher. It's also what runs all the coremods and all that stuff. There's FML, which is the basic mod loader that just loads a class file, fires off a couple events saying 'Hey, the client loaded'; and then there's Forge, which is all of the actual modifications to Minecraft, adding new events, changing how- basically all the registries, all the big library stuff, is Forge. <br>
So, cpw has to comment on this, but as far as 1.13 is concerned, because we're updating to support Java 9 which everyone has been craving for, and so much is changing in 1.13, he's completely rewriting LaunchWrapper, and that's the fundamental thing-

__cpw__: FML as well. So, FML is mostly rewritten, it's restructured- there's still a lot of common code, but a large amount of the methodology that FML uses to load mods has changed as we've gotten more and more-

__LexManos__: Your mic's doing it again.

__cpw__: _Oh... [mic cuts out briefly] better?_ As we've got more and more understanding about how FML works and how people have been using it, building these giant modpacks, we've realized that one of the big problems is the way that FML loads mods. It's all single stream at the moment, and one mod goes after another all the way through, and if like you have 250 mods and each one takes 1 second to execute one of the events, we have 5 events that they can receive, that means that they take 5 seconds each to load; 250 times 5, that's 750 seconds, that's over 10 minutes. _(chuckles)_

__LexManos__: One of the major complaints people have is just the load time, and there will never be a day Forge loads a thousand mods instantaneously-

__cpw__: No.

__LexManos__: -because stuff needs [to be] actually processed, but we're working on making it faster without the technical debt we've acrued from ModLoader. A lot of the issues is because ModLoader.

__cpw__: Yeah, a lot of it is technical debt that we carried over from ModLoader, which is annoying, but that's why- _["250 * 5 is not 750" from offbeathwitch]_ and yeah, you're right, it's not 750, it's 1250, so it's actually way worse than that, that's 20 minutes, isn't it? _(chuckles)_ You can blame ModLoader, ModLoader is from a different era. That's the reality of the situation. Modding was just different; people weren't building as many huge mods, they were the exception rather than the rule. _["a different eta... like 7+ years ago" from ohaiiChun]_ Yes, it was 7 years ago, iChun. <br>
Anyway, so there is progress; there has a huge amount of progress. I'm confident that we can deliver something; it's gonna be a- gonna be a lot of work between now and "Wow, 1.13 is wonderful and stable and I love it!", but, yeah. I'm fairly certain it will probably be 1.14 before we really are at that point... but, yeah.

**Last position of transcription: _22:05_**