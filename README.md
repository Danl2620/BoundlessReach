# Readme
Welcome to the Boundless Reach vault!  This is a game using the Starforged TTRPG.


## Folder Structure
1. **Characters:** All the Inline Scripts shortcut commands require that the Characters folder structure remain as it is now.  Any character with stats that you need to access through moves should be in this folder.

2. **Images:** All images are pulled from the Images folder.  You can add additional folders and images, but don't change the structure of the images currently there.

3. **Progress:** Any thing that will have a progress track must go in the Progress folder.  This includes combat tracks, vows, bonds with NPCs, etc.

## Inline Script Commands
While you are free to use any and all of the commands the Inline Scripts offers out of the box, below are explainations of the specific scripts I set up in four different files.  Remember that every Inline Scripts command starts with `;;` and ends with `::` by default.  I won't be able to type the full commands as examples below because it would trigger the scripts.

### Summary of Commands
1. <u>impact {condition} {optional: Which character filename?}</u> - Toggle an impact on/off for the given character.
   
2. <u>burnmom  {optional: Which character file?}</u> - Burns and resets momentum for the given character.
   
3. <u>take {amount} {meter/stat/asset} {optional: Which character filename?}</u> - Adds to given meter, stat, or asset track for the given character.  If you are taking for the command vehicle integrity, you can either type "cv" or "Starship" as the asset name.
   
4. <u>suffer {amount} {meter/stat/asset} {optional: Which character filename?}</u> - Subtracts from given meter or asset track for the given character.  If you are suffering from the command vehicle integrity, you can either type "cv" or "Starship" as the asset name.
   
5. <u>move {initials} {stat/asset name} {add} {optional: Which character filename?}</u> - Makes a challenge roll using the given stat or asset meter and add for the specified move for the given character.  If you are using <u>Withstand Damage</u> for the command vehicle and thus rolling +integrity, you can either type "cv" or "Starship" as the asset name.
   
6. <u>moveref {initals}</u> - Embed the text of a move.
   
7. <u>createprogress</u> - Creates a new progress file for vows, combat tracks, bonds, etc. with popup inputs.
   
8. <u>markprogress {filename} {amount} {optional: Which character filename?}</u> - Marks progress the given number of times on the track in the given file (for the given character if Bonds, Discoveries, or Quests in which case use ticks).
   
9. <u>clearprogress {filename} {amount of TICKS} {optional: Which character filename?}</u> - Clears progress the given number of TICKS on the track in the given file (for the given character if Bonds, Discoveries, or Quests).
   
10. <u>setprogress {filename} {amount of TICKS} {optional: Which character filename?}</u> - Set progress on the track in the given file (for the given character if Bonds, Discoveries, or Quests) to the amount of ticks, meaning the amount is out of 40.
   
11. <u>resetlegacies {optional: Which character filename?}</u> - Resets all legacies tracks and XP earned to 0 for the given character.
   
12. <u>endprogress {filename} {optional: Which character filename?}</u> - Makes the progress move and Fulfill Your Vow or Take Decisive Action on an objective (for the given character if Bonds, Discoveries, or Quests).
   
13. <u>createclock</u> - Create a progress clock with popups.

14. <u>advanceclock {filename} {optional: # of times}</u> - Advances the given clock the given number of times which defaults to filling one segment.

15. <u>setclock {filename} {segments to fill}</u> - Takes an already existing clock and sets it to the given value.

16. <u>endclock {filename}</u> - Marks the given clock as complete.

17. <u>oracle {question}</u> - Ask a question and then select the oracle to roll from the popup menu.

18. <u>yesno {odds} {question}</u> - Ask the oracle a yes/no question with the given odds.

19. <u>at {question}</u> - Ask a question and get an Action/Theme result as an answer.

20. <u>df {question}</u> - Ask a question and get a Descriptor/Focus result as an answer.

21. <u>ptp</u> - Rolls on the oracle from the Pay the Price move.

22. <u>character</u> - Rolls a full NPC with all the character oracles.

23. <u>faction</u> - Rolls a full faction with all the faction oracles.

24. <u>sector</u> - Rolls a full sector including planets and settlements.

25. <u>settlement</u> - Rolls a full settlement using the settlement oracles.

26. <u>starship {region}</u> - Rolls a full starship using the starship oracles in the given region.

27. <u>creature {environment}</u> - Rolls a full creature using the creature oracles of the given environment.

28. <u>planet {class} {region}</u> - Rolls a full planet of the given class in the given region.

29. <u>derelict</u> - Rolls what you initially see at a derelict.

30. <u>vault</u> - Rolls what you initially see at a precursor vault.

31. <u>mech</u> - Adds a generic blue "Mechanics" box if there are some other random game mechanics that you want separated from the fiction.

32. <u>sh {move initials} {optional: character file name}</u> - returns an automatic strong hit for the given move and character.  Giving no character file name defaults to the first character in the Characters folder.

33. <u>wh {move initials} {optional: character file name}</u> - returns an automatic weak hit for the given move and character.  Giving no character file name defaults to the first character in the Characters folder.

34. <u>miss {move initials} {optional: character file name}</u> - returns an automatic miss for the given move and character.  Giving no character file name defaults to the first character in the Characters folder.

35. <u>stats {optional: character file name}</u> - returns all the meter and stat values of the given character.  Giving no character file name defaults to the first character in the Characters folder.

36. <u>roll {amount of dice}d{# of sides}</u> - a generic dice roller that returns the sum of the dice rolled in the heading and the individual rolls in the body of the callout box.

### Details of Individual Commands

1. **starforged_stats.sfile:** This file contains several helper functions that you don't need to worry about as well as the following Inline Scripts commands.
	* **impact {impact name} {optional: Which character filename?}:** This command will turn on or off a condition such as `Wounded` or `Traumatized`.  These are actually unicode open hex or close hex that live in the frontmatter of each character file, and this script flips the unicode symbol back and forth.  NOTE: You must use `Harmed` instead of `Permanently Harmed` since frontmatter variables cannot have spaces in them.
	  
	  <u>Example use:</u> `;;impact wounded Char1` 
	  
	  <hr>
	* **burnmom {optional: Which character filename?}:** This command burns momentum for the given character and gives you a callout box to write out what this mechanically changed.
	  
	  <u>Example use:</u> `;;burnmom Char1`
	  
	  <hr>
	* **take {amount} {meter/stat/asset} {optional: Which character filename?}:** This command adds to a specific meter like `Health`, stat like `Iron`, or an asset's track like a service module's `Integrity` or the `Ammo` on the `Archer` asset.  It will make sure you don't go over the max amount.  You use either the meter name (Health, Spirit, Supply, Wealth, or Momentum), stat name (Edge, Heart, Iron, Shadow, Will), or the asset name (Starship, Glowcat, Archer, etc.).  This command used to be "gain", but I changed it to "take" so the command is the result of the move, like "take 2 Health".
	  
	  <u>Example use:</u> `;;take 2 Archer Char1` will add 2 Ammo to the Archer asset while `;;take 2 Momentum Char2` will add 2 Momentum to the character with filename `Char2`.
	  
	  <hr>
	* **suffer {amount} {meter/stat/asset} {optional: Which character filename?}:** The opposite command from above which will make sure you don't go below the minimum amount.  If you need to lose more `Health` than you have, it will give you a message informing you so that you can decide if you need to lose more of something else (like `Momentum`) to compensate.
	  
	  <u>Example use:</u> `;;suffer 2 Momentum Char1` will subtract 2 Momentum from the character with filename `Char1`.

2. **starforged_moves.sfile:** This file sets up shortcuts to use with moves.  The commands are as follows:
	* **getmovename {initials}:** This is a helper function that you will never use directly, but it does explain how you need to reference moves.  To use a move, use it's initials in the command unless it's only a single word move in which case you use the full name.  This shortcut then expands it to the full name.
	  
	  For example, `AYA` will give "Aid Your Ally" while `BATTLE` is necessary for the "Battle" move.  There are a few exceptions which are:
		  - All the "Face Something" moves have the same initials of `FD`.  Therefore, `FD` = Face Danger, `FDEATH` = Face Death, `FDEFEAT` = Face Defeat, and `FDESOLATION` = Face Desolation.
		  - Fulfill Your Vow and Forsake Your Vow are both FYV, so they can be referenced with `FULFILL` and `FORSAKE`.
	  
	  <hr>
	* **move {initials} {stat} {add} {optional: Which character filename?}:** This command will be used frequently because it's how you perform moves.  The {initials} were explained previously, but now you'll need to also give the {stat} you're using to make the challenge roll and an amount to {add} using 0 if there is no add.  You also need to give it the character filename to pull the stats from if you have multiple characters.  This returns a green callout box for a strong hit, orange for a weak hit, and red for a miss. 
	  
	  <u>Example use:</u> `;;move saa wits 1 Char2` will make a challenge roll with Wits from the character with filename `Char2` and an add of +1 on the Secure An Advantage move.  `;;move compel iron 0 Char1` makes a challenge roll with Iron from the first character and no add on the Compel move.
	  
	  <hr>
	* **moveref {initials}:** Embeds a callout box with the text of the referenced move.  This is incase you want to read the text of the move but not open a different note to do so.
	  
	  <u>Example use:</u> `;;moveref fd` will embed the Face Danger move.
	  
	  <hr>
	* **mech:** Embeds a generic mechanics callout box in case you want to detail some mechanical consequence or action.
	  
	  <u>Example use:</u> `;;mech` creates a blue callout box.

3. **starforged_progress.sfile:** This file contains the commands necessary to interact with your vows, bonds, combat tracks, etc.  Anything that uses a progress track should run through these commands.
	* **createprogress:** This command will create a new note in the Progress folder, apply the template, and use your inputs for the filename, name of the vow (or bond or combat), and the difficulty level.
	  
	  <u>Example use:</u> `;;createprogress` will create a new progress track file in the Progress folder.
	  
	  <hr>
	* **markprogress {either the filename that contains the progress track or use the one-word references of Bonds, Discoveries, or Quests} {amount} {optional: Which character filename?}:** This command marks progress the given amount of times on the progress track contained within the given file.  You give it the number of times to mark progress on a normal progress track (or the number of tick marks if marking Bonds, Discoveries, or Quests).  For example, if you want to mark progress twice on a Dangerous vow, use 2 (progress) and not 16 (the # of ticks marked with two progress of two boxes each).
	  
	  <u>Example use:</u> `;;markprogress PirateFight1 1` will mark progress once filling in the appropriate number of tick marks depending on the Difficulty level of the vow.
	  
	  <hr>
	* **clearprogress {either the filename that contains the progress track or use the one-word references of Bonds, Discoveries, or Quests} {amount of TICKS} {optional: Which character filename?}:** This command clears progress the given amount of TICKS on the progress track contained within the given file.  Some moves says clear progress boxes and others say units of progress, so I had to use the number of ticks.  That means if it says to clear four boxes, you would use 16 ticks.  If it's a dangerous vow that says to clear three units of progress, that would be six boxes meaning you would use 24 ticks.
	  
	  <u>Example use:</u> `;;clearprogress Bonds 2 Char2` will clear 2 ticks of progress on the Bonds track for the character with filename `Char2`.
	  
	  <hr>
	* **setprogress {either the filename that contains the progress track or use the one-word references of Bonds, Discoveries, or Quests} {amount} {optional: Which character filename?}:** With this command you can set any progress track to any value you need.  The amount should be given in the number of ticks.  That means for regular progress tracks it should be out of 40, and for Legacy tracks it should be out of 80.
	  
	  <u>Example use:</u> `;;setprogress Bonds 53 Char2` will set the Bonds track for the second character to 13 ticks becuase it rolled over at 40.  It will also recalculate XP Earned at this time.
	  
	  <hr>
	* **endprogress {either the filename that contains the progress track or use the one-word references of Bonds, Discoveries, or Quests} {optional: Which character filename?}:** This command makes the final progress move to Fulfill Your Vow or Take Decisive Action on an objective and it marks the file as a completed vow.
	  
	  <u>Example use:</u> `;;endprogress PirateFight1` will roll the challenge dice and compare them to your current progress.  
	  
	  <hr>
	* **createclock:** This command creates a new file in the Clocks fiolder to track a progress clock.  Popup menus allow you to set the filename (like "Clock1"), a name for clock (like "Incoming Storm"), and how many total segments the clock should have (4, 6, 8, or 10).
	  
	  <u>Example use:</u> `;;createclock` will create a new progress clock
	  
	  <hr>
	* **advanceclock {filename} {optional: # of segments to fill}:** This command advances the clock stored in the given filename the given number of segments.  If not segments are given, it defaults to advancing the clock one pie wedge.
	  
	  <u>Example use:</u> `;;advanceclock Clock3` will advance the clock in the file Clock3 once. Alternately, you could say `;;advanceclock Clock3 2` to advance the clock twice (fill two pie wedges).
	  
	  <hr>
	* **setclock {filename} {number of filled wedges}:** This command sets the clock stored in the given filename to the given number of filled wedges.
	  
	  <u>Example use:</u> `;;setclock Clock3 7` will set the progress clock to have seven segements filled.  If this is more than the maximum number of wedges you can have filled, it will set it to the max.
	  
	  <hr>
	* **endclock {filename}:** This command marks the progress clock stored in the given filename as complete.  You can then add details as to what exactly this means in the callout box that is created.
	  
	  <u>Example use:</u> `;;endclock Clock3` will mark the progress clock stored in Clock3 as complete and then give you a callout box for you to add more details as to what the consequences of that are.
	  	  
4. **starforged_oracles.sfile:** This file contains all the shortcuts for rolling oracles.
	* **getoracle {file path}:** This is a helper function that you don't ever need to use.  It is used by the other commands but needed to be an actual shortcut rather than a true JS function.  The specific purpose of this function is to check for Action/Theme, Descriptor/Focus, or Roll Twice results and then substitute those new oracle results in.
	  
	  <hr>
	* **oracle {question}:** This command allows you to ask a question and then calls up the oracle selection menu where you can select the appropriate oracle.
	  
	  <u>Example use:</u> `;;oracle What is the next zone in the derelict?` will bring of the oracle selection menu where you can select the appropriate Derelict oracle.
	  
	  <hr>
	* **yesno {odds} {question}:** This command is the basic Ask the Oracle move giving a yes/no answer based on the given odds.  Use initials for the odds like AC = Almost Certain, L = Likely, FF = Fifty/Fifty, U - Unlikely, and SC - Small Chance.  This does note results with a match and returns the number value rolled.
	  
	  <u>Example use:</u> `;;yesno FF Will there be hotdogs?` answers the question with a 50/50 likelihood.
	  
	  <hr>
	* **at {question}:** Ask a question and get an Action/Theme response.
	  
	  <u>Example use:</u> `;;at What is the hidden agenda of the faction?` will answer the question by rolling an Action/Theme.
	  
	  <hr>
	* **df {question}:** Ask a question and get a Descriptor/Focus response.
	  
	  <u>Example use:</u> `;;df What is the nature of the advanced technology?` will answer the question by rolling a Descriptor/Focus.
	  
	  <hr>
	* **ptp:** Rolls on the Pay the Price oracle.
	  
	  <u>Example use:</u> `;;ptp` gives a result such as "You are harmed" from the Pay the Price move.
	  
	  <hr>
	* **sector:** Gives a random sector including planets and settlements.
	  
	  <u>Example use:</u> `;;sector` gives a full sector
	  
	  <hr>
	* **character:** Gives a new NPC including the Name, Callsign, First Look, Initial Disposition, Revealed Aspect, Role, and Goal.
	  
	  <u>Example use:</u> `;;character` gives a full NPC
	  
	  <hr>
	* **settlement:** Rolls all the settlement oracles at once.
	  
	  <u>Example use:</u> `;;settlement` gives a full settlement
	  
	  <hr>
	* **faction:** Rolls all the faction oracles at once.
	  
	  <u>Example use:</u> `;;faction` gives a full faction
	  
	  <hr>
	* **starship {optional: region}:** Rolls all the starship oracles using results from the tables within the specific region (Terminus, Outlands, or Expanse).  If you don't type in a region, it defaults to Terminus.
	  
	  <u>Example use:</u> `;;starship` gives a starship in Terminus while the command `;;starship expanse` gives a starship in the Expanse.
	  
	  <hr>
	* **creature {optional: environment}:** Rolls all the creature oracles for the given environment.  If environment is left blank, it randomly rolls the environment first before rolling the rest of the oracles.
	  
	  <u>Example use:</u> `;;creature air` gives a creature using Air as its environment while `;;creature` gives a creature from a random environment.
	  
	  <hr>
	* **derelict:** Rolls the Location/Type, Outer First Look, Condition, and starting Zone of a derelict.
	  
	  <u>Example use:</u> `;;derelict` gives the above listed oracle results.
	  
	  <hr>
	* **vault:** Rolls the Location, Outer First Look, Form, Scale, Material, and Shape of a precursor vault.
	  
	  <u>Example use:</u> `;;vault` gives the above listed oracle results.
	  
	  <hr>
	* **planet {class} {optional: region}:** Rolls the oracles for a planet of the given class in the given region.  Leaving the region blank will default to Terminus.  If you want a random class of planet, type `Random` in the {class} section.
	  
	  <u>Example use:</u> `;;planet vital outlands` gives the oracle results from a Vital planet in the Outlands while `;;planet random expanse` gives a planet of a random class in the Expanse while `;;planet random` gives a planet of a random class in Terminus sine no region is listed at the end of the command.
	  
## Support Folder
This folder contains all the Inline Script shortcut files.  If you are making your own shortcut files, add them here.

## Templates Folder
The Templates folder is necessary for creating new files with progress tracks.  However, the Oracle, Move, and Asset templates were only used for importing JSON data and can safely be removed.  You can also add any other templates to this file that you would like the Templater plugin to have access to.

## Credits
All original Assets, Moves, and Oracles are from [Dataforged](https://github.com/rsek/dataforged), the official Starforged repository. Starsmith: Expanded Oracles, Starsmith: Mecha Merc assets, and Starsmith: Assets are my original works (available in PDF and print form on [DriveThruRPG](https://www.drivethrurpg.com).)

Image, Map, and Stethoscope icons from [Lucide](https://lucide.dev/)

All other icons from [game-icons.net](https://game-icons.net) by Delapouite, et. al.

This set-up only works with the [Dataview](https://github.com/blacksmithgu/obsidian-dataview), [Templater](https://github.com/SilentVoid13/Templater), and most importantly: [Inline Scripts](https://github.com/jon-heard/obsidian-inline-scripts) plugins.
