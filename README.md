# Rollback4ASBR

A project that aims to implement Rollback Netcode into JoJo All-Star Battle R

## STATUS: RESEARCH 🔎

## Motivation

Since CC2 basically killed this ultra fun game with their oh so great delay networking and shown no kind of signs to even fix some of the current netcode bugs (f.e. random game crashes while connecting to match), it’s now time to hack the game so we can get a decent online experience with a more modern approach (at least we’ll try).

The hardest thing would be getting the actual game to well rollback (lmao), but if we figure it out the rest of the project is child’s play. Also we gotta have someone that’s willing to host a server since we will be using a client <-> server <-> client connection (maybe setup some kind of donation and self host), also the servers shouldn’t be very resource intensive so it shouldn’t be expensive to host them. (Definitely WAY less than a shadow parsec server)
The server can also be used for a better ranked system, stats (pickrate, winrate etc.), replays (by storing players inputs and allowing to replay those), realtime spectating, and probably more (any ideas highly appreciated!)

## Technical Plan

[Technical Plan](./doc/technical-plan.md)
