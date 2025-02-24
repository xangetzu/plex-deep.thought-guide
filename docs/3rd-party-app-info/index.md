# **My set up deep.thought and how I manage the library**

## **The basics**

Three years ago, I decided to get a bit more serious with my Plex server. It had been up until then, running on an old Windows machine that was formally a game rig with a bunch of USB attached drives. I wanted something more so I bought hardware to build a server. New to the concept, and realizing I wanted to be off of the Windows environment; I looked at **Unraid** as an option as I was still nervous about learning something new but wanted the benefits of Linux stability. Three years later, the whole setup has evolved. I now have multiple Network Attached Storage boxes (NAS) both on Synology and TrueNAS operating systems and my suite of apps running on Unraid has grown to way more than just one docker container with plex on it. 

At the core is Unraid which acts as my application server. My NASs hold the library and the apps on Unraid are able to view that data and make changes to it. Running on Docker on my Unraid box I have 5 levels of applications related to media and Plex. 

 1. **Plex Apps**: These are apps related to plex directly and interface with it directly. Things like **Overseerr** (for requesting new content); **Tautulli** (for viewing history, handling notifications, and server analytics); and finally **Sync-Lounge** (for watch-together type stuff.)
 2. **Media Management Apps**: Media Management and Download services work in tandem to each other. The **ARR** applications receive notifications from Overseerr when a new request is made for Movies and TV. They then search various indexers for where the media can be found, and in turn, instruct my Download services to grab it. Then, once it is complete, they move it and rename it to where it needs to be for Plex to ingest it and make it available to view. Some things are also managed by other connections outside of Overseerr such as **Trakt** or **Spotify** for music. 
 3. **Download Services**: Pretty cut and dry with this one. These apps literally download the media and hold it until told to do otherwise.
 4. **Streaming Services**: Something most people won't have access to, but I use an **IPTV** service that I pipe through Plex using a streaming application that simulates a cable card in my server for Live-TV.
 5. **Media Processing**: Media processing is something I do when I have a file I can't get in a format or size I want. Generally, I aim for something called H265, or HEVC as its also called. This stands for **High Efficiency Video Codec**. It basically means for a smaller file size I can still get exceptionally good picture and audio quality. But this takes a lot of compute power to do so it's always best to try and find the media already in this format to begin with. As such, this ends up being a last resort and I seriously weigh the benefit to the conversion and if it will be worth the time investment as an entire show with many seasons can take 6 months to complete.

These applications run 24/7 and are always adding new content, upgrading and replacing content, and whatever else is needed to make the Plex experience on deep.thought great. 

## **Communication**

Communication is very important to me. To that end, I use both Tautulli and Overseerr to communicate a few things.

1. When a request is approved via **Overseerr**, I send a notification to **discord**. If the person that requested the content is a member of the discord and added to the server I set up for deep.thought, the message will be directed to them with an (@user) call out. 
2. Once media becomes available from Plex's point of view, meaning its finished scanning it in, another notification is sent out to the discord stating the content is in Plex. This message is meant for everyone so a user is not tagged in it.
3. **Tautulli** also keeps tabs on whether the server is online or even reachable and will notify when it is not. 

In the future, I plan on adding better communication around server availability because it suffers from being local to the actual plex server. Meaning, it can't report to discord if something outside of my home happens such as the internet going down. I need an external application to do that type of monitoring. I'd also like to leverage with the **ARR** applications can muster as well, by indicating when they have found the requested content and begin downloading it. 

!!! note
    It is highly recommended you reach out to me on [discord](https://discord.com/users/401938150877954048) in order to be added to the dedicated server I have set up for **deep.thought**. This will enable you to receive notifications when media is added or when the server is down. It also happens to be the only way to reach out to me directly with questions.

## **Maintenance and Updates**

I generally keep everything up to date as much as possible. Plex enters its maintenance period based on a time I have selected that is best for most of my users. However, there are some over in the UK and AU (Sorry mates) that this may effect. From 4 AM to 11 AM daily, Plex analyzes new media to create what it needs to operate more efficiently which can sometimes slow it down. Every few days, it runs some database stuff that kills it for about 20 minutes outright, but it usually comes back up reliably. 

Operating system updates and application updates are more manual and I try to warn people beforehand that they will be happening, sometimes even setting up an event in Discord so that everyone is aware if I expect it to take longer than just a few minutes. When hardware is involved, it is a case by case basis for whether there is a real impact or not.  