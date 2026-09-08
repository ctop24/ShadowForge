# ShadowForge — A Britannia Idle Tale

A web-based idle game inspired by **Ultima Online**. Open `index.html` in a browser (or serve it with GitHub Pages) and start training — no build step, no dependencies, everything in one file.

## The pitch

Classic UO skill mechanics, idle-game pacing:

- **Skills rise by use.** Mine ore to raise Mining, swing a sword to raise Swordsmanship — 0.0 to 100.0 in 0.1 increments, just like the old skill gump.
- **Difficulty-based gains.** Easy actions stop teaching you. Iron ore stalls around 60 skill; you'll need Dull Copper, Shadow Iron… all the way to Valorite to keep learning. Same for monsters, lumber, fish, and crafts.
- **No 700-point skill cap.** These lands are kinder than Sosaria — Grandmaster every skill if you have the patience.
- **UO titles** — Neophyte → Novice → Apprentice → … → Grandmaster → Elder → Legendary.
- **Power Scrolls.** Dragons, Ancient Wyrms, and Balrons rarely drop scrolls that raise an individual skill cap past 100, up to 120.
- **Stats by use.** STR/DEX/INT grow from the skills you train. STR gives HP and melee damage, DEX gives swing speed and dodge, INT gives mana.

## Skills (17)

| Group | Skills |
|---|---|
| Gathering | Mining (9 colored ores), Lumberjacking (7 woods), Fishing (4 catches) |
| Crafting | Blacksmithy, Carpentry, Tailoring, Cooking, Alchemy |
| Combat | Swordsmanship, Tactics, Anatomy, Healing |
| Magic | Magery, Evaluating Intelligence, Meditation |
| Roguery | Hiding, Stealth |

## Gameplay loop

1. **Gather** — colored ore, special woods, fish. Higher tiers unlock with skill and sell for far more.
2. **Craft** — smith weapons and armor from any ingot color (better material = better item = higher skill needed). Items better than your gear are auto-equipped; the rest are sold. Tailors work hides into armor, alchemists brew heal potions, cooks turn fish into steaks (Well Fed regen buff).
3. **Hunt** — thirteen monsters from Mongbat to Balron. Fight as a **Warrior** (Swords/Tactics/Anatomy) or a **Mage** (Magery/Eval Int — casts your best affordable spell, Magic Arrow through Flamestrike). Bandages, potions, and food are used automatically; Hiding and Stealth grant dodge.
4. **Die occasionally** — "Thou art dead!" costs 10% of your gold; a wandering healer resurrects you and you rejoin the fight (three deaths in a row and you're told to seek easier prey).
5. **Idle** — one active task at a time, like a proper macro session. Offline progress is simulated for up to 10 hours and summarized when you return.

## Saving

Autosaves to `localStorage` every 15 seconds and on page close. Export/Import lets you move a save between browsers. Reset starts a fresh character.

## Development

It's a single `index.html` — open it and edit. A debug hook is exposed in the console: `SF.simulate(3600)` fast-forwards an hour of the current task; `SF.state` inspects the game state.
