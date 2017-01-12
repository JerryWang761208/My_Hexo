---
title: FB ROBOT
date: 2016-12-28 22:25:24
tags:
---
![](https://image-cc.s3.envato.com/files/182634816/Cover.png)
Today, I want to talk about FB ROBOT created by **node.js**
(All credit for [Larry Lu](https://github.com/Larry850806))

To memory the things is that I run the bot on my NAS server.
And I let it 
``` zsh
node server.js &
```
which is running app in the background mode.

What's embarrassing is that I couldn't shut down the bot.
And it kept sending message to my friends.(annoying...)
Yep, even I delete the original file.

Hopefully, I found the solution is stopping ps.
``` zsh 
pkill -f node
```

Keep going !
