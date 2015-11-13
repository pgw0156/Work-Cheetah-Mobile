# Work-Cheetah-Mobile
猎豹移动


## 1.水平居中：
###  行内元素：设置其父元素的text-align为center；
###  块级元素：left & right的margin设成auto；
  
## 2.垂直居中：
###  light-height方法:
    line-height: xxxpx;  
    vertical-align: middle;（图片）
###  优点：适用于所有浏览器，无足够空间时不会被截断
###  缺点： 只对文本和图片有效(块级元素无效) ，多行时，断词比较糟糕
  
###  table方法：
    #parent {display: table;}
    #child {
      display: table-cell;
      vertical-align: middle;
    }
###  优点：content 可以动态改变高度(不需在 CSS 中定义)。当 wrapper 里没有足够空间时， content 不会被截断
###  缺点：Internet Explorer(甚至 IE8 beta)中无效，许多嵌套标签
  
###  定位方法1：
    #parent {position: relative;}
    #child {
      position: absolute;
      top: 50%;
      left: 50%;
      height: 30%;
      width: 50%;
      margin: -15% 0 0 -25%;
    }
###  优点：适用于所有浏览器，不需要嵌套标签
###  缺点：没有足够空间时，content 会消失(类似div 在 body 内，当用户缩小浏览器窗口，滚动条不出现的情况)
  
###  定位方法2：
    #parent {position: relative;}
    #child {
      position: absolute;
      top: 0;
      bottom: 0;
      left: 0;
      right: 0;
      width: 50%;
      height: 30%;
      margin: auto;
    }
###  优点：简单，无需其他特殊标记，CSS代码量少，支持百分比%属性值和min-/max-属性，完美支持图片居中
###  缺点：低版本IE(IE8以上OK)中无效，必须声明高度，建议设置overflow:auto来防止内容越界溢出
    
###  元素float方法：
    #parent {height: 250px;}
    #floater {
      float: left;
      height: 50%;
      width: 100%;
      margin-bottom: -50px;
    }
    #child {
      clear: both;
      height: 100px;
    }
###  优点：适用于所有浏览器，没有足够空间时(例如：窗口缩小) content 不会被截断，滚动条出现
###  缺点： 需要额外的空元素
  
