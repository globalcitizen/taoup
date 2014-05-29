TAO (The Art) of Unix Programming
=================================

This is a ruby-powered, ANSI-enabled, fortune-like program to espouse wisdom at
opportune moments, such as when you log in.

To get it running, make sure you have `ruby` and `gem` installed, then run:
 `gem install ansi`

After that, it should work fine.

To have it display on login, you could try something like this:

```
/path/to/taoup |grep -v '^---' | while read line;do echo $RANDOM'|'$line;done |sort|cut -d"|" -f2- | head -n 1 | cowsay -f eyes -n |head -n 2 |tail -n 1
echo '' | cowsay -f eyes |tail -n 10 |sed 's/^/[0;32;40m/'
```

That `while read line...done` stuff is an ugly hack for portable random `sort`.
(If you don't yet have `cowsay`, stop reading right now and get it installed!)
