TAO (The Art) of Unix Programming (and related systemic epiphanies)
===================================================================

This is a ruby-powered, ANSI-enabled, `fortune`-like program to espouse wisdom at
opportune moments, such as when you log in.

It's mostly a personal collection, but contributions are welcome.

To get it running, make sure you have `ruby` and `gem` installed, then run:
 `gem install ansi`

After that, it should work fine, as long as you use a black terminal (who doesn't?).

![screenshot](https://raw.githubusercontent.com/globalcitizen/taoup/master/screenshot.png "Behold, wisdom!")


Getting wisdom at login
-----------------------

To display `taoup` output at login, use the `taoup-fortune` example script or try adding something similar in your `.profile`.

Special modes
-------------

There are four modes other than standard invocation:
 * `--help` or `--h` shows brief command line help on invocation syntax
 * `--whitetrash` converts the otherwise attractive color scheme to be legible on light or white terminals
 * `--machine` drops any ANSI colors from the output
 * `--fortune` converts the wisdom to an assumed imitation of the fortune format. To make the resulting fortune format file available to the classic `fortune` program (loses ANSI colors in output) you can run `strfile` as follows: ```
taoup --fortune >taoup-fortunes
strfile taoup-fortunes taoup-fortunes.dat
fortune taoup-fortunes
```

Praise for taoup
----------------

* "Taoup is in my zshrc startup, it’s consistently fun/intelligent/thoughtful. Thanks for the continued maintenance 👍, cheers." [@ronjouch](https://github.com/ronjouch)
* We are now the [top ranked fortune implementation](https://github.com/topics/fortune) on Github. Spread the word!
