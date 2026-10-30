# Bomberman World — Shabang

**Student:** Maria-Teodora Oprea 

## How to play

- **Controls:** WASD keys to move, SPACE to place a bomb, R to restart after a win or loss, H to activate the shield, Q OR ESCAPE to quit.
- **Objective and rules:** Defeat 20 enemies to win. Lose if a blast or an enemy touches you. If both happen in the same frame, the loss wins.
- **Configurations / demo setup:** Default.

## Features and validation

| Feature | Check, observed result, and expected behaviour |
| --- | --- |
| 1. Player damage and death | I died once from my own bomb and once by walking into an enemy. Both set the round to Lost, as expected.|
| 2. Round states and objective | I won the round by defeating 20 enemies. Was difficult but not impossible. When the game was lost or won, the world froze as expected and the message stayed on screen.|
| 3. Safe restart | I restarted with R after a win and a loss and played normally. When a bomb was still active and i died by colliding with an enemy, by pressing R, everything reseted and i could continue playing without the blast from the bomb to appear.|
| 4. Solid bombs with owner escape | I placed a bomb, walked off it, and tried to re-enter: I was blocked.After detonation I could walk through the tile. An enemy walking into a bomb turned around. Pressing SPACE again on the occupied tile created no second bomb.|
| 5. Blast-range pickup | I placed a bomb at range 3, collected the green pickup (the HUD showed 4); then placed another bomb: only the new one had the longer blast. Returning to the pickup's tile did nothing. After a restart, the pickup was back and the range was 3.|
| 6. Multiple bombs per owner| I made the number of maximum bombs placed at once to be 3. I placed 3 bombs on different tiles and the 4 was rejected. After one detonated I could place a replacement, and repeating the cycle behaved the same. The count is taken from the live bombs each time, so it cannot drift out of sync.|
| 8. Shield | Pressing H starts a 5 second shield (a blue ring around the player). A 20 second cooldown starts when the shield ends, and H does nothing during the shield or the cooldown. While shielded I survived an enemy touch and a blast, and after the ring disappeared both killed me; Restart reset both timers. |
| 11. Scoring and combos | Each destroyed enemy gives 100 points times the current multiplier, awarded once in the destruction step. Kills within 3 seconds of each other raise the multiplier (maximum x5); after 3 seconds without a kill it goes back to x1. I killed two enemies within the window (x2), then waited for it to expire (x1). When i restarted the game, the score was 0 and the multiplier back to 1. |

**Known issues:** Collision uses a footprint at the entity's feet, which is smaller than its draw size. An enemy walking in a lane just above or below a bomb can overlap it visually without touching it, so it is not blocked. I confirmed this by drawing the collision boxes: they did not touch. 

## Sources and assistance

This project builds on the shared Kotte foundations ( Week 6 reference). I used Claude as a tutor while working. I gave him the assignment and suggested a schedule i should keep up with, as i procrastinated a bit with this assignment. I ask him to explain some existing code and also gave hints on compiler errors and helped me with the HUD script. 
