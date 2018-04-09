# Phoenix configuration

This is my personal [Phoenix](https://github.com/kasper/phoenix) configuration, written in TypeScript. I also created [typings](https://github.com/mafredri/phoenix-typings) for it, feel free to use them.

## Key bindings

The definition of `hyper` and `hyperShift` can be found in [src/config.ts](src/config.ts).

### Basic bindings

* `hyper + Left` (Left half of screen)
* `hyper + Right` (Right half of screen)
* `hyper + Up` (Top half of screen height, keeps current width)
* `hyper + Down` (Bottom half of screen height, keeps current width)
* `hyper + Return` (Toggle maximize, remembers unmaximized position)
* `hyper + Tab` (Jump to next screen whilst keeping relative size and placement)
* `hyper + Delete` (Minimize focused window)
* `hyperShift + Left` (Move window to left edge of screen)
* `hyperShift + Right` (Move window to right edge of screen)
* `hyperShift + Up` (Move window to top edge of screen)
* `hyperShift + Down` (Move window to bottom edge of screen)
* `hyperShift + Return` (Move window to center of screen)

Use combos of the key bindings to further place the windows:

* `hyper + Left` + `hyper + Down` (Bottom left corner of screen)
* `hyper + Enter` + `hyper + Up` (Top half of screen, full width)

I've optimized the key bindings for my common use-case, showing two windows on one screen and moving windows between screens.

### Misc bindings

* `hyper + c` (Start coffee timer, defaults to 8 minutes)
* `hyper + +` (Increase monitor brightness using external script)
* `hyper + -` (Decrease monitor brightness using external script)
* `hyper + Space` (Experimental: search for windows, tab to cycle, enter to switch, esc to cancel)
* `§` (Show or hide the last used Terminal window)
* `Cmd + §` (Cycle between Terminal windows)
* `Cmd + Escape` (Cycle between windows of current application, including minimized and windows on a different screen)
* `Cmd + Shift + Escape` (Same as `Cmd + Escape` except in reverse order)

## Misc features

* Switch between Karabiner-Elements profiles when screens change
* Refresh screen brightness info when screens change (using `ddcctl`)
* Support disabling / re-enabling all current keybindings via [src/key.ts](src/key.ts) (used by scanner)

## Building

```
git clone https://github.com/mafredri/phoenix-config.git
cd phoenix-config
yarn && yarn run typings
yarn run build
```

The TypeScript compiler and Webpack will produce `out/phoenix.js` that can be used as Phoenix configuration. 

For development, `yarn start` will run Webpack in watch-mode.
