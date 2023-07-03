# Rollback4ASBR

A project that aims to implement Rollback Netcode into JoJo All-Star Battle R

## STATUS: RESEARCH 🔎

For now this repository only will consist of research and documentation. Once we have a solid plan (or i get bored with writing docs), we will start working on the actual implementation. If you want to help with the research, check out the [Contributing section](#contributing).

## Motivation

Since CC2 basically killed this ultra fun game with their oh so great delay networking and shown no kind of signs to even fix some of the current netcode bugs (f.e. random game crashes while connecting to match), it’s now time to hack the game so we can get a decent online experience with a more modern approach (at least I’ll try).

The hardest thing would be getting the actual game to well rollback (lmao), but if I figure it out the rest of the project is child’s play. Also we gotta have someone that’s willing to host a server since we will be using a client <-> server <-> client connection (maybe setup some kind of donation and self host), also the servers shouldn’t be very resource intensive so it shouldn’t be expensive to host them. (Definitely WAY less than a shadow parsec server)
The server can also be used for a better ranked system, stats (pickrate, winrate etc.), replays (by storing players inputs and allowing to replay those), realtime spectating, and probably more (any ideas highly appreciated and can be posted in the Discussions under the `Ideas` tag!)

This project will be open source so anyone can contribute to it and help make the game playable again (also it's open source so i can have ppl pressure me to actually work on it lmao). While i don't expect this to be a quick project, nor do i know if i will ever finish it at all, i will try my best to make it happen. I will also publicly embarrass myself on twitch most of the time while working on this project, so if you want to see me suffer, you can follow me on [twitch](https://www.twitch.tv/kapilarny).

## Technical Plan

[Technical Plan](./doc/technical-plan.md)

## Contributing

If you want to contribute to this project, you can do so by forking this repository and creating a pull request with your changes. If you want to discuss something, you can hit me up on Discord: `@kapilarny`.
