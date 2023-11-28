  - [Address Watcher](#address-watcher)

### Address Watcher

Here's an easy trick using a dummy achievement to watch an address for any changes, which is something you'll quite often want to know.

![](https://user-images.githubusercontent.com/32706333/51081767-dbdb0880-16b4-11e9-9672-4b39721accd3.png)

**Conditions Explained**  

1. ``Value 1 = Value 0``; This is to prevent the achievement from ever being true, as the value 0 never equals 1.
2. ``Value 1 = Value 1``; For this trick to work the achievement needs hits to reset. When 1 = 1 hits will be added to this condition.
3. ``ResetIf Mem 0x10 != Delta 0x10``; This is the address you want to watch. Any time there is a change the achievement will reset.

- Last of all make sure that ``Pause on Reset`` and ``Active`` are both checked. Now you will get a pop-up and emulation will pause each time this address changes.
