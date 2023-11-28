# Logic Overview
There are several tools and options available to a developer. Knowing how to properly utilize them will improve the quality of your sets. These tools/options can be used in the Achievement Editor:

![achievement_editor](https://user-images.githubusercontent.com/45054151/128662028-74e64baf-46ff-4c9f-9837-3684bfb42ad8.png)

For more help regarding these, our [Discord server](https://discord.gg/dq2E4hE) is always open for assistance.

### Types
  - Mem
  - Value
  - Delta
    - `Mem > Delta` Comparisons
  - Prior
  - BCD
  - Float

### Flags
  - <a name="pauseif"></a>[`PauseIf` Flag](PauseIf-Flag)
    - <a name="pauseif-with-hit-counts"></a>[`PauseIf` with hit counts](PauseIf-Flag#pauseif-with-hit-counts)
    - Pause Locks

  - <a name="resetif"></a>[`ResetIf` Flag](ResetIf-Flag)
    - <a name="resetif-with-hit-counts"></a>[`ResetIf` with hit counts](ResetIf-Flag#resetif-with-hit-counts)

  - <a name="resetnextif"></a>[`ResetNextIf` Flag](ResetNextIf-Flag)

  - <a name="addsource"></a>[`AddSource` Flag](AddSource-Flag)

  - <a name="subsource"></a>[`SubSource` Flag](SubSource-Flag)
    - <a name="checking-for-a-negative-result"></a>[Checking for a negative result](SubSource-Flag#checking-for-a-negative-result)

  - <a name="addhits"></a>[`AddHits` Flag](AddHits-Flag)

  - <a name="subhits"></a>[`SubHits` Flag](SubHits-Flag)

  - <a name="addaddress"></a>[`AddAddress` Flag](AddAddress-Flag)

  - <a name="andnext"></a>[`AndNext` Flags](AndNext-Flag)
    - Multiconditional hits
    - Multiconditional resets/pauses

  - <a name="ornext"></a>[`OrNext` Flag](OrNext-Flag)

  - <a name="measured"></a>[`Measured` Flag](Measured-Flag)

  - <a name="measuredif"></a>[`MeasuredIf` Flag](MeasuredIf-Flag)

  - <a name="trigger"></a>[`Trigger` Flag](Trigger-Flag)

### Sizes
  - bitflags (bit0 - bit7)
  - 8-Bit
  - 16-Bit
  - 24-Bit
  - 32-Bit
  - Lower4 and Upper4
  - 16-Bit BE
  - 24-Bit BE
  - 32-Bit BE
  - BitCount
  - Float
  - MBF32

### Comparisons
  - `=`
  - `<`
  - `<=`
  - `>`
  - `>=`
  - `!=`
  - `*`
  - `/`
  - `&`

### Other Toolkit Features
  - Alt Groups
  - Vs. OrNext
  - Hit counts
    - Hit counts as a timer
    - Checkpoint hits
    - Multi-conditional hits
    - Pause Locks

## Logic Tips and Tricks
  - Using Delta Values and Hit Counts to Detect an Increment
  - Circumvent the Problem of a Counter Incrementing Twice in the Same Frame
    - `note: need to add something about how the toolkit still uses hex even if the value is in BCD`
  - Various types of chains
  - When to use Reset If or Pause If
  - When to use Delta or Prior
  - Using BitCount for collectables
  - Using Add Source with `Mem / Mem` comparisons
  - Creating a Timer with Reset If hits based on the speed of the game
  - Using `bit0` to include or exclude odd-numbered values

## Lesser-Known Features
  - Double-Clicking bitflags while in 8-bit view
  - Right-Clicking addresses in the editor to jump to them in the Memory Inspector (also works with offsets to jump to the current address)
  - Highlighting conditions and holding CTRL while clicking to change a field in multiple conditions at once

## Protections
  - Demo Protection
    - Finding and testing demo addresses
  - Save Protection
    - Delta and Prior
    - Using in-game timers
    - Using event flags
  - Password Protection
  - Cheat Protection
  - Multiplayer Protection
  - Other
    - Dipswitch
    - BIOS (PlayStation and Saturn)