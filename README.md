# Sweet Spaceship

A minimalist multiplayer space shooter in white and glass. Fly a wireframe
starfighter, clear waves of grey enemy interceptors rendered as vector
outlines, and race up to three friends on the leaderboard — most ships
destroyed wins.

## Game modes

The room creator picks the mission; everyone who joins the link plays it.

- **Frontline** — the classic run. Enemies sweep in from the right; fly
  freely in all directions and hold the line.
- **Zero G** — rotate & thrust. Left/right turn the ship, up thrusts,
  down reverse-thrusts, and momentum carries you when you let go. No
  walls (cross an edge, reappear on the other side) and enemies attack
  from everywhere.

## Play

Open the game, name your pilot, pick a color, and share the invite link.
Anyone opening your link joins your room (up to 4 pilots total).

- **Desktop** — `WASD` / arrows, `Space` to fire, `Esc` to pause
- **Mobile (landscape)** — drag on the left half to fly/steer, tap/hold
  the right half to fire

Each pilot has 3 hearts and respawns 5 seconds after going down. Sustained
fire overheats your cannons — pace your shots. Big ships take three hits;
watch their hull bar shrink.

## How it works

- Single self-contained `index.html` — canvas rendering, no build step
- Peer-to-peer multiplayer over WebRTC via [Trystero](https://github.com/dmotz/trystero)
  (Nostr relays for signaling — no server, no accounts, no keys)
- The room id and game mode live in the URL hash; one peer is elected
  spawner and broadcasts enemy waves, kills are claimed optimistically
- The base color `#FF76A2` is reserved for the pilot who created the room;
  joiners pick from `#00C3FF`, `#3ED29C`, `#A58BEA` — never duplicated

## Run locally

Just open `index.html` in a browser — multiplayer works even from `file://`
as long as you're online.
