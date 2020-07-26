---
layout:     post
title:      Regular expression and generate random strings in javascript
subtitle:   
date:       2020-06-30
author:     Linz
header-img: img/Background/b2.jpg
catalog: true
tags:
    - JavaScript
---

## 1. Regular expression in javascript

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

## 2. Generate random string
Goal: 
1. Generate a fix length random string.
2. Generate a random length rangom string.
3. Provides a Letter pool.
```javascript 
function randomStringGenerate(flag, min, max){
  var str = "";
  var letterPool = ["a","b","c"];
  var stringLength = 0;
  if(flag){
    stringLength = Math.round(Math.random() * (max-min)) + min; // generate a number
  }
  //generate string
  for(var a = 0; a <stringLength ; a++ ){
      pos = Math.round(Math.random() * (arr.length-1)); // same logic, generate a number
      str += arr[pos]; // add position char to str
  }
}
```