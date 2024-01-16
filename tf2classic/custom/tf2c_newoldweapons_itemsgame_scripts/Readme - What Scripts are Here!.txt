Hi! Here's a quick overview over what kind of scripts you can find sitting in the open, here!
I strongly encourage you to poke around at them if you have any interest in modding!

There's 4 groups of scripts, I'll list their files too.



//---------------//
-items_game (For adding / modifying TF2C Weapons)
[scripts/items/items_game.txt]
[scripts/items/items_game_tf2c.txt]
[scripts/items/custom_items/New-Old Weapons Pack!.txt]

[maps/itemtest_4team_items_game.txt]
[maps/itemtest_4expanse_items_game.txt]


These files control everything about TF2C's weapons and their stats!
Thus, you can use and modify them to create brand new weaponry, or tweak existing weapons.

The one in [scripts/items/items_game.txt] is a "global" file for the entire game - ALL the game's weapons across ALL maps are handled by this!
It hooks two files, "items_game_tf2c.txt", which is a copy of TF2C's default items_game.txt, and "New-Old Weapons Pack!.txt", which is this Weapons Pack's stuff!
It also theoretically can hook other Weapons Packs, too, so I included some hooks for other popular weapons collections I know of! Some assembly required.

Meanwhile, the ones in [maps/themapnames_items_game.txt] are custom items that ONLY work on a certain map!
The two here only activate on "itemtest_4team" and "itemtest_4expanse", respectively! You can copy + rename these files to add more maps by hand!

Additionally, I left a gajillion code-comments inside them. Please give them a read - they might help
figure out how some tricky or weird weapons work!



//---------------//
-game_sounds (For adding sound effects / soundscripts into TF2C)
[scripts/game_sounds_manifest.txt]
[scripts/game_sounds_custom_nowp.txt]
[scripts/game_sounds_weapons.txt]


These files are essentially what the game looks at to figure out how to "play" a sound;
their pitch, volume, fade-out level, and if there's other random sounds to worry about!

Importantly, the game checks [scripts/game_sounds_manifest.txt] first for a list of subfiles to load!
If you peek in there, you'll notice I made a bunch of includes for files that don't exist. That's for you guys!
After it does that, it reads soundscripts from whatever it loaded.

[scripts/game_sounds_weapons.txt] is all the Sound Effects scripts from Live TF2 / "Normal" TF2. 
Literally the same file. If you need, go replace it!

[scripts/game_sounds_custom_nowp.txt] is for sound stuff added exclusively by New-Old Weapons Pack!
If you need to add your own, do it through another file hooked the same way!



//---------------//
-response_rules (For adding voice lines for events in the game)
[scripts/talker/response_rules.txt]
[scripts/talker/Global_Taunts.txt]
[scripts/talker/custom_responses_nowp.txt]


This one is the hardest to understand, so I don't blame you if you don't wanna bother with them.
In a nutshell, these files control some "Responses" - ways characters react to stuff that happens in-game?

That first file, [scripts/talker/response_rules.txt], is used to include other files, kinda the same way game_sounds_manifest.txt does!
All of the include hooks are at the VERY bottom of the file for loading purposes - otherwise, it's the same.
In previous versions, this used to be Pyro.txt! If you still have that, please remove it!

The other two, [scripts/talker/Global_Taunts.txt] and [scripts/talker/custom_responses_nowp.txt], are for
adding Taunting to Randomizer Mode, and New-Old Weapons Pack's voice + taunt responses, respectively!



//---------------//
-particles (For custom particles / VFX on weapons)
[particles/particles_manifest.txt]


Fairly straightforward, this singular file is a hook file that points to a bunch of .pcf "Particle" files that have, well, particles and effects!
The only file of note, [particles/particles_manifest.txt], points to a .pcf file for NOWP, "nowp_wpnfx.pcf" and variants, and also
includes several hooks for either custom particles, or, if you need them for some reason, common Live TF2 particles that weren't included in TF2C



//---------------//
-weapon_scripts (For base Weapon properties)
[scripts/tf_weapon_grenadelauncher.txt]
[scripts/tf_weapon_pipebomblauncher.txt]
[scripts/tf_weapon_revolver.txt]


These are BIG files to be changing, but hopefully it doesn't have much impact. These just add some shell-casing models for the
Grenade Launcher, Stickybomb Launcher, and Revolver. The other properties are 100% untouched, and none of these weapons eject anything either way
unless the models have attachments for 'em (none of them do by default). These are minor and can be removed at your discretion!