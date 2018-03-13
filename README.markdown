Neat Status Line
===

```
                           _   _            _   ____  _        _
                          | \ | | ___  __ _| |_/ ___|| |_ __ _| |_ _   _ ___
                          |  \| |/ _ \/ _` | __\___ \| __/ _` | __| | | / __|
                          | |\  |  __/ (_| | |_ ___) | || (_| | |_| |_| \__ \
                          |_| \_|\___|\__,_|\__|____/ \__\__,_|\__|\__,_|___/
```

Yet another status line plugin. The aim of Neat Status is to provide neat, and
simple UI with just basic information and no bells and whistles for those users
who consider things like Powerline to be overkill.

**Note:** this is not a drop-in replacement for Powerline but rather a much
simpler and streamlined plugin. The aim of the project is not to achieve one
to one feature compatibility but merely to implement a narrow subset of said
features for users who want something simple and easy. If you would like a
robust, feature-full Powerline replacement you should check out [Vim-Airline][va].

Screenshots
-----------

Here is how this status line will look in vim on Mac Terminal with the Monokai color scheme:

![Neat Statusline][ns]

Information provided from left to right:

1. Mode Indicator - changes color depending on the editor mode
2. Session - displays vim terminal name (eg. tmux, term)
3. File path for the file associated with current buffer
4. File type (eg. python, ruby, etc..)
5. File format (eg. unix, dos, etc..)
6. File encoding (eg. utf8, latin1, etc..)
7. Buffer number
8. Current line, total number of lines (purple box)
9. Percentage of file read
10. Relative & absolute column number (from 1st character / from start of line)
11. Modified / Unmodified indicator

Installation
---

Installing with Vundle:
  * Put this into your `.vimrc` under your Vundle section:
```
Bundle 'Cu7ious/vim-neatstatus'
```
  * Execute `:PluginInstall`

Configuration
---

You can configure the colors of the status line elements by defining the following global vars in your `.vimrc`:

* `g:NeatStatusLine_color_normal` - the color of the mode indicator when in normal mode
* `g:NeatStatusLine_color_insert` - the color of the mode indicator when in insert mode
* `g:NeatStatusLine_color_replace` - the color of the mode indicator when in replace mode
* `g:NeatStatusLine_color_position` - the color of the cursor position box (and session box)
* `g:NeatStatusLine_color_line` - the color of the line number in the cursor position box
* `g:NeatStatusLine_color_modified` - the color of the "modified" indicator on the right
* `g:NeatStatusLine_color_filetype` - the color of the filetype box

Make sure you define values both for graphical and terminal clients when you do this. Here is
a quick example that shows you hot to redefine the insert mode colors:

    let g:NeatStatusLine_color_insert = 'guifg=#ffffff guibg=#ff0000 gui=bold ctermfg=15 ctermbg=9 cterm=bold'

Note that these only affect the small boxes created by NeatStatus. Your status line will remain
the default color as per your color scheme. This works very well if you also happen to use the
Obvious-Mode plugin.

If you want to style your status line, you can do it in your `.vimrc` normally using the `hi StatusLine`
and `hi StatusLineNC` commands.

You can also change the separator character that divides the boxes by changing:

* `g:NeatStatusLine_separator`

By default the separator is set to the pipe `|` character. You can disable the separator by setting it to empty string.

[ns]: https://github.com/Cu7ious/vim-neatstatus/raw/master/Vim-neatstatus.png "Neat Statusline"
[va]: https://github.com/bling/vim-airline
