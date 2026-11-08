# Scrapwalker

A voxel mech prototype. You start on foot as the pilot, run to your **Bulwark**, climb in through the roof hatch and take it into a destructible city held by hostile drones. The frame is sized around the pilot: the hull top is about at head height, and you barely fit inside. It is small and quick, not a lumbering tank. The default camera is over the shoulder, and V switches to the cockpit. This first build gets the core right: the mech, how it moves, what happens as it loses legs, and a world you can blow apart.

Open `index.html` in a desktop browser. It's a single file, and it loads three.js and the fonts from a CDN.

## What's in this build

**The pilot**
- Built from 6.25 cm blocks at real human size (1.8 m), in a flight suit and helmet.
- On foot you run, sprint and jump. F climbs in when you're next to the frame, and G climbs back out. One hit kills you on foot.

**The mech (Bulwark-4)**
- About 2.5 m tall to the top of the turret, with legs spanning about 4.5 m. Walks at about 7 m/s, strides at 10 m/s and can jump. Built from blocks: armour panels, hazard stripes, worn paint. Hits chip blocks off the hull, turret and the leg segment that was struck.
- An outside camera that trails the frame and bumps on every footfall. The optional cockpit has a status screen and a dog tag that swings as you walk.
- Four legs with two segments each, driven by procedural IK. They move in a diagonal trot: one pair lifts while the other pair carries the weight. The body sags when legs lift and thuds when they plant, and it leans into starts, stops and turns.
- A 75 mm main gun (0.9 s reload) on a turret that follows your eyes with a delay. The ring on screen shows where the barrel actually points, and it turns teal when the barrel is on target and loaded. Firing kicks the whole frame.
- Two grapples (65 m cable). Hold to reel in, which can lift the frame up a building. Let go to hang on the cable, and cut the cables to drop.

**Leg damage changes how the mech moves**

| Legs | Behaviour |
| --- | --- |
| 4 | Normal diagonal trot. Shift gives a long stride. |
| 3 | Slower. The frame tilts toward the missing leg, veers and crabs sideways, so you have to steer against it. |
| 2 | The hull drags on the ground. It lurches: reach, then pull, with sparks and scraping. |
| 1 | Crawl. It drags slowly in grinding lurches. |
| 0 | Immobile. Grapples are the only way to move. |

**Death:** the pilot is the one thing you can't lose.
- A cockpit hit cracks the canopy, and a second cockpit hit kills the pilot.
- Hull hits wear the armour down. Once it's gone, the next hull hit reaches the pilot.

**World:** 384×96×384 voxels at 0.25 m each, meshed with greedy merging. The shader adds per-block shading and edges.
- Shells carve craters, and the hull bulldozes through glass, wood and trees.
- Feet crush weak blocks and stomp small drones.
- Anything cut off from the ground breaks free and falls as one piece, then shatters into rubble. That includes tower tops, water tanks and roofs, and it can crush your mech.

**Drones (test opposition)**
- **Sentries** sit on the rooftops. They flash their eye before firing and mostly aim at your legs.
- **Hounds** run at you and explode next to your legs.

## Controls

| Input | Action |
| --- | --- |
| W / S | Walk forward and back (on foot: run) |
| A / D | Turn the hull |
| Q / E | Crab sideways |
| Shift | Long stride (4 legs only) |
| Mouse | Look and aim |
| Left click | Fire |
| Right click / F | Grapple (hold to reel) |
| Space | Jump |
| X | Cut cables |
| F (on foot) / G | Climb in / climb out |
| V | Switch between the outside view and the cockpit |

Test keys:

| Key | Action |
| --- | --- |
| 1 2 3 4 | Blow off leg FL, FR, BL or BR |
| 0 | Field repair |
| H | Hostiles on/off |
| N | Spawn a hound |
| R | Redeploy after death |

Touch: a left stick to walk and turn, drag the right side of the screen to look, plus FIRE, HOOK, CUT and VIEW buttons. Hold the phone in landscape.

## Next steps
- A mission loop: deploy, kill, loot, extract.
- A hangar where scrap buys repairs, new legs, guns and other frames.
- Heat and ammo management.
- Smarter drone types.
