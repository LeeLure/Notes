
## 实现样式
![[Echarts/components/assets/dataZoom.png]]

## 代码
>[!done] 
>```js
dataZoom: {
    type: 'slider', //slider表示有滑动块的，inside表示内置的
    // type: 'inside', // 放大和缩小
    // orient: 'vertical',
    show: true,
    width: '95%',
    height: '20px',
    xAxisIndex: [0], //设置 dataZoom-inside 组件控制的 x轴,可以用数组表示多个轴
    start: 70,  //数据窗口范围的起始百分比,表示0
    end: 100,  //数据窗口范围的结束百分比,表示50%
    fillerColor: 'rgba(40, 107, 255, 1)', //选中范围的填充颜色
    backgroundColor: '#FFFFFF', //组件的背景颜色
    borderColor: 'rgba(241, 245, 255, 1)',
    borderRadius: '20px',
    bottom: "1%", //位置
    // left: 40,
    moveHandleIcon: '', //移动手柄中间的icon，支持路径字符串
    handleIcon: 'path://M512,512m-448,0a448,448,0,1,0,896,0a448,448,0,1,0,-896,0Z', //两侧缩放手柄的 icon 形状，支持路径字符串
    handleSize: '85%', //滑动条的 左右2个滑动条的大小
    showDetail: false,//即拖拽时候是否显示详细数值信息 默认true
    handleStyle: {
      borderWidth: 0,
      color: 'rgba(40, 107, 255, 1)'
    },
    dataBackground: {  //数据阴影的样式。
      lineStyle: { //阴影的线条样式
        color: '#FFFFFF'
      },
      areaStyle: { //阴影的填充样式
        color: '#FFFFFF'
      }
    },
    textStyle: { //dataZoom文本样式
      show: false,
      color: 'transparents'
    }
    // filterMode: 'none'
  }, 
> ```


## [DataZoomComponents docs]()
```embed
title: "Documentation - Apache ECharts"
image: "https://echarts.apache.org/zh/images/logo.png?_v_=20240226"
description: "Apache ECharts，一款基于JavaScript的数据可视化图表库，提供直观，生动，可交互，可个性化定制的数据可视化图表。"
url: "https://echarts.apache.org/zh/option.html#dataZoom"
favicon: ""
aspectRatio: "22.70606531881804"
```
