# Sweet Spaceship

A minimalist multiplayer space shooter in white and glass. Fly a wireframe
starfighter, clear waves of gray TIE-style ships straight out of the
*A New Hope* targeting computer, and race up to four friends on the
leaderboard — most ships destroyed wins.

## Play

Open the game, name your pilot, pick a color, and share the invite link.
Anyone opening your link joins your room (up to 5 pilots total).

- **Desktop** — `WASD` / arrows to fly, `Space` to fire, `Esc` to pause
- **Mobile (landscape)** — drag on the left half to fly, tap/hold the right half to fire

Each pilot has 3 hearts and respawns 5 seconds after going down. Sustained
fire overheats your cannons — pace your shots.

## How it works

- Single self-contained `index.html` — canvas rendering, no build step
- Peer-to-peer multiplayer over WebRTC via [Trystero](https://github.com/dmotz/trystero)
  (Nostr relays for signaling — no server, no accounts, no keys)
- The room id lives in the URL hash; one peer is elected spawner and
  broadcasts enemy waves, kills are claimed optimistically
- The base color `#FF76A2` is reserved for the pilot who created the room;
  joiners pick from four other colors, never duplicated

## Run locally

Just open `index.html` in a browser — multiplayer works even from `file://`
as long as you're online.
