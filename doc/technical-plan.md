# Technical Plan

This document serves to note all technical details we will need to know when implementing the Rollback.
To be clear, this project (atleast for now) ONLY focuses on the Windows PC Steam version of the game, since it's the most popular platform and the easiest to work with.

## Simplified plan for client <-> server <-> client communication

We will use some mystical modding magic to intercept the game's input, we will send that input with its neccessary for rollback frame ID. We will also need to perform a voodoo ritual to somehow rollback the game. Now depending on the setup and how everything goes we can go with two versions:

- Have a server that will be basically a proxy between the players. This has an advantage in a way that the other player cannot get your IP (with P2P connection you can get the IP of the other player and that can be used for mischevious things like DDoS attacks), also the servers could be used for some cool ass things like stats, replays (storing the game inputs) and probably a lot more. The disadvantage is that you need to have a server running somewhere.

- Have a P2P connection between the players. This has an advantage in a way that you don't need to have a server running somewhere. The disadvantage is that as said bit earlier, the other player can get your IP.

For now i will stick mainly with the server version, but i will make it possible to also use the P2P version for those who arent scared of leaking their ip somewhere or playing with friends.

![really great drawing](./img/ASBR%20ROLLBACK%20NOTES.png)

This really great drawing above shows the basics on how the server will work. The red/blue arrow represent the packets that respectively P1 and P2 send. Basically server just receives the packet and sends it back to the opposite player. Nothing too crazy there.
For P2P connections we could just ignore the servers and send the packets directly to the other player.

## How to rollback the game

Ah yes, rollback netcode, the thing that makes fighting games playable online. Well how does it work you may ask? Well glad you asked, because i have no idea. But i will try to explain it as best as i can.
You know how the great mighty delay-based netcode works right? It waits for the other player input to go thru and than allow you to input. It's bad, we don't wanna wait for nothing. So how does rollback netcode work? Well it's simple, you just don't wait for the other player input to go thru, you just assume that the other player will do the same thing as he did on his last frame (f.e. if he was moving forward on last frame we will predict that well he still walkin, or if the player is in the middle of an animation we just play another frame of that animation) and pray to god that he actually did. And after we receive the actual frame data on what the hell actually happened on that particular frame we either do nothing if we guessed correctly, or rollback the player to last known frame and replay the game from that frame, include the input that we just received and put the player in the right state. To actually perform a rollback we will use a buffer of sorts for few of the last frames that will include the players data so we can go back in time. Now this is a very simplified explanation, but i hope you get the idea. Now another question would be, how the hell are we going to manipulate the game to actually perform a rollback, and to be honest I have no clue, as I said earlier we will probably need to perform voodoo rituals and sacrifice a goat or something, but we will figure it out (hopefully).

## Technologies

We will use most probably C++ for the client application that will handle sending inputs and rollbacking, for server i have no clue yet but most probably some performant language like Rust or Go.
