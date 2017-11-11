# doppelplay

## Learn a language while you sing

Doppelplay is a fun way to learn about languages and cultures. We provide a media player 
where you choose the playlist (from novice learner to advanced) and the level of assistence. 
You could view subtitles in your native language, in the language you are learning or both 
at the same time.

If you decide to take it one step further, we can show only a single word as a hint, or we 
could quiz you real-time on your knowledge of the lyrics.
 
We will start out with a selection of moderated songs and lyrics for a few languanges, but 
we plan to expand to more languages and media types. Why not learn from famous speaches, 
interviews or lectures?

## Possible future plans

We would like to facilitate a community around doppelplay, where you can share and moderate 
content and playlists. For now this is out of the scope of this project.

## Architecture

```
(react client)                         (node server)          
┌─────────────────────┐ users, lyrics  ┌─────────────────────┐
│     DOPPELPLAY      │← ─ ─ ─ ─ ─ ─ → │                     │
│                     │                │   MEDIASUBS SERVER  │
│ ┌─────────────────┐ │   playlists    │                     │
│ │   MEDIA QUEUE   │ │← ─ ─ ─ ─ ─ ─ → └──────────┬──────────┘
│ └────────┬────────┘ │                           │
│ ┌────────┴────────┐ │                   ┌───────┴───────┐ 
│ │  MEDIA PLAYER   │ │← ─ ┐              │   DATASTORE   │
│ └─────────────────┘ │    │              └───────────────┘
└─────────────────────┘    │
                           │
                           YouTube
                           Vimeo etc
```

The architecture will consist of several semi-autonomous components:

* MEDIA PLAYER: preferable a third-party react media player that handles streaming from various sources.
* MEDIA QUEUE: this handles the queue, shuffle, playlists etc and forms and integrates with the media player.
* DOPPELPLAY: all the functionality that is specific to displaying multilingual subtitles and handling users.
* MEDIASUBS SERVER + DATA STORE: provide an API to retreive and store lyrics, playlists and user data.


## License and team

Doppelplay is an Open Source project released under the MIT license. It is an educational, 
not-for-profit project that was initiated by selected students of the Udacitiy Nanodegree 
Program, without any further association with Udacity.
