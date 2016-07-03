PICOLOVE
--------

NEW: Forked by me, Max Hunt/mrh/m-r-hunt. Updated for Love 0.10.x, added new library mode (example coming soon), various bug fixes.

Originally written by Jez Kabanov, see https://github.com/ftsf/picolove

ABOUT
-----

Implementation of PICO8 API for LOVE

On github at: https://github.com/m-r-hunt/picolove

Requires Love 0.10.x

What it is:

 * An implementation of pico-8's api in love

What is Pico-8:

 * See http://www.lexaloffle.com/pico-8.php

What is Love:

 * See https://love2d.org/

Why:

 * For a fun challenge!
 * Allow standalone publishing of pico-8 games on other platforms
  * should work on mobile devices
 * Configurable controls
 * Extendable
 * No arbitrary cpu or memory limitations
 * No arbitrary code size limitations
 * Betting debugging tools available
 * Open source

What it isn't:

 * A replacement for Pico-8
 * A perfect replica
 * No dev tools, no image editor, map editor, sfx editor, music editor
 * No modifying or saving carts
 * Not memory compatible with pico-8

Not Yet Implemented:

 * Memory modification/reading

Differences:

 * Uses floating point numbers not fixed point
 * sqrt doesn't freeze
 * Uses luajit not lua 5.2

Extra features:

 * `ipairs()`, `pairs()` standard lua functions
 * `log(...)` function prints to console for debugging
 * `assert(expr,message)` if expr is not true then errors with message
 * `error(message)` bluescreens with an error message
 * `warning(message)` prints warning and stacktrace to console
 * `setfps(fps)` changes the consoles framerate
 * `_keyup`, `_keydown`, `_textinput` allow using direct keyboard input

USAGE
-----

Cart mode: download the source, add your cart file to the folder, change main.lua (or write your own) to read

    require "pico8lib"
    load_p8("mycart.p8")
    
Then run as you would a normal Love project.

Library mode: download the source, change main.lua to read

    require "pico8lib"
    
    function _init()
    end
    
    function _draw()
    end
    
    function _update() 
    end
    
    -- etc
    
You have access to all the Pico-8 api functions, and your _init, _update, and _draw functions will be run as you would expect on Pico-8. However, you are not sandboxed into the Pico-8 environment and could run Lua or Love api functions directly, or whatever shenanigans you would like to do that wouldn't be supported in Pico-8. With great power comes great responsiblity, i.e. you could break stuff.

TODO: Loading assets in library mode, including arbitrarily large spritesheets/maps/sfx/music files.
