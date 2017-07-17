# hammer是什么
  hammer.js是一款开源的移动端脚本框架，
  如：点击、滑动、拖动、多点触控等事件。
  不需要依赖任何其他的框架，并且整个框架非常小

# 用法(引入hammerjs)
  1、pan事件：在指定的dom区域内，一个手指放下并移动事件，即触屏中的拖动事件。
  如：左拖动、右拖动等，如手要上使用QQ时向右滑动出现功能菜单的效果。
  该事件还可以分别对以下事件进行监听并处理：

  panstart：  拖动开始
  panmove：   拖动过程
  panend：    拖动结束
  pancancel： 拖动取消
  panleft：   向左拖动
  panright：  向右拖动
  panup：     向上拖动
  pandown：   向下拖动

  2、pinch事件：在指定的dom区域内，两个手指（默认为两个手指，多指触控需要单独设置）或多个手指相对（越来越近）移动或相向（越来越远）移动时事件。
     该事件事以分别对以下事件进行监听并处理：

      pinchstart：多点触控开始
      pinchmove： 多点触控过程
      pinchend：  多点触控结束
      pinchcancel 多点触控取消
      pinchin：   多点触控时两手指距离越来越近
      pinchout：  多点触控时两手指距离越来越远

  3、press事件：在指定的dom区域内触屏版本的点击事件，这个事件相当于PC端的Click事件，
     不能包含任何的移动，最小按压时间为500毫秒，常用于我们在手机上用的“复制、粘贴”等功能。
      该事件分别对以下事件进行监听并处理：

      pressup：点击事件离开时触发

  4、rotate事件：在指定的dom区域内，当两个手指或更多手指成圆型旋转时触发（就像两个手指拧螺丝一样）。
     该事件分别对以下事件进行监听并处理：

     rotatestart： 旋转开始
     rotatemove：  旋转过程
     rotateend：   旋转结束
     rotatecancel：旋转取消

  5、swipe事件：在指定的dom区域内，一个手指快速的在触屏上滑动。即我们平时用到最多的滑动事件。

     swipeleft： 向左滑动
     swiperight：向右滑动
     swipeup：   向上滑动
     swipedown： 向下滑动

  6、tap事件：在指定的dom区域内，一个手指轻拍或点击时触发该事件(类似PC端的click)。
     该事件最大点击时间为250毫秒，如果超过250毫秒则按Press事件进行处理。
  ------------------------------------------------------------------------------------------
         //创建一个新的hammer对象并且在初始化时指定要处理的dom元素
         var hammertime = new Hammer(document.getElementById(""));
         //添加事件
         hammertime.on("tap", function (e) {
             console.log(e);
         });

  这六个事件是有区别的：
    在Pinch事件和Rotate事件中，并没有对Pinch和Rotate事件进行监听，使用前需要先做一步
    hammertime.add(new Hammer.Pinch());  hammertime.add(new Hammer.Rotate ());
    而其他四个事件没有用，直接添加了事件的监听程序


  # 对于tap点透的bug，先使用click
