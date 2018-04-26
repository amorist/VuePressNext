---
title: npm script -- 当npm start之后launch浏览器
date: 2018-01-23
post: true
---


```
// Windows
"start":"start http://localhost:8081 & node bin/www"

// Mac
"start":"open http://localhost:8081 && node bin/www"

// Linux
"start":"xdg-open http://localhost:8081 && node bin/www"
```