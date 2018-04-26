---
title: mongodb批量更新
date: 2018-01-23
type: post
---

momgodb批量更新操作

## version<2.2

```
db.users.update(
{userid: {$in: ['1','2','3']}},
{$inc: {mycounter: 1}},
false, true
);
```
## version>2.2

```
db.users.update(
{userid: {$in: ['1','2','3']}},
{$inc: {mycounter: 1}}, 
{{multi: true}}
);