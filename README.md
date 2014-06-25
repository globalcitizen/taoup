TAO (The Art) of Unix Programming (and related systemic epiphanies)
===================================================================

This is a ruby-powered, ANSI-enabled, fortune-like program to espouse wisdom at
opportune moments, such as when you log in.

To get it running, make sure you have `ruby` and `gem` installed, then run:
 `gem install ansi`

After that, it should work fine.

There are two modes other than standard invocation, `--machine` which drops any
ANSI colors from the output, and `--fortune` which converts the wisdom to an
assumed imitation of the fortune format. To make the resulting fortune format
file available to the classic `fortune` program (loses ANSI colors in output)
you can run `strfile` as follows:

```
taoup --fortune >taoup-fortunes
strfile taoup-fortunes taoup-fortunes.dat
fortune taoup-fortunes
```

To display `taoup` output at login, try something like this in your `.profile`:

```
/path/to/taoup |grep -v '^---' | while read line;do echo $RANDOM'|'$line;done |sort|cut -d"|" -f2- | head -n 1 | cowsay -f eyes -n |head -n 2 |tail -n 1
echo '' | cowsay -f eyes |tail -n 10 |sed 's/^/[0;32;40m/'
```

Note that you need to use the real source of `README.md` for the command here, 
since the final `sed` contains extended ANSI escape sequence characters that 
do not copy from Github-webland. The `while read line...done` stuff is an 
ugly hack for portable random `sort`, mostly for OSX users. If you don't yet 
have `cowsay`, stop reading right now and get it installed!

