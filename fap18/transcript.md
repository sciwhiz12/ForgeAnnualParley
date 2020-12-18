Transcript for FAP18
====================

[Link to Twitch VOD](https://www.twitch.tv/videos/274162622)
[Link to YouTube video](https://www.youtube.com/watch?v=g976eKmFs9s)
[Link to official GitHub Gist of questions, by Asherslab](https://gist.github.com/Asherslab/b071438a6503dd76d0cf09bf35804e56)

Participants
------------

- **LexManos**: Project lead and God of Forge.
- **cpw**: Co-lead maintainer of Forge and FML, king of the squirrels.
- **mezz**: Contributor to Forge, PR and Triage manager

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

__cpw__: And taumass is hanging out in the background; he's been a long-time co-...pal of Forge. We hope to have some other people joining us later on, we'll see what happens. But right now, I'll switch the screen back to this _(screen switches to FAP18 logo)_, we'll go back to the code in a wee while. <br>
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

__cpw__: "oh god please not" _[from Grum_]_, he doesn't actually want to go on voice anyway, so that's fine. "Only a fake grum would say hes the real grum" _[from The_CodedOne]_.

__mezz__: Yeah, we should try to get a fake Grum in chat.

__cpw__: _Hang on a minute... yeah that's no one I care about._ We can get an easy verification from Grum. _(keyboard clacking)_ <br>
I've put a request in, Grum, you know where to answer it. _(moment of silence)_

__LexManos__: Cuz if that it the real Grum, toss him a moderation thing.

__cpw__: That's what I was gonna do, I was gonna mod him.

__LexManos__: I love you all in channel, but I prefer- I like to filter people out based off on icons cuz there's a lot of people.

__cpw__: "2 kittens" _[from Grum_]_, yes indeed , that's right. Yes indeed. Ah, yeah, there you go. _(laughs)_ Fine, whatever. How do I give you moderation... _ban, timeout, mod user!_ There we go, he's now a mod. Alright, _(clears thoart)_ you did. Let's carry on talking about what's going on. Do do do..., where's that bloomin' list of questions, cuz I think that's probably a good place to start, wouldn't you agree?

__LexManos__: Yup, that's why we had them collate it.

__cpw__: Yeah, indeed. _Yeah, that's good... that one! If I do this..._ _(Screen switches to list of questions)_

***Last position of transcription: 16:22***