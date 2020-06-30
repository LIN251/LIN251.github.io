---
layout:     post
title:      Regular expression in javascript
subtitle:   
date:       2020-06-30
author:     Linz
header-img: img/Background/b2.jpg
catalog: true
tags:
    - javascript
---

## Regular expression in javascript

***String example:***
var regularExpression = "(b)+bab(babab)+[a+b]-{ab}";

#### Parentheses ()
```javascript 
var regex1 = /\((.+?)\)/g;  
console.log(regularExpression.match(regex1)); 
```
#### Square brackets []
```javascript 
var regex2 = /\[(.+?)\]/g; 
console.log(regularExpression.match(regex2)); 
```

#### big parantheses {}
```javascript 
var regex3 = /\{(.+?)\}/g; 
console.log(regularExpression.match(regex3)); 
```

