First there was: [http://snipplr.com/view/15246/color-coded-svn-status](http://snipplr.com/view/15246/color-coded-svn-status)

Then there was: [http://snipplr.com/view/16540/color-coded-svn-status-v2](http://snipplr.com/view/16540/color-coded-svn-status-v2)

A few days ago, I found a handy script online that colorized the output of SVN status. It worked pretty well, but needed a little polish and a couple of tweaks to make it use more common Python idioms. As I continued to use it and fix bugs and inefficiencies, I ended up replacing nearly every line in the original, but it was still a great starting point.

Additional changes include ANSI word-wrapping, a configurable tab expansion feature (for better code alignment), the 'colorizedSubcommands' sequence so that only applicable commands get colorized, use of proper `subprocess` module calls so that piping through `less` will work (for example, try `svn-color diff | less -r` to see colorized diff output).

To use, stick it somewhere, make executable (`chmod 755`), and then add this to your .profile:

    alias svn=/usr/local/bin/svn-color.py

I hope you find my modifications useful. You can modify the colors used by looking up the ANSI color codes for your preferred color scheme and editing the 'statusColors' dictionary. Here's a useful reference for ANSI color values:

[http://www.ibm.com/developerworks/linux/library/l-tip-prompt/colortable.gif](http://www.ibm.com/developerworks/linux/library/l-tip-prompt/colortable.gif)

Requires Python 2.4 or greater.