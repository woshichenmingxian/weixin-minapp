# 小程序开发小结

**针对业务需求，针对性小程序开发，总结以下：**

#### 1.框架

可以开发小程序的框架有很几类：**uni-app** 、**Taro**、**mpvue**、**小程序框架**。uni-app与Taro开发编码风格风别属于vue和react编码风格，但是最终通过编译成为小程序原生项目文件，也就是**小程序框架**

##### [uni-app](https://uniapp.dcloud.io)（ctrl+鼠标左键）

uni-app是一个使用 [Vue.js](https://vuejs.org/) 开发所有前端应用的框架，开发者编写一套代码，可发布到**iOS、Android、H5、以及各种小程序（微信/支付宝/百度/头条/QQ/钉钉）**等多个平台,不跨端，`uni-app`也是更好的小程序开发框架（[详见](https://ask.dcloud.net.cn/article/35947)）、更好的App跨平台框架、更方便的H5开发框架。不管领导安排什么样的项目，你都可以快速交付，不需要转换开发思维、不需要更改开发习惯。

![img](https://img.cdn.aliyun.dcloud.net.cn/uni-app/doc/uni-app-frame-0310.png)



##### [Taro](https://taro-docs.jd.com/taro/docs/README.html)（ctrl+鼠标左键）

**Taro** 是一套遵循 [React](https://reactjs.org/) 语法规范的 **多端开发** 解决方案,只书写一套代码，再通过 **Taro** 的编译工具，将源代码分别编译出可以在不同端（微信/百度/支付宝/字节跳动/QQ/京东小程序、快应用、H5、React-Native 等）运行的代码，遵循 [React](https://reactjs.org/) 语法规范，它采用与 React 一致的组件化思想，组件生命周期与 React 保持一致，同时支持使用 [JSX 语法](https://taro-docs.jd.com/taro/docs/jsx.html)，让代码具有更丰富的表现力，使用 **Taro** 进行开发可以获得和 React 一致的开发体验，语法如下：

```JavaScript
mport Taro, { Component } from "@tarojs/taro";
import { View, Button } from "@tarojs/components";

export default class Index extends Component {
  constructor() {
    super(...arguments);
    this.state = {
      title: "首页",
      list: [1, 2, 3]
    };
  }

  componentWillMount() {}

  componentDidMount() {}

  componentWillUpdate(nextProps, nextState) {}

  componentDidUpdate(prevProps, prevState) {}

  shouldComponentUpdate(nextProps, nextState) {
    return true;
  }

  add = e => {
    // dosth
  };

  render() {
    return (
      <View className="index">
        <View className="title">{this.state.title}</View>
        <View className="content">
          {this.state.list.map(item => {
            return <View className="item">{item}</View>;
          })}
          <Button className="add" onClick={this.add}>
            添加
          </Button>
        </View>
      </View>
    );
  }
}
```

Taro 方案的初心就是为了打造一个多端开发的解决方案。目前 Taro 代码可以支持转换到 **微信/百度/支付宝/字节跳动/QQ/京东小程序** 、**快应用**、 **H5 端** 以及 **移动端（React Native）**。



##### [小程序框架]([https://developers.weixin.qq.com/miniprogram/dev/framework/quickstart/#%E5%B0%8F%E7%A8%8B%E5%BA%8F%E7%AE%80%E4%BB%8B](https://developers.weixin.qq.com/miniprogram/dev/framework/quickstart/#小程序简介))（ctrl+鼠标左键）

小程序官方推出开发小程序框架，小程序包含一个描述整体程序的 `app` 和多个描述各自页面的 `page`。一个小程序主体部分由三个文件组成，必须放在项目的根目录

| 文件     | 必需     | 作用               |
| -------- | -------- | ------------------ |
| app.js   | 必须文件 | 写小程序逻辑       |
| app.json | 必须文件 | 小程序公共配置文件 |
| app.wxss |          | 小程序公共样式     |

一个小程序页面由四个文件组成，分别是：

| 文件类型 | 必需 | 作用       |
| -------- | ---- | ---------- |
| js       | 是   | 页面逻辑   |
| wxml     | 是   | 页面结构   |
| json     | 否   | 页面配置   |
| wxss     | 否   | 页面样式表 |

**注意：为了方便开发者减少配置项，描述页面的四个文件必须具有相同的路径与文件名。**

##### [**mpvue（ctrl+鼠标左键）**](http://mpvue.com/)

`mpvue` （[github 地址请参见](https://github.com/Meituan-Dianping/mpvue)）是一个使用 [Vue.js](https://vuejs.org/) 开发小程序的前端框架。框架基于 `Vue.js` 核心，`mpvue` 修改了 `Vue.js` 的 [runtime](http://mpvue.com/mpvue) 和 [compiler](http://mpvue.com/mpvue-template-compiler) 实现，使其可以运行在小程序环境中，从而为小程序开发引入了整套 `Vue.js` 开发体验

使用 `mpvue` 开发小程序，你将在小程序技术体系的基础上获取到这样一些能力：

- 彻底的组件化开发能力：提高代码复用性
- 完整的 `Vue.js` 开发体验
- 方便的 `Vuex` 数据管理方案：方便构建复杂应用
- 快捷的 `webpack` 构建机制：自定义构建策略、开发阶段 hotReload
- 支持使用 npm 外部依赖
- 使用 `Vue.js` 命令行工具 vue-cli 快速初始化项目
- H5 代码转换编译成小程序目标代码的能力

其它特性正在等着你去探索，[详细文档](http://mpvue.com/mpvue)。



#### 2.小程序功能性开发方案

##### 2.1.接口-请求域名配置

注册并登录微信公众平台-小程序==>开发==>开发设置中：

服务器域名：

```
request合法域名：配置接口请求域名地址
uploadFile合法域名：文件上传请求域名地址
downloadFile合法域名：文件下载请求域名地址
```



##### 2.2.上传

###### 2.2.1.文件上传

微信平台限制，上传只能读取微信聊天历史记录中选择文件

```javascript
/**
   *微信上传文件功能
   *  
   */
  wechatUpload(){
    wx.chooseMessageFile({
      count:1,
      type:'file',
      success:(res)=>{
        wx.uploadFile({
          url: urls.aly, //仅为示例，非真实的接口地址
          filePath: res.tempFiles[0].path,// res.tempFilePaths[0]
          name: 'file',
          formData: {
            OSSAccessKeyId: this.state.alyPolicy.accessid,
            key: this.state.alyPolicy.dir + "${filename}",
            policy: this.state.alyPolicy.policy,
            success_action_status: "200",
            callback: this.state.alyPolicy.callback,
            signature: this.state.alyPolicy.signature,
            filename:'test.jpg'
            // file: res.tempFiles[0],
          },
          success(res) {
            const data = res.data
            //do something
          }
        })

      }
    })
    // this.uploadALY()
  }
```



###### 2.2.2.图片上传

可以读取相册或者使用相机功能

```javascript
/**
   *微信上传照片功能
   *  
   */
  wechatUploadPht() {
    Taro.chooseImage({
      success:(res)=>{
        this.uploadALY(res)
      }
    })
    // this.uploadALY()
  }
```



##### 2.3.下载

操作系统限制,ios与安卓下载操作也有区别，小程序下载相对应的处理，具体如下：

```javascript
/**
   * 用后台地址请求aly服务地址
   * */ 
  alyUrl(filePath){
    serverAPI('post', urls.getOSSURL, { filePath }, ({ data }) => {
      Taro.getSystemInfo({
        success:(res)=>{
          // 存储设备信息
          this.setState({
            systemInfo: res
          },()=>{
             //判断平台
            // ios打开pdf 
            if (this.state.systemInfo.platform ==='ios'){
                this.iosPDF(data.data)
            }
            // 安卓打开pdf
            else{
            
                this.android(data.data)
            } 
          });
        }
      })
     })
   }
```

###### 2.3.1.ios下载

由于平台限制，只能打开临时文件地址

```javascript
 /**
   * ios页面（也可以web-view嵌套pdf）
   * 
   * */  
  iosPDF(url){
    Taro.downloadFile({
      url,
      success: function (res) {
        var Path = res.tempFilePath   //返回的文件临时地址，用于后面打开本地预览所用
        Taro.openDocument({
          filePath: Path,
          success: function (res) {
            console.log('打开成功');
          }
        })
      },
      fail: function (res) {
        console.log(res);
      }
    })
  }
```

###### 2.3.2Android下载

安卓可以下载到本地，可以设置保存路径，文件进行预览

```javascript
/**
   * 安卓需要下载系统打开
   * 
   * */ 
  android(url){
    /* 使用时间戳为下载后的文件的名字 */
    let fileName = new Date().valueOf();
    Taro.downloadFile({
      url,
      /* filePath指定文件下载后存储的路径，Taro.env.USER_DATA_PATH */
      filePath: wx.env.USER_DATA_PATH + '/' + fileName + '.pdf', 
      success: function (res) {
        const tempFilePaths = res.filePath
        // 保存到本地
        Taro.saveFile({
          tempFilePath: tempFilePaths,
          success(res) {
            const savedFilePath = res.savedFilePath
            Taro.openDocument({
              filePath: savedFilePath,
              success: function (res) {
                console.log(res)
                console.log('打开成功');
              }
            })

          }

        })
      },
      fail: function (res) {
        console.log(res);
        Taro.showToast({ title: '下载失败', icon: "loading", duration: 1000 }) 
      }
    })
  }
```



##### 2.4.web-view

webview一般用于跳转**H5页面**，不建议用于打开文件/文档,

如果需要预览PDF文件/文档可以采用**wx.openDocument()**  



##### 2.5.可视化开发

小程序可视化方案本人已知有一下几种：

###### [ec-canvas（echarts官方提供）](https://github.com/ecomfe/echarts-for-weixin)（ctrl+鼠标左键）

为了兼容小程序 Canvas，我们提供了一个小程序的组件，用这种方式可以方便地使用 ECharts。

首先，[下载本项目](https://github.com/ecomfe/echarts-for-weixin)（ctrl+鼠标左键）。

其中，`ec-canvas` 是我们提供的组件，其他文件是如何使用该组件的示例。

`ec-canvas` 目录下有一个 `echarts.js`，默认我们会在每次 `echarts-for-weixin` 项目发版的时候替换成最新版的 ECharts。如有必要，可以自行从 ECharts 项目中下载[最新发布版](https://github.com/ecomfe/echarts/releases)，或者从[官网自定义构建](http://echarts.baidu.com/builder.html)以减小文件大小。其他详情操作，请参考`ec-canvas`github。

本人就taro框架开发可视化，使用`ec-canvas`使用进行了多一层次的修改，原来的组件使用使用起来有点复杂，维护起来有些不便，具体如下：

```javascript
把ec-canvas文件夹(github上的文件夹)，从官网下载，并且放入你开发的项目中
在与ec-canvas文件夹平级，创建index.js,其中代码如下：

import Taro, { Component } from "@tarojs/taro";
import * as echarts from "./ec-canvas/echarts";
/**
 * echarts图标模板！！！！这个需要注意echarts有些图表配置项需要echarts再提供api，比如渐变...，所以需要再把echarts传入
 * @param {Object} chart:echats option模板
 **/
function setChartData(chart,data) {
    let cla=Object.prototype.toString.call(data);
    // if(){}
    // console.log(chart)
    cla==='[object Function]'?chart.setOption(data(echarts)):chart.setOption(data)
}

export default class Chart extends Component {
  config = {
    usingComponents: {
      "ec-canvas": "./ec-canvas/ec-canvas"
    }
  };

  constructor(props) {
    super(props);
  }

  state = {
    ec: {
      lazyLoad: true
    }
  };

  componentWillUnmount(){
    // console.log(this.Chart.chart)
    // this.Chart.chart._api.off();
    // this.Chart.chart._api.isDisposed();
  }

  refresh(data) {
    setTimeout(()=>{
      this.Chart.init((canvas, width, height) => {
        const chart = echarts.init(canvas, null, {
          width: width,
          height: height
        });
        setChartData(chart, data);
        // chart.dispose();
        return chart;
      });
    },50)
  }

  refChart = node => (this.Chart = node);

  render() {
    return (
      <ec-canvas
        ref={this.refChart}
        canvas-id="mychart-area"
        ec={this.state.ec}
      />
    );
  }
}

```

组件使用：

```javascript
import Taro, { Component } from '@tarojs/taro'
import { View, Picker, Text} from '@tarojs/components'
import Echarts from '@/components/echarts';//这个存放着ec-canvas文件夹和index.js
import Title from '@/components/title/manageTitle'
import ChinaJson from '@/components/echarts/mapJson/china';
import initData from '@/libs/initData';
import {ios,numberFormat,serverAPI} from '@/libs/util'
import Url from '@/libs/urls';
import '../index.scss';
export default class ClientImport extends Component {
    config={
        navigationBarTitleText: '折线图',
    }
    constructor(props){
        super(props)
        this.state = {
            platform:ios(),//平台判断
            colorArr:['21,157,252','247,86,76','0,195,143','255,162,0','47,69,84'],//颜色系列
            legend:[
                {
                    data:'业务量',
                    style:{
                        color:'rgb(97, 165, 232)',
                    }
                    
                },
                {
                    data:'服务费',
                    style:{
                        color:'rgb(225, 103, 87)',
                    },
                }
            ]

        }
 
    }
    componentDidMount(){
        this.getAllScale();//地图
        this.getTopFive(1);//五大客户
    }

    // 业务量--地图
    getAllScale(){
        serverAPI('post',Url.getAllScale,{},({data})=>{
            this.mapChart(data.data)
        })
    }
    // 五大客户
    getTopFive(type){
        serverAPI('post',Url.getTopFive,{"summaryType":type},({data})=>{
            let res=data.data;
            this.hBarChart(res)
        })
    }
    getTenthClient(){
        Taro.navigateTo({
            url: '/pages/manageChart/groupClient/tenthClient/tenthClientList'
        })
    }


    // 横向叠加图
    hBarChart(res){
        let {platform,colorArr}=this.state;

        // 设置默认值
        this.setState({
            receivableInitData:receivableInitdata,
            receivableUpdate:res.updateTime
        })
        let series=[];
        res.data.map((item,index)=>{
            series.push(
                {
                    name:index,
                    type: 'bar',
                    stack: '总量',
                    label: {
                        normal: {
                            show: false,
                        }
                    },
                    itemStyle:{
                        color:`rgba(${colorArr[index]},0.85)`
                    },
                    animation: false,
                    data:this.utilM(item)
                }
            )
        })
        const chartData = {
            xAxis:[{
                type: 'category',
                data: res.xAxis,
                name:'时间',
                nameLocation:'end',
                // minInterval: 1,
                axisLine:{
                    lineStyle:{
                        color:'#999'
                    }
                },
                axisTick :{
                    lineStyle:{
                        color:'#999'
                    }
                },
                axisLabel:{
                    fontSize:platform?12:13,
                    color:'#999'
                }
            }] ,
            yAxis:{
                type: 'value',
                name:'业务量(百万)',
                nameLocation:'end',
                // data: res.xAxis.reverse(),
                // nameGap:-1,
                axisLabel:{
                    fontSize:platform?12:13,
                    // color:'#999'
                },
                axisTick:{
                    show:false,
                    lineStyle:{
                        color:'#999'
                    }
                },
                axisLine:{
                    lineStyle:{
                        color:'#999'
                    }
                }
                
            },
            tooltip : {
                trigger: 'axis',
                animation: false,
                axisPointer: {
                    type: 'line',
                    axis:'x',
                    animation:false,
                    label: {
                        backgroundColor: '#6a7985'
                    },
                    lineStyle:{
                        type:'dashed'
                    }
                },
                backgroundColor:'transparent',
                formatter:(val)=>{
                    let arr=[];
                    val.map(item=>{
                        arr.push(item.data)
                    })
                    this.setState({
                        receivableInitData:arr
                    })
                    let value='';
                    return value
                }
            },
            grid: {
                left: '6%',
                right: '15%',
                bottom: '3%',
                top:'15%',
                containLabel: true
            },
            animation: false,
            series,
            
        }
        this.hBarChart_id.refresh(chartData);
    }
   
    // 地图画图 这种需要把echarts在传入与正常的图表配置chartData有区别，具体参照index.js
    mapChart(chinaData){
        const chartData=(echart)=>{
            echart.registerMap('china', ChinaJson);
            return{
                animation: false,
                tooltip: { 
                    trigger:'none',
                    animation: false,
                    position: function (point, params, dom, rect, size) {
                        return [point[0]-140, point[1]];
                    },
                    formatter:(val)=>{
                        let data=val.data;
                        return `${data.name}: \n业务量：${data.value}`
                    }
                },
                visualMap: {
                    show: true,
                    min: 0,
                    max: 10000000000,
                    itemWidth:10,
                    itemHeight:200,
                    // left: '0%',
                    left: 'left',
                    // text: ['100亿', '0'],
                    showLabel: true,
                    bottom: 0,
                    orient: 'horizontal',
                    calculable: true,
                    animation: false,
                    // text:'Low',
                    seriesIndex: [0],
                    formatter:(val)=>{
                        return (val/100000000).toFixed(0) + '亿'
                        // if(val>0){
                        //     return (val/100000000).toFixed(0) + '亿'
                        // }
                    },
                    inRange: {
                        color: ['rgb(255,255,255)', 'rgba(255,162,0,0.85)','rgba(247,86,76,0.85)'] // 蓝绿 ['21,157,252','247,86,76','0,195,143','255,162,0','47,69,84']
                        
                    }
                },
                
                series: [
                    {
                        type: 'map',
                        map: 'china',
                        geoIndex: 0,
                        aspectScale: .75, //长宽比
                        animation: false,
                        showLegendSymbol: false, // 存在legend时显示
                        label: {
                            normal: {
                                show: true,
                                fontSize:8
                            },
                            emphasis: {
                                show: false,
                                textStyle: {
                                    color: '#fff',
                                    
                                }
                            }
                        },
                        roam: false,
                        itemStyle: {
                            normal: {
                                // areaColor: '#031525',
                                borderColor: '#3B5077',
                            },
                            emphasis: {
                                areaColor: '#999'
                            }
                        },
                        animation: false,
                        data: chinaData
                    }
                ]
            }
            
        }
        this.mapChart_id.refresh(chartData);
    }


    render(){
        let {xxx}=this.state;
        return (
            <View className="client-import">
                <View className="import-status">
                
            
                    <View className="receivable-lines-charts">
                        <Echarts ref={(node)=>this.hBarChart_id=node}></Echarts>
                    </View>
                </View>
                
                <View className="import-status margin-top-20 ">
                    <Title>集团业务量地域分布</Title>
                    <View className="ollection-ratio-map-chart">
                       {
                           <Echarts ref={(node)=>this.mapChart_id=node}></Echarts>
                       } 
                    </View>
                </View>
            </View>
        )
    }
}
```



###### [mpvue-echarts](https://github.com/F-loat/mpvue-echarts)（ctrl+鼠标左键）

本项目是 ECharts 的 Mpvue 小程序版本。开发者可以通过熟悉的 ECharts 配置方式及 Vue 语法，快速开发图表，满足各种可视化需求。

```javascript
<template>
  <div class="echarts-wrap">
    <mpvue-echarts :echarts="echarts" :onInit="onInit" canvasId="demo-canvas" />
  </div>
</template>

<script>
import echarts from 'echarts'
import mpvueEcharts from 'mpvue-echarts'

let chart = null;

function initChart(canvas, width, height) {
  chart = echarts.init(canvas, null, {
    width: width,
    height: height
  });
  canvas.setChart(chart);

  var option = {}; // ECharts 配置项

  chart.setOption(option);

  return chart; // 返回 chart 后可以自动绑定触摸操作
}

export default {
  components: {
    mpvueEcharts
  },
  data () {
    return {
      echarts,
      onInit: initChart
    }
  }
}
</script>

<style scoped>
.echarts-wrap {
  width: 100%;
  height: 300px;
}
</style>
```



###### **[ wx-charts](https://github.com/xiaolin3303/wx-charts)**（ctrl+鼠标左键）

具体使用请点击，参考官方文档。



#### 3.开发注意点：

- [map](https://developers.weixin.qq.com/miniprogram/dev/component/map.html)、[video](https://developers.weixin.qq.com/miniprogram/dev/component/video.html)、[canvas](https://developers.weixin.qq.com/miniprogram/dev/component/canvas.html)、[camera](https://developers.weixin.qq.com/miniprogram/dev/component/camera.html)、[live-player](https://developers.weixin.qq.com/miniprogram/dev/component/live-player.html)、[live-pusher](https://developers.weixin.qq.com/miniprogram/dev/component/live-pusher.html),这些标签在实机中为顶层，不能重置层级，需要cover-view才能覆盖，注意点，cover-view标签加载必须在你需要覆盖的标签加载完成之后，否则无效。

- canvas在实机测试中有时候会丢失ontouch事件，导致可视化图表移动端交互效果有缺陷。

  

