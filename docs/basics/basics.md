## How It Works

An achievement consists of multiple conditions that must be true in order for it to be awarded. These conditions are based on logic that utilizes a game's RAM. If an emulator or core supports RetroAchievements, the achievement processing will begin upon loading a game. The conditions for each achievement are constantly scanned to see if they have been met. Once all conditions have been met, the achievement will unlock. After all achievements in a set have been unlocked, the player will earn the game's mastery badge.

The typical process of creating an achievement involves these steps:

- Finding addresses in the game's RAM where relevant information is stored. Examples include stage or map ID, current health, timer, points, inventory slots, etc.
- Create conditions that make up the logic
- Test if the achievement is working as expected

It is very common for these steps to be repeated multiple times in order to stabalize an achievement.

## Getting Started

Ensure that you have an emulator from the website's [download page](https://retroachievements.org/download.php).

For the purposes of this guide, we'll use RALibRetro with the Genesis Plus GX core to demonstrate and the game [Sonic the Hedgehog](http://retroachievements.org/Game/1). We are using RALibRetro but the same applies to any emulator that supports [RAIntegration](https://github.com/RetroAchievements/RAIntegration).

To begin, run the RALibRetro executable and login when prompted. If you have not used the Genesis Plus GX core before, you can install it by going to Settings -> Manage Cores -> selecting Sega Genesis in the drop down menu -> clicking Download to the right of the core name. Once the core is installed, go to File -> Select Core -> Sega Genesis -> Genesis Plus GX. Now that you have the core selected, you'll need to load the game. Go to File -> Load Game and select the Sonic the Hedgehog ROM (we recommend using No Intro ROMs by default).

## Memory Inspector

You should now have your main window running Sonic. There are 3 other dialogs we'll be using, which can be found under **RetroAchievements** in the menu. We'll be dealing with the **Memory Inspector** first:

![memoryinspector](/img/basics-memoryinspector.png)

The Memory Inspector can be used to find addresses in RAM for us to use. Essentially you are on a treasure hunt for memory locations - this dialog will help you examine and filter the game's RAM while the game is running.

**NOTE: If you want a step-by-step video explanation on finding memory addresses, you can [view this updated video](https://www.youtube.com/watch?v=7ZMlBVyHl5M).**
**For another video resource, you can [view this older video](https://www.youtube.com/watch?v=8nYb_5cgQHY)**.

**See also**: [Memory Inspector Overview](Memory-Inspector-Overview) and [Memory Digging Tips](Tips-and-Tricks#memory-digging-tips).

To keep things simple, we'll start by looking for the memory address which holds the number of rings we have collected:

- Load the game and ensure the Memory Inspector window is open
- Start a new game
- Click the **New Search** button in the Memory Inspector
- Run your first filter by clicking **Filter Once**
  - Clicking on addresses in the results window will jump to those addresses in the **Memory View** and allow you to monitor them while playing the game.
- Play the game for a moment, but do not collect any rings
- Run a second filter by clicking **Filter Once** again
- Return to the game, but this time collect at least one ring
- In the Memory Inspector window, changed the **Filter** to **>** and click **Filter Once** again
  - Each time you perform the last two steps, the number of results will get smaller. Continue doing this until there are only 5-10 results; it may take several attempts.
- Continue with the game and you should see the values in memory change as you collect rings. If you don't, or if something doesn't look right, try another address. With the first Sonic the Hedgehog, the memory address for the number of rings is `0xfe20`.

!!! note "Save States"
    If you use save states, you can switch back and forth between them  to alter what is in RAM. This is a great way to filter out bad candidates. You can search for values that remain the same (I.e. If you know the value didn't change, use `=`), or values that are different (use 'not equal', symbol `!=`). Using the example above, you can collect a ring then use the ">" filter, take a few steps then use the "=" filter (since the number of rings did not change), collect more rings and use the ">" filter again, etc.

!!! note "Every Game Is Different"
    There's unfortunately no guarantee from game to game on how the developers have stored their data (4-bit, 8-bit, 16-bit, binary-coded decimals, negative/inverted, i.e. using 0xff/0xffff to represent 'set', or plain randomly), but eventually you should come across some good addresses. If you are struggling to find good values, remember that there is no shame in asking for help!

!!! note "Tip"
    Try entering new values directly into the memory viewer. This can have devastating effects on a game, do exactly what you expect, or do nothing at all! Use with caution!

When you have found an address you are happy with, you can type a note in the **Code Notes** window and click **Publish**. This will store the note in the database.

!!! note "Publishing Code Notes"
    When a code note is published, it is being saved to the RetroAchievements database. It will appear in the **Memory Inspector** the next time you load the game and on the website via the Code Notes section for that game entry.

You can find more useful [Memory Digging Tips here](Tips-and-Tricks#memory-digging-tips).

## Achievement Sets

So the memory location for the number of rings is stored at `0xfe20` - note to a non-programmer, we're dealing in [hexadecimal numeral system](https://simple.wikipedia.org/wiki/Hexadecimal_numeral_system) which can be daunting, but don't worry, essentially it's just numbers and letters instead of only numbers, and not forgetting `0x` at the start to show that it's a memory location in hex. We've found an address we're interested in and stored it using **Publish**. We now want to create a new achievement.

Go to the **RetroAchievements** in the menu, choose **Assets List** and you'll see this dialog:

![assetslist](/img/basics-assetslist.png)

Here we group all the achievements we know about into three sets:

1. Core Achievements (the main, public Achievement set),

2. Unofficial/User Achievements (public, but will not award you points: for peer review),

3. Local Achievements (exclusive to your PC).

In the Achievements dialog, click **Local Achievements** (top left), then **Add New Achievement** (top right). This will add a blank entry to the list in the center. Double click on it: if it's not already open, this should select it and open the **Achievement Editor** dialog.

## Achievement Editor

This is how it looks:

![achievementeditor](/img/basics-achievementeditor.png)

This is the final dialog where we bring all the data together. Most of the top fields are self explanatory, I.e. Title, Description, Points. The main one is the 'Requirements' part.

Let's say we want to add an achievement for collecting a certain number of rings. Let's say 15 rings for simplicity. After filling out the fields at the top and selecting a suitable icon (in this example we used the gold trophy badge (00136), but you can upload a new one), we need to fill out Requirements. We have one requirement, **that the number of rings is at least 15**. Next click is **Add New Requirement**.

Clicking this button will add several default values to the Requirements list. These defaults just ensure that something relatively sensible is added to the list. For now, ignoring the field 'Special?'. When we clicked create, the default memory value will be whatever value you last left in the memory dialog.

Next we will change these values to the following:

* **Size**: `16-bit` - we're using 16-bit because the value *can* exceed 255 (which is 0xff in hex)
* **Memory**: `0xfe20`
* **Cmp**: `>=` - this is the comparison to make. We could have any comparison here, but it's sensible to have "greater than or equal to". This is important because if we get 10 rings then a super ring box to have 20, we would miss out having *exactly* 15 rings.
* **Type**: `Value` - we're comparing this memory value to a fixed value: 15
* **Size**: `Empty` - this is only relevant when comparing memory to memory
* **Mem/Val**: `15` - the number of rings required: the value we are comparing the memory to
* **Hit Count**: `0` - ignore this for now, its useful for when something needs to happen a certain number of times

With that set, we don't have any more conditions to add, so we return to the **Achievements Dialog**. To be safe, we should save our progress by hitting **Save Local**! This saves everything to file locally to ensure that we won't lose any progress.

- **Note**: An achievement should have more than one requirement to avoid it triggering at the wrong time (i.e. playing demo mode). In this example, we are using only one requirement to simplify the explanation. See more [Achievement Creation Tips here](Tips-and-Tricks#achivement-creation-tips).

## Testing the Achievement

We can now 'activate' this achievement locally by checking the box next to **Active** on the right-hand side in the Achievement Editor or by selecting the achievement in Achievement Sets and clicking **Activate Selected**. This will start monitoring these memory locations and will award the achievement once all the conditions are true. Now we can go ahead and test to see if this achievement works!

![overlay](/img/basics-overlay.png)

If we press `Esc` in-game, you will see the achievement show up as a demonstration of what it would look like in the in-game overlay!

![unlock](/img/basics-unlock.png)


Although the achievement worked fine in our tests, an achievement with logic like that is not ready to be officially released. First of all, it has only one condition: "collected rings >= 15". The problem is that the memory address used to record the number of collected rings is also used when the game runs in "demo mode" (AI playing the game after you wait a while on the title screen). So, if Sonic collects 15 rings in demo mode this achievement will trigger, which is unwanted.

Check the tips in the next section below to know how to improve the logic of your achievement and then make it acceptable to be officially released.


## Important Tips

Here are some tips you have to keep in mind when creating your achievements:

- **~~Never~~ Avoid making achievements with only one condition as much as you can**. Otherwise it will most likely pop at the wrong time. This is the **most common error by a developer**

- If the game has a **demo mode** (AI plays the game after you wait a while on the title screen), make sure to [find the address for it](Tips-and-Tricks#finding-the-address-for-demo-mode) and add a condition so your achievements don't trigger in demo mode. You'll also need to know how to use [PauseIf](Achievement-Logic-Features#pauseif) and [ResetIf](Achievement-Logic-Features#resetif).

- **[PauseIf](Achievement-Logic-Features#pauseif) cheat codes**: If the game has a cheat code to increase lives, select stages, etc., make sure to find the addresses for it and add some kind of protection in your achievements. OK, maybe it's not a very basic topic, but you have to keep it in mind when creating an official achievement set.

- **Avoid creating achievements for just entering a stage.** As it can be earned by a password or a stage select cheat code. It is preferred to make achievements for finishing stages, [like in this template here](Achievement-Templates#finish-level-n). Also, **do not create achievements for just starting a game or "starting a game with character X"**.

- If you want to create an achievement for getting a unique item in the game, add some conditions to make sure the player obtained the item where it is supposed to be obtained, [like in this template here](Achievement-Templates#collect-an-item-in-a-specific-level). Otherwise the achievement can be earned by using password or loading a saved game.

- **Avoid making too many achievements about simple things that require minimal effort**. Examples of what **NOT** to do: get one coin or one mushroom on Super Mario Bros.

- Be aware of the [unwelcome achievement's design concepts](Developers-Code-of-Conduct#unwelcome-concepts).

- **Be creative with your achievements**. Those covering unique features and details of the game are the most welcome. The players love when that little detail of a game they love is supported on an achievement. Reading a walkthrough on [GameFAQs](https://gamefaqs.gamespot.com/) can give some inspiration too.

- It can take a while to understand how the memory works in a game, so try spending as much time with it as you can, especially if it's your first attempt at developing achievements. 

You can find more in the [Tips and Tricks page](Tips-and-Tricks).


## Next Steps

Now that you know how to use the Memory Inspector, and the Achievement Editor. It's time to learn new techniques and practice:

- In order to refine your achievement logic, you can see what features you have in the [Achievement Logic Features](Achievement-Logic-Features) page.

- Another way to learn is by looking at existing achievements that other devs made with an extra explanation in the [Real Examples](Real-Examples) page.

- You can also see some generic examples in the [Achievement Templates](Achievement-Templates) page.

- Once you have learned the basic techniques, you can continue your quest to become an achievement developer by following the steps explained here: [How to Become an Achievement Developer](How-to-Become-an-Achievement-Developer)


Have fun!