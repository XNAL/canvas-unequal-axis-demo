## 前言

这段时间一直在迭代开发公司的小程序，其中需要用到小程序版本的echarts。做起来痛苦的要死。一是小程序版本的echarts很多功能并不是很全。二是，产品经理总是有不少奇思妙想，就是不按常理出牌。痛苦！

有时候坐标轴两个坐标之间的间距因为数据的原因不能等距来显示，产品经理又是强烈要求要实现这个需求，所以只能尝试各种方法来实现。

## 实现

这次主要用markLine来实现。

一般平时使用markLine都是用来做y轴的标线，那天晚上加班的时候突然灵光一现，想到是不是可以用多个markLine来实现x轴的不等距坐标。

尝试一下，确实是可行的！！！

具体实现其实挺简单，主要是有没有想到这点！

## 效果图

![echarts demo](https://github.com/XNAL/echarts-unequal-axis-demo/blob/master/screenshorts/echarts-unequal-axis-demo.png)

## 代码

- ##### 核心代码

```javascript
markLine : {
  silent: true,
  symbol: ['none', 'none'],
  lineStyle: {
    normal: {
      opacity: 0
    }
  },
  label: {
    show: true,
    position: 'start',
    fontSize: 10,
    color: '#8A8FAB',
    padding: 2,
  },
  data : [
      {
        xAxis: 1
      },
      {
        xAxis: 3
      },
      {
        xAxis: 8
      },
      {
        xAxis: 12
      }
  ]
}
```

