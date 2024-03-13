## Planning an Achievement Set

### Deciding on Game Version

Many games were released in different regional formats and versions. Often, a game’s RAM is not consistent between formats and a developer must decide which the set will support. Once a particular game format/version is selected, if it is not already linked to the set, a developer will link, or associate, it with the set using the RA developer toolkit.

### Selecting Between NTSC and PAL Format

Games are either NTSC or PAL format depending on which region they were released due to differing worldwide television standards. US and Japanese releases are NTSC while EU releases are PAL. NTSC runs at either ~60 or 30 frames per second (FPS) whereas PAL runs at either ~50 or 25 FPS. Although RAM addresses may be consistent between NTSC and PAL releases, it is not uncommon to find that address values differ between the formats. Additionally, due to FPS differences, achievements based on time will not be consistent between formats in most cases. Creating a set that is equivalent with both formats is possible, but often will take significantly longer development and testing effort to ensure compatibility.

There are three options for format selection when considering a set, support NTSC only, support PAL only, or support both. Due to FPS performance, NTSC should be the default format to support. In more advanced consoles, PAL releases typically have additional language support which may be worth sacrificing FPS to support. A developer should consider the tradeoff between FPS and language support. For an RPG, additional language support is likely more valuable to the player base than higher FPS, however for a fast paced game, higher FPS may be more important.

### Selecting Game Version

Many games were released in different versions, usually to fix bugs that were not known at the time of initial release. In almost all cases, the latest version of a game should be supported by the set. In many cases, supporting earlier versions of the game is viable because the vast majority of RAM will be identical, however earlier versions may contain bugs or exploits that may not result in the intended player experience if abused. There is not an especially compelling reason to support multiple versions of a game in almost all cases.

### RA Hashing

RA uses a hashing algorithm to assign a unique code to each game, called a hash. The hash is then associated or “linked” with a particular achievement set such that RA can reference a particular set of achievement code when a game is being played. Sets can have multiple linked hashes.

### Patched Games

Patched versions of games may be linked to sets as well for things such as language translations, cosmetic updates, debug function removal or similar reasons. Patches that alter gameplay or difficultly in any way are prohibited without expressed permission from Developer Compliance. A patched game can be linked to the set the same way a standard release version is linked. All linked patched games must have their patches submitted to the RAPatch repository. Information on how to do this is available in the RAPatches forum in the RA discord.

Once a developer has linked the hash(es) the set will support, the next step is to plan the achievement set. 

### Achievement Set Plans

An achievement set plan is working document that a developer uses to guide and track set development progress. The set plan should be understood as a malleable document to be refined throughout development to ensure the best possible final product is produced. It will aid a developer with organizing a set and guide them throughout the development process. It is similar to creating an outline for an essay. A set plan may contain some of or all the following:

- a list of intended achievements
- ideas for potential achievements
- intended achievement features such as measuring or challenge indicators
- ideas for titles and descriptions
- badge creation status
- planned point values
- a place to keep notes for future reference
- individual achievement coding and testing status
- anticipated RAM digging needs

Having a flexible and iterative plan can significantly improve the overall process and help a developer create the set they envisioned efficiently and effectively. This article will offer techniques used by experienced developers, but it is important to understand that there are many methods by which to develop a set and it’s important for a developer to find a method that works well for them.

### Fundamentals Of An Achievement Set Plan

#### Tools

Many developers organize their set plans on spreadsheets. Google Sheets is an outstanding tool for creating and managing a set plan. In addition to being a versatile tool by itself, Google Sheets can be shared by multiple users and is quite beneficial in collaborations with other developers and art team members.

[Example Set Plan sheets](https://docs.google.com/spreadsheets/d/1VC2phJ9AUcZK5Ll4bVuMpJXED8QdM_nw8OdSAuLc3bI/)

#### Research

The first step in building a set plan is to consider what types of achievements a developer intends to put into the set. Developers will use resources such as long play videos, faqs, wikias and other dedicated websites to learn as much about the game as possible. This is essential to ensuring the set will cover the game’s full content. Even if a developer is already very knowledgeable about a game, it may still behoove them to conduct some research in the event there is content of which they are unaware.

### Achievement Types

There are several types of achievements should be considered when developing a set plan. This section will list and explain these acheivement types.

- Progression
- Optional content
- Collection
- Challenge
- Easter egg/for fun

#### Progression Achievements

Progression achievements are awarded for completing specific, mandatory parts of a game as a player progresses towards beating the game in an intended way, including beating the game itself. Progression achievements must be unable to be avoided by a player. RA achievements should be for completing levels or tasks, not for reaching them. Examples of valid progression achievements include:

- Defeat Frankenstein’s monster (Castlevania)
- Defeat Dr. Robotnik the Final Zone (Sonic the Hedgehog)
- Defeat the Lich and purify the Earth Crystal (Final Fantasy)

Progression achievements should be spaced out throughout the course of a game at relatively consistent intervals and be awarded when significant progress in the game is made. Avoid spoiling major plot points with your achievement descriptions. It’s acceptable to be vague as progression achievements cannot be missed. Points awarded for progression achievements should generally begin at 5 and possibly progress to 10 nearing the end of the game with 25 being the stand point value for a beating the game achievement. Consider the total accumulation of points a player will earn in a playthrough from each of the progression achievements and score them accordingly so the total is a fair reflection of the time and effort requirement.

#### Optional Content Achievements

Optional content achievements are awarded for completing non-mandatory things in a game such as side-quests or alternate routes. Optional content may sometimes seem like progression, but in cases such as games with warps, may not actually be mandatory when beating a game. Examples of valid optional content achievements include:

- Complete the second quest (Castlevania)
- Collect 6 Chaos Emeralds (Sonic the Hedgehog)
- Receive King Bahamut’s praise and his reward (class change) (Final Fantasy)

Optional content can best be described as deliberately included game content that is not required to complete the game, but is clearly present to offer additional gameplay experience to players. In many cases, completion of optional content is rewarded by the game. This can be a good indication as to whether the optional content should be considered worthy of a dedicated achievement.

#### Collection Achievements

Collection achievements are awarded for collecting things. Common use cases of collection achievements are for acquiring the best weapon in an RPG and collecting all items or treasures in a particular stage or playthrough. Examples of valid collection achievements include:

- Break all item containers and find the hidden treasure on Stage 8 (Castlevania)
- Collect 100 rings (Sonic the Hedgehog)
- Obtain Masamune (Final Fantasy)

Collection achievements should have some significance driving them such as clearing an area of all its items, obtaining an especially useful, uncommon item, or collecting enough items to be rewarded by the game. If a game has many levels or areas, to avoid spam, consider grouping sections together and creating a single collection achievement that covers several areas.

#### Challenge Achievements

Challenge achievements are awarded for completing developer created challenges within a game. The three most common types of challenges are limitation, time-based and score-based. A limitation challenge requires a player to do something in game with certain restrictions imposed by the developer. Examples of limitation challenge achievements include:

- Complete stages 1 through 3 without using a subweapon (Castlevania)
- Complete Green Hill Zone with no more than 1,000 points (Sonic the Hedgehog)
- Defeat Tiamat with an attack from a Warrior or Knight (Final Fantasy)

A limitation challenge achievement is awarded for a player completing a task under developer specified restrictions such as beating a stage without dying or being damaged.

A time-based challenge achievement is one that requires a task to be done in a certain amount of time. Common time-based challenge achievements are for things like beating levels, beating bosses or collecting a certain number of items in a limited time.

A score challenge achievement is awarded for achieving significant scores.

#### Easter Egg/For Fun Achievements

Some games may have some additional content that is inconsequential and easily missed, but a developer may want to highlight to players who would likely otherwise be unaware of the content. These achievements are typically fairly easy to earn, confer low points, and do not have significant impact on the game play experience. Examples of Easter Egg/For Fun achievements include:

- Complete the secret slider puzzle (Final Fantasy)
- Stay in the bath for a little too long… (Suikoden)
- Start a cucco frenzy (The Legend of Zelda: A Link to the Past)

Easter Egg/For Fun achievements are a way to show players the extra details the game developers put in to make the experience more fun than it otherwise would have been.

### Creating An Initial Set Plan

It is helpful to create a rough draft or initial set plan after conducting the research phase of set design. A developer may use one of the sample set plan spreadsheets or use any other form of organizational medium that they choose. Personal preference is important such that a developer continues to utilize the process and receive the maximum benefit.
An initial set plan gives a developer a baseline from which to update throughout the course of set development. During development playthroughs, a developer should expect to make numerous revisions to the set plan as achievement ideas are tested for validation, new ideas are considered and set pacing is better understood. This iterative process ensures ideas are refined and fully matured for the set’s release.

The two most common methods of organizing an initial set plan are by achievement type and expected chronology. Both methods have their own strengths and weaknesses. Listing achievements by type helps to ensure that nothing is accidentally omitted because it is easier to scrub lists of similar types for totality. Plans ordered by achievement type help ensure a developer maintains a desirable balance in achievement types by grouping types of achievements together for easy comparison. Chronologically ordered lists are easier to work with during the development phase as a developer knows which achievement will be the next one they will encounter and will be better prepared to create necessary saves to use for coding and testing.

### Refining The Set Plan During Development

Once a developer has an initial set plan, they should begin playing through the game. As they reach sections of the game with planned achievements, they should consider how their current achievement ideas, how well paced the set is to ensure players are rewarded at appropriate and meaningful intervals, and be on the lookout for other achievement opportunities which were not previously considered.

Many factors such as new acheivement ideas, implementation feasibility due to memory constraints, trigger timing preference, additional features such as measurements or challenge indicators, and many other may necessitate updates to the set plan. When playing through the game, context that may be helpful for achievement titles or badges may also present itself which should be captured on the set plan. Additionally, a developer may recognize opportunities for creative leaderboards during development which can be added to the plan.

### Finalizing The Set Plan 

Achievements may be coded as they are encountered during the development playthrough or after the playthrough by utilizing saves. In either case, the set plan is a valuable tool to ensure that all intended achievements, features, and leaderboards are well accounted. At the conclusion of development, the set plan will ultimately serve as a checklist to ensure that exactly what the developer wants in the set has been created and thoroughly tested. When a set plan is ultimately finalized following set testing, the set is ready for promotion.

### Common Set Planning Mistakes

The most common set planning mistake is resistance to changing the set plan during development. The set plan is a tool, not a compulsory mandate. Commonly, ideas that may have initially seemed good often require implementation changes to maximize the player experience or outright removal from the plan. A bad player experience may be poor set pacing such as collecting items or beating short stages in rapid succession and receiving an award for each of them, unbalanced challenge difficulty such as one or two challenges that are far more difficult than anything else in an otherwise relatively easy set, or untimely achievement awarding such as awarding achievements at unsatisfying times like at the start of the next stage as opposed to the end of the previous one.

### Take Aways

It is vital to challenge your ideas throughout development and seek feedback from potential players to take into consideration. Creating a poll in the #poll-me channel of the RA discord is a great way to quickly get feedback from potential players.  Additionally, seek out advice from experienced developers if you are unsure of an idea. Building and using a set plan is a great way to ensure a developer delivers a fantastic experience to the players of the set. Set plans are simple to create and maintain throughout development and will likely save a significant amount of time or result in a better overall set.