## The Latest in Stalker Assistance Technology

Ever get a reply on reddit where you think "Dear Lord Almighty! This person crazy. Who is this?!" 

Now you *could* page through their comments and stalk them the old way or you could live it up with the brand new
`reddit-comment-miner`.

This magical PHP7 script casts a spell of Internet Stalker Level 1 over a given reddit user.

Watch as we provide a nickname and the script chugs away, slurping up all their comments:

    $ ./reddit-comment-miner kristopolous
    1 https://www.reddit.com/user/kristopolous/
    2 https://www.reddit.com/user/kristopolous/?count=25&after=t1_ddlmrtg
    ...
    $

Now we descend into the `data/` directory and see the tasty morsels left behind:

    kristopolous-10.html
    kristopolous-11.html
    ..
    kristopolous-comments
    kristopolous-distrib


These are truly delicious:

* The html files are cleaned up versions of what reddit gave us.
* The comments file are ALL THE COMMENTS in one giant, searchable, plain text file.  We can do <s>creepy</s> marvelous things like `grep -i "i work at"` or `"i live in"`.
* The distrib file is a subreddit distribution to conveniently judge someone at a quick glance.

### But Wait, There's More!

The first field of every line of the comment file is the score of that comment.  You can see how immensely unpopular the user is
with a few quick cuts of everyday shell tools: `cat kristopolous-comments | awk ' { print $1 } ' | sort -n | uniq -c`. 

Razzamatazz and alakazam, you've been data-mined!
