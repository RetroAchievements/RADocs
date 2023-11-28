## Things to Avoid and Why
  - **Avoid using only one condition as much as you can**. When using only one condition the achievement will most likely pop at the wrong time.  This is the **most common error by a developer**.
  - Redundant Resets and Pauses
  - **Avoid relying on text and graphics**: Most of the time, an achievement that requires triggering a special event can be tied to an event flag (usually a single bit or byte), or to an item received by the player. It is better practice to use these values than to check the ID of text being displayed in a text box, or, even worse, video RAM (memory tied to the actual graphics displaying on the screen) as they are often less stable. Especially between different versions of a single game, and they are more difficult to debug.

## Workflow Tips
  - Using Google Sheets and Notepad++
  - Editing local file