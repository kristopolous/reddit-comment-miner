## Introduction

Sometimes I get a reply to a comment that makes me think "Is this person crazy? Who the heck is this?" 

Now I could just page through the comments reading them like a typical obsessive crazy person. But I'm a programmer! I am
computer-assisted crazy! 

## The Goods

This only slightly magical PHP7 script casts a spell of Internet Stalker Level 1 over a given reddit user.

To use, provide a nickname, such as, well ok, let's use mine.

    $ ./reddit-comment-miner kristopolous
    1 https://www.reddit.com/user/kristopolous/
    2 https://www.reddit.com/user/kristopolous/?count=25&after=t1_ddlmrtg
    ...
    $

Now what you'll have, in the `data/` directory, are morsels like these:

    kristopolous-10.html
    kristopolous-11.html
    ..
    kristopolous-comments
    kristopolous-distrib


* The html files are cleaned up versions of what reddit gave us.
* The comments file is ALL THE COMMENTS in one giant, searchable, plain text file.  You can do things like um, `grep -i "i work at"` or "i live" ... creepy creeepy!
* The distrib file is their subreddit distribution so you can harshly judge them via a quick glance.

Additionally the first field of every line of the comment file is the score of the comment.  You can say, I dunno, see how stupid someone is
by doing, you know, `cat kristopolous-comments | awk ' { print $1 } ' | sort -n | uniq -c`. 

And like that, razzamatazz and alakazam, you've been data-mined!

I mean um, hey, stop doing that. What's wrong with you. 

Gawwd, you creep.


