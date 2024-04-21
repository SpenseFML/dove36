## Config for using handwired keyboard with ZMK
I had to flash my keyboard quiet a lot of times until I got the config right.
I made this Repo public to help others with the hassle.
If you have any questions or need help with your config, you can join my [discord](https://discord.gg/6NYX3pecrV) server.

## About this Project
The dove36 is a keyboard I designed myself. I wanted a unibody mechanical keyboard that is a hybrid of the [skeletyl](https://github.com/Bastardkb/Skeletyl) and the [reviung41](https://github.com/gtips/reviung/tree/master/reviung41). I went away from the splitkeyboard idea to make it easier and less expensive to build (niceNano! controllers cost about 25€)
Something that was quite important to me was the pinky stagger. I seem to have small pinkies and I had to move my hand often times when i wanted to use them, what defeated the purpose of an "ergo mech board" for me.

This layout tries to emulate [Neo2](https://www.neo-layout.org), and is intended to be used with a German QWERTZ softwarelayout.
It has "üäöß" on the standard layer as it is optimized for a mix of German & English.
The special character layer and the navigation & number block layer are designed to keep the fingers near the home row.

I had to make some adjustmens to vanilla Neo2 to make it fit a 3x5 layout:
"y" and "ß" are on "," and "." with an Hold-tap. This means that tapping the key will output "y" while holding it for 200ms will output ",". 
I'll probably change "." and "," to the number block layer to be able to use my modifiers on both sides on the bottom row.
If you want to learn more about Hold-tapping, be sure to look at the [ZMK config](https://zmk.dev/docs/behaviors/hold-tap) for it. I use the ["Tap-Preferred"](https://zmk.dev/docs/behaviors/hold-tap#option-2-tap-preferred) Option in this config.

## Why ZMK?

I use a [NiceNano V2](https://nicekeyboards.com/nice-nano/) in my setup, because I like to use my devices wireless. NiceNanos cant use QMK, thats why I have to use ZMK, which is no problem at all, because ZMK fit my needs quite right


## Compiling on your Machine

I compiled the firmware for a long time on my computer using zephyr and west. I kinda grew tired of it and that's why I now use Github Actions. The config is in this repo, so you dont have to make any changes to it.


## The Layers


This config is subject to change for my personal usecase, but I will do my own changes on another branch.

This layout has some adaptations, due to the limited keys available: 
* [home row modifiers](https://precondition.github.io/home-row-mods#what-are-home-row-mods)
* 4 Layers
    -> 1. Movement and Numblock
    -> 2. Special Characters
    -> 3. Special Macros for hard to do movements and shortcuts
    -> 4. Bluetooth and Bootloader (ZMK)



I made some custom changes to make this layout more enjoyable for me.

## Neo2 Base Layer
```
Y hold is ","
ß hold is "."
U and D hold is LSHIFT
I and T hold is LGUI
A and R hold is LALT
E and N hold is LCTRL
        |----------------------------------|    |----------------------------------|
        |   X  |   V  |   L  |   C  |   W  |    |   K  |   H  |   G  |   F  |   Q  |
        +------+------+------+------+------|    |------+------+------+------+------|
        |   U  |   I  |   A  |   E  |   O  |    |   S  |   N  |   R  |   T  |   D  |
        |------+------+------+------+------|    |------+------+------+------+------|
        |   Ü  |   Ö  |   Ä  |   P  |   Z  |    |   B  |   M  |   Y  |   ß  |   J  |
        |------+------+------+------+------|    |------+------+------+------+------|
                      |  M3  |  M2  |  M1  |    |  SPC  |  M1 |  M4  |
                      |--------------------|    |--------------------|  
  ```

## M1 Movement and Numblock
```
        |----------------------------------|    |----------------------------------|
        |  ESC |  BKS |  UP  |  DEL |  TAB |    |   ,  |   7  |   8  |   9  |   *  |
        +------+------+------+------+------|    |------+------+------+------+------|
        | HOME | LEFT | DOWN | RGHT |  END |    |   .  |   4  |   5  |   6  |   -  |
        |------+------+------+------+------|    |------+------+------+------+------|
        | PGUP | PGDW |  TAB | ENTR | NONE |    |   0  |   1  |   2  |   3  |   +  |
        |------+------+------+------+------|    |------+------+------+------+------|
                      | TRNS | TRNS | TRNS |    | TRNS | TRNS | TRNS |
                      |--------------------|    |--------------------|  
```

## M2 Special Characters
```
        |----------------------------------|    |----------------------------------|
        |   €  |   _  |   [  |   ]  |   ^  |    |   !  |   <  |   >  |   =  |   &  |
        +------+------+------+------+------|    |------+------+------+------+------|
        |   \  |   /  |   {  |   }  |   *  |    |   ?  |   (  |   )  |   -  |   :  |
        |------+------+------+------+------|    |------+------+------+------+------|
        |   #  |   $  |   |  |   ~  |   @  |    |   +  |   %  |   "  |   '  |   ;  |
        |------+------+------+------+------|    |------+------+------+------+------|
                      | TRNS | TRNS | TRNS |    | TRNS | TRNS | TRNS |
                      |--------------------|    |--------------------|  
```

## M3 F-Keys and usefull Macros
```
    UP, DOWN, LEFT, RIGHT with SHIFT and CTRL to mark whole words
    Backspace and delete with shift to delete whole words
    SHIFT + CTRL + X for 1Pass Browser extension on Chrome
    LALT + # for comments in VSCode 
    "§" and "°" which didnt fit on Layer 2
    more to come
        |----------------------------------|    |----------------------------------|
        | NONE - BKSP |  UP  |  DEL | NONE |    | NONE |  F7  |  F8  |  F9  |  F12 |
        +------+------+------+------+------|    |------+------+------+------+------|
        | HOME | LEFT | DOWN | RGHT |  END |    | NONE |  F4  |  F5  |  F6  |  F11 |
        |------+------+------+------+------|    |------+------+------+------+------|
        |   §  |   °  |  CMT | 1PSS | NONE |    | NONE |  F1  |  F2  |  F3  | NONE |
        |------+------+------+------+------|    |------+------+------+------+------|
                      | TRNS | TRNS | TRNS |    | TRNS | TRNS | TRNS |
                      |--------------------|    |--------------------|  
```

## M4 Bluetooth Control 
```
    BOOTLOADER on lower left
    BT CLEAR where M1 would be
    Will put some usefull Macros on here in future...
        |----------------------------------|    |----------------------------------|
        |  CLR | NONE | NONE | NONE | BOOT |    | NONE | NONE | NONE | NONE | BOOT |
        +------+------+------+------+------|    |------+------+------+------+------|
        |  BT3 |  BT2 |  BT1 |  BT0 | NONE |    | NONE | NONE | NONE | NONE | NONE |
        |------+------+------+------+------|    |------+------+------+------+------|
        | NONE | NONE | NONE | NONE | NONE |    | NONE | NONE | NONE | NONE | NONE |
        |------+------+------+------+------|    |------+------+------+------+------|
                      | TRNS | TRNS | TRNS |    | TRNS | TRNS | TRNS |
                      |--------------------|    |--------------------|  
```
