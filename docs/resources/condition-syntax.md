### Memory sizes

Size          | Prefix | Example   |
:------------:|:------:|:---------:|
Bit0          | `0xM`  | `0xM01234`
Bit1          | `0xN`  | `0xN01234`
Bit2          | `0xO`  | `0xO01234`
Bit3          | `0xP`  | `0xP01234`
Bit4          | `0xQ`  | `0xQ01234`
Bit5          | `0xR`  | `0xR01234`
Bit6          | `0xS`  | `0xS01234`
Bit7          | `0xT`  | `0xT01234`
Lower4        | `0xL`  | `0xL01234`
Upper4        | `0xU`  | `0xU01234`
8bit          | `0xH`  | `0xH01234`
16bit         | `0x `  | `0x 01234`
24bit         | `0xW`  | `0xW01234`
32bit         | `0xX`  | `0xX01234`
16bit BE      | `0xI`  | `0xI01234`
24bit BE      | `0xJ`  | `0xJ01234`
32bit BE      | `0xG`  | `0xG01234`
BitCount      | `0xK`  | `0xK01234`
Float         | `fF`   | `fF01234`
MBF32         | `fM`   | `fM01234`

### Prefixes

Modifier | Prefix | Example |
:-------:|:------:|:-------:|
Delta  | `d` | `d0xH1234`
Prior  | `p` | `p0xH1234`
BCD    | `b` | `b0xH1234`
Invert | `~` | `~0xH1234`

### Logical Flags

Flag | Prefix | Example   |
:---:|:------:|:---------:|
Reset If      | `R:` | `R:0xH1234=1`
Reset Next If | `Z:` | `Z:0xH1234=1`
Pause If      | `P:` | `P:0xH1234=1`
And Next      | `N:` | `N:0xH1234=1`
Or Next       | `O:` | `O:0xH1234=1`
Add Source    | `A:` | `A:0xH1234=1`
Sub Source    | `B:` | `B:0xH1234=1`
AddHits       | `C:` | `C:0xH1234=1`
SubHits       | `D:` | `D:0xH1234=1`
AddAddress    | `I:` | `I:0xH1234=1`
Measured      | `M:` | `M:0xH1234=1`
Measured%     | `G:` | `G:0xH1234=1`
Measured If   | `Q:` | `Q:0xH1234=1`
Trigger       | `T:` | `T:0xH1234=1`
