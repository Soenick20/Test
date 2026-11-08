# Scrapwalker

A voxel mech prototype. You pilot a four-legged **Bulwark** frame from inside the cockpit, in a small destructible city held by hostile drones. This first build gets the core right: the mech, how it moves, what happens as it loses legs, and a world you can blow apart.

Open `index.html` in a desktop browser. It's a single file, and it loads three.js and the fonts from a CDN.

## What's in this build

**The mech (Bulwark-4)**
- First-person cockpit with a canopy frame, a status screen on the dashboard (leg health, armour, radar, scrap) and a dog tag that swings with every step and hit.
- Four legs with two segments each. Every leg is driven by procedural IK and steps by itself onto rubble, craters and rooftops. The hull pitches and rolls to match where the feet are.
- A 120 mm main gun on a turret that follows your eyes with a delay. The ring on screen shows where the barrel actually points, and it turns teal when the barrel is on target and loaded. Firing kicks the whole frame.
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

**World:** 256×64×256 voxels at 0.5 m each.
- Shells carve craters, and the hull bulldozes through glass, wood and trees.
- Feet crush weak blocks and stomp small drones.
- Anything cut off from the ground breaks free and falls as one piece, then shatters into rubble. That includes tower tops, water tanks and roofs, and it can crush your mech.

**Drones (test opposition)**
- **Sentries** sit on the rooftops. They flash their eye before firing and mostly aim at your legs.
- **Hounds** run at you and explode next to your legs.

## Controls

| Input | Action |
| --- | --- |
| W / S | Walk forward and back |
| A / D | Turn the hull |
| Q / E | Crab sideways |
| Shift | Long stride (4 legs only) |
| Mouse | Look and aim |
| Left click | Fire |
| Right click / F | Grapple (hold to reel) |
| Space | Cut cables |
| V | Switch between cockpit and outside view |

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
