# UndertaleModTool
*(seeing such an amazing tool...<br/>
... fills you with DETERMINATION.)*

heya. i heard you like digging deep into Undertale data so i made a tool just for you! 

**Downloads** are **HERE**: :point_right::point_right::point_right: https://github.com/krzys-h/UndertaleModTool/releases :point_left::point_left::point_left:

**Have questions? Want to talk?** Join us on Discord! https://discord.gg/RxXpdwJ

![flowey](flowey.png)

### Main features
* Can read every single byte from the data file for lastest version of Undertale, Deltarune, and probably other GameMaker: Studio games (GM:S 1.4 and GMS2 bytecode versions 14 to 17 are currently supported) for every platform and then recreate a byte-for-byte exact copy from the decoded data.
* Properly handles all of the pointers in the file so that if you add/remove stuff, make things longer/shorter, move them around etc. the file format won't break.
* An editor which lets you change (almost) every single value, including unknown ones.
* Includes a (very) simple room/level editor.
* Allows for code disassembly and editing. This means you can add any custom code to the game, either using the built-in GML compiler or GML assembly.
* Experimental high-level decompiler. The output is accurate (except for the latest GameMaker versions), but it could use some more cleaning up of the high-level structures.
* Support for running scripts that automatically modify your data file (or perform other nefarious tasks) - this is the way to distribute mods, but creating them is a manual job for now. It also serves as a replacement for sharing hex editor offsets - if you make it into a file-format-aware script instead, there is much smaller change of it breaking after an update.
* All core IO functionality extracted into a library for use in external tools.
* Can generate an .yydebug file for the GM:S debugger so that you can edit variables live! (see [here](https://github.com/krzys-h/UndertaleModTool/wiki/Corrections-to-Game-Maker:-Studio-1.4-data.win-format-and-VM-bytecode,-.yydebug-format-and-debugger-instructions#yydebug-file-format))

### Included scripts
Included are some test scripts. They are:
* Universal:
  * EnableDebug: does just that, makes the global variable 'debug' be enabled at game start. If you don't know about Undertale's debug mode, check out https://tcrf.net/Undertale/Debug_Mode
  * DebugToggler: similar to the above, but instead toggles the debug mode on and off with F1
  * GoToRoom: Replaces the debug mode functionality of the F3 button with a dialog that lets you jump to any room by ID
  * ShowRoomName: Displays the current room name and ID on screen in debug mode
  * Search: Simple search for text in decompiled code entries
* Undertale only:
  * BorderEnabler: lets you import the PlayStation exclusive borders into the PC version and patches all version checks so that they display properly
  * testing: nothing important, just displays random text on the main menu - the first script I ever made
  * TTFFonts: Makes the game load fonts in TTF format from current directory instead of using the spritesheet fonts. You will need to track down all the font files yourself, I can't host them here for licensing reasons :(
  * RoomOfDetermination: Adds a new room to Undertale 1.08. I wanted to add something more to it but never got around to it, so I guess I'm releasing it as is. Just start the game and you'll see. Probably the most complete sample of adding stuff you'll find.
* Deltarune only:
  * DeltaHATE: [HATE](https://www.reddit.com/r/Undertale/comments/41lb16/hate_the_undertale_corruptor/)-inspired script for corrupting Deltarune
  * DeltaMILK: Replaces every non-background sprite with the K.Round healing milk. Don't ask why.
  * TheWholeWorldRevolving: The world is spinning, spinning
  
Additionally, included are some community-made scripts, "experimental scripts." For more information, consult the README file inside that directory.

### Bug reports, contributing
All contributions are welcome! If you find a bug, a data file that does not load etc. please report it on the [issues page](https://github.com/krzys-h/UndertaleModTool/issues). Pull requests and help with decoding the format is welcome too! Here is a current list of stuff that needs to be worked on:
* Add missing chunk editors for Timelines and Extensions
* Add support for YYC games - you won't be able to edit code, but everything else should technically work
* Add support for latest versions of GameMaker (notably, 2.3) - decompiler cannot function in most cases currently

### data.win file format
Interested in the file and instruction format research I've done while working on this? Check out these:
* https://github.com/krzys-h/UndertaleModTool/wiki/Corrections-to-Game-Maker:-Studio-1.4-data.win-format-and-VM-bytecode,-.yydebug-format-and-debugger-instructions
* https://github.com/krzys-h/UndertaleModTool/wiki/Changes-in-Game-Maker:-Studio-2
* https://github.com/krzys-h/UndertaleModTool/wiki/Extensions,-Shaders,-Timelines-format
* https://github.com/krzys-h/UndertaleModTool/wiki/Bytecode-version-differences
* https://github.com/krzys-h/UndertaleModTool/wiki/YYC-games

### Special thanks
Special thanks to everybody who did previous research on unpacking and decompiling Undertale, it was a really huge help:
* https://pcy.ulyssis.be/undertale/
* https://github.com/donkeybonks/acolyte/wiki/Bytecode
* https://github.com/PoroCYon/Altar.NET
* https://github.com/WarlockD/GMdsam
* [@NarryG](https://github.com/NarryG) for [helping me figure out](https://github.com/krzys-h/UndertaleModTool/issues/3) the missing stuff for GMS2 and Nintendo Switch release
* [@colinator27](https://github.com/colinator27) for [lots of things, including the gml compiler](https://github.com/krzys-h/UndertaleModTool/issues/4), [Sha](https://github.com/krzys-h/UndertaleModTool/issues/13)[ders](https://github.com/krzys-h/UndertaleModTool/pull/25) and [a bunch of other stuff](https://github.com/krzys-h/UndertaleModTool/pull/30)
* [@Kneesnap](https://github.com/Kneesnap) for [improving the decompiler a bunch](https://github.com/krzys-h/UndertaleModTool/pull/162)

And of course, special thanks to Toby Fox and the whole Undertale team for making the game(s) ;)

How about a random screenshot because I'm bad at writing READMEs? NYEH HEH HEH HEH!

![screenshot](screenshot.png)
