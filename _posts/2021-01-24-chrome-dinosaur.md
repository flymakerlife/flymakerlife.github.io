---
layout: post
title: chrome小恐龙实用代码
date: 2021-1-24
categories: blog
tags: [小技巧]
description: 文章金句。
---
##首先，要知道如何修改：按F12，然后在"console"一栏添加代码，最后回车

**自动跳跃：**
```js
(function (){
  var __update = Runner.prototype.update;
  var JUMPMINTIME = 18;

  function jump() {
    var event =  new KeyboardEvent('keydown',{ code:'Space', keyCode:32, key: " " });
    document.dispatchEvent(event);
  }

  Runner.prototype.update = function (){
    var tRex = Runner.instance_.tRex;
    if(!tRex.jumping) {
      var obstacles =  Runner.instance_.horizon.obstacles;
      var index = 0;
      while(index < obstacles.length){
        var xDistance = obstacles[index].xPos - tRex.xPos;
        if(xDistance > 0){
          if (xDistance / Runner.instance_.currentSpeed < JUMPMINTIME) {
           jump();
          }
          break;
        } else {
          index ++;
        }
      }
    }
    __update.call(this)
  }

  jump();
})()
```

**取消跳跃：**

```js
Runner.instance_.tRex.setJumpVelocity(0)
```

**无敌:**
```js
var dino = Runner.prototype
dino.gameOver = () => {}
```

最后，祝大家玩的愉快

