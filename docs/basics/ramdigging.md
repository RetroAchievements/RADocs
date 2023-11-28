## Basics
  - RAM digging
    - Utilizing Game Genie, Game Shark, Codebreaker, Action Replay, etc. codes

## Memory Digging Tips

See also: [Memory Inspector Overview](Memory-Inspector-Overview).

- Start with 8-bit view in the Memory Viewer. Looking at larger chunks of memory will complicate things, but it will make a seasoned developer's job easier. If you're just starting out and unaware of terms like **endianess** and **bit ordering** (or when the eyes are tired), its best to make your observations in 8-bit view. Its just easier!

- **Uncheck "Show Decimal Values"** in the Achievement Editor so you can enter the hex values you see in the Memory Viewer. Its better than using a programmers calculator!

- If you find an address, also search the same region surrounding it and you could find many more useful addresses.

- You can input values in the memory viewer to see if it affects the game.

- Even if something is visibly decreasing in-game, like health, memory can behave differently. It's possible for it to be increasing, so since it's uncommon for you to know for sure, prefer the `!=` and `=` filters.

- If you absolutely cannot reduce the results of a filter, you can try guessing some values or at least how the value is acting (`>` or `<`). For example, no health is usually `0`, Stage 1 is usually value `0`, Stage 2 is usually value `1` depending on the type of game.

- **16/32 bit view**: remember that when working with 16 or 32 bit address the address to the right comes first. Example: if in 8bit it looks like `AB CD WX YZ`, in 16 bit it becomes `CDAB YZWX`. This is called "[big endian byte ordering](https://en.wikipedia.org/wiki/Endianness#Big-endian)". You can safely ignore the geek-speak by just remembering things are stored **backwards** in 16 bit view and above.

- **Bit fields**: Use single bits for things that only change a single bit. In the Memory Inspector, when an address is selected, there will be `Bits: 7 6 5 4 3 2 1 0` above the addresses. And below those numbers will be either `0` or `1`, like `0 0 1 0 0 0 1 1` in the image below. If `bit5` has `1` under it, then `bit5=1` for that address. Single bit usage is very common for game items/events/unlocks/etc. This may be confusing, but it's very important to understand. Some games with limited memory space use bit fields a lot! Its an important technique to learn.

![memsizes](https://user-images.githubusercontent.com/32680403/45276439-8cbf6580-b47f-11e8-803c-7e7e391a9e55.png)
