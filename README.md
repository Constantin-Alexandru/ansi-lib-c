ANSI LIB
========

Ansi Lib is a multi-language library that allows the coloured printing of text inside terminals.
This repository contains the C implementation of the library.

## Enable the library on Windows

To allow the function to work on some Windows terminal, the following function needs to be called at the beginning of the program: `ANSI_LIB_WINDOWS_INIT()`.

## Available functions

Ansi Lib contains the following function:

**Color functions:**

- `COLOR(value)`: returns the escape code string for setting the color chosen. Accepts one of the predefined 8 color values. Each color has a predefined MACRO that calls the function with the corresponding value. (See [Predefined Colors](#predefined-colors))
- `COLOR256(value)`: returns the escape code string for setting the color of the text using the 256 color mode.
- `BKG_COLOR256(value)`: returns the escape code string for setting the color of the background using the 256 color mode.
- `COLORRGB(r, g, b)`: returns the escape code string for setting the color of the text using rgb values.
- `BKG_COLORRGB(r, g, b)`: returns the escape code string for setting the color of the background using rgb values.
- `SET_COLOR(color)`: sets the color of either text or background using any of the above colors.

**Effect functions:**

- `EFFECT`: returns the escape code string for setting the chosen effects. Accepts one of the predefined effect values. Each effect has a predefined MACRO that calls this function with the corresponding value. (See [Predefined Effects](#predefined-effects))
- `SET_EFFECT`: sets the effect using the above effect.
- `RESET`: resets all effects and colors.

**Movement functions:**

- `GOTOXY(x, y)`: moves the cursor to the corresponding column and row inside the terminal.
- `GoUpN(n)`: moves the cursor up n lines. The cursor will remain on the same column.
- `GoUpNLines(n)`: moves the cursor up n lines. The cursor will be moved to the first column of the line.
- `GoDownN(n)`: moves the cursor down n lines. The cursor will remain on the same column.
- `GoDownNLines(n)`: moves the cursor down n lines. The cursor will be moved to the first column of the line.
- `GoLeftN(n)`: moves the cursor left n columns. If n is bigger than the current column index, the cursor will stay at the first column.
- `GoRightN(n)`: moves the cursor right n columns.

**Erasing functions:**

- `CLEAR_SCREEN`: clears the entire screen.
- `CLEAR_SCREEN_BELOW`: clears the content below the current line.
- `CLEAR_SCREEN_ABOVE`: clears the content above the current line.
- `CLEAR_LINE`: clears the entire line.
- `CLEAR_LINE_RIGHT`: clears the content right of the current column.
- `CLEAR_LINE_LEFT`: clears the content left of the current column.

## Predefined Colors

- `BLACK`
- `RED`
- `GREEN`
- `YELLOW`
- `BLUE`
- `MAGENTA`
- `CYAN`
- `WHITE`

- `BKG_BLACK`
- `BKG_RED`
- `BKG_GREEN`
- `BKG_YELLOW`
- `BKG_BLUE`
- `BKG_MAGENTA`
- `BKG_CYAN`
- `BKG_WHITE`

## Predefined Effects

- `BOLD`
- `DIM`
- `ITALIC`
- `UNDERLINE`
- `BLINKING`
- `INVERSE`
- `HIDDEN`
- `STRIKETHROUGH`
- `DOUBLE_UNDERLINE`

- `BOLD_RESET`
- `DIM_RESET`
- `ITALIC_RESET`
- `UNDERLINE_RESET`
- `BLINKING_RESET`
- `INVERSE_RESET`
- `HIDDEN_RESET`
- `STRIKETHROUGH_RESET`
- `DOUBLE_UNDERLINE_RESET`
