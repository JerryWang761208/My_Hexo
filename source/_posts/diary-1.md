---
title: diary_1
date: 2016-12-20 23:15:14
tags:
---

![logo](https://scontent.ftpe4-1.fna.fbcdn.net/v/t1.0-9/10403244_10152499810492276_4569228001943214400_n.jpg?oh=deedfc478157ee8ca4d498eca5e874a4&oe=58E82D13)

![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

I would love to write a diary in English everyday.
By using hexo as my blog generator is so funny and exciting.

When I push my article to Github, I need to do 

``` bash
$ hexo g && hexo d
```

### And I am very lazy, I put script in **package.json** which is the following

``` bash
"scripts":{
    "deploy": "hexo g && hexo d"
  }
``` 

### And now I just need to type in one line:


``` bash
$ npm run deploy
```



