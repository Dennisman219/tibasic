# The TI-BASIC Compiler

This is a fork of [the original project](https://github.com/miselin/tibasic) made initially to implement support for additional symbols.

The TI-BASIC Compiler is all about compiling TI-BASIC code on your computer
into an 8XP file ready for transferring to your TI-83/TI-83+/TI-84 calculator.

Being able to type your programs instead of try and use the calculator's keypad is much easier :).

## Usage

```bash
tibasic [options] filename
```
compiles a TI-BASIC source file to a 8XP file which can be transfered to and executed on the calculator.

### Options
`-d` to decompile (generate TI-BASIC file from 8XP file)\
`-o filename` to specify output file

## Building

You can build this project yourself using meson/ninja by executing

```bash
meson build
```
followed by
```bash
ninja -C build
```

## Important Note!

There are a few symbols that could not be directly transferred to the language and were replaced instead with tokens. Here are some examples of replaced symbols:

|TIBasic symbol|Supported token|e.g.|
|-|-|-|
|`&`|`and`||
|`\|`|`or`||
|`~`|`xor`||
|`θ`|`[theta]`||
|powers|`^`|Five squared : `5^2`|
|`e`|`[e]`||
|roots|`[root]^`|Square root of D : `[root]^2D`|
|`-` (negative)|`[neg]`|Negative X : `[neg]X`|
|`→` (store)|`->`||

All Picture variables (Pic0 - Pic9) and String variables (Str0 - Str9) are CAPITALIZED (i.e. STR0)

TODO specify all (replaced) symbols and corresponding tokens

-----------------------------------------

Happy programming!
