## CSS公用样式

前端做任何项目，必须要用的css，其实很多css有很大的通用性，公用样式的目标，就是把这些通用性的东西，总结下来。

应用场景：前端任何项目中，都可以使用该common.css文件。

common.css 内容概览

<table class="relative-table wrapped confluenceTable"><colgroup><col style="width: 20.728%;" /><col style="width: 26.1881%;" /><col style="width: 24.9747%;" /><col style="width: 28.1092%;" /></colgroup><tbody><tr><th class="confluenceTh">分类</th><th class="confluenceTh">class名</th><th class="confluenceTh">属性</th><th class="confluenceTh">描述</th></tr><tr><td class="confluenceTd">1、初始化部分</td><td class="confluenceTd">#app、html、body、.wrapper</td><td class="confluenceTd"><p>width: 100%;</p><p>height: 100%;</p><p>margin: 0;</p><p>padding: 0;</p></td><td class="confluenceTd">单页面应用中，一般需要对这几个类做初始化，保证padding、margin重置、宽高为100%</td></tr><tr><td class="confluenceTd">2、flex部分</td><td class="confluenceTd">.flex-box、.flex-col、.flex1、.flex2、.center、.left-center、</td><td class="confluenceTd"><p>display: flex、align-items、justify-content等等。</p></td><td class="confluenceTd">flex布局，主要解决的是页面结构的问题，是竖直排布，还是水平排布，是等分，还是其他方式。</td></tr><tr><td class="confluenceTd">3、margin部分</td><td class="confluenceTd"><p>.margin</p><p>.margin-left-*</p><p>.margin-top-*</p><p>.margin-bottom-*</p></td><td class="confluenceTd"><p>margin、margin-left、margin-top、margin-bottom等等。</p><p>基本的距离设置为：5、10、20、30、50、100.</p></td><td class="confluenceTd">主要针对margin属性的间距，设置的几个具体的class。</td></tr><tr><td class="confluenceTd" colspan="1">4、padding部分</td><td class="confluenceTd" colspan="1"><p>.padding</p><p>.<span>padding</span>-left-*</p><p>.<span>padding</span>-top-*</p><p>.<span>padding</span>-bottom-*</p></td><td class="confluenceTd" colspan="1"><p><span>padding</span>、<span>padding</span>-left、<span>padding</span>-top、<span>padding</span>-bottom等等。</p><p>基本的距离设置为：5、10、20、30、50、100.</p></td><td class="confluenceTd" colspan="1"><span>主要针对<span>padding</span>属性的间距，设置的几个具体的class。</span></td></tr><tr><td class="confluenceTd" colspan="1">5、width宽度</td><td class="confluenceTd" colspan="1">.width*</td><td class="confluenceTd" colspan="1"><p>宽度设置：width</p><p><span>基本的宽度设置值为：100、200、250、300、400、500、600、700、800、900、1000、1280</span></p></td><td class="confluenceTd" colspan="1">Block元素宽度设置</td></tr><tr><td class="confluenceTd" colspan="1">6、其他</td><td class="confluenceTd" colspan="1"><p>.text-center</p><p>.border</p><p>.border-bottom</p><p>.one-line</p></td><td class="confluenceTd" colspan="1"><p>text-align: center</p><p>border: 1px solid #ccc</p><p>white-space: no-wrap</p></td><td class="confluenceTd" colspan="1">一些常用的类：文本居中、文本单行展示、border边框。</td></tr></tbody></table>

1、初始化部分
```js
#app,
html,
body,
.wrapper {
width: 100%;
height: 100%;
margin: 0;
padding: 0;
}
2、flex部分
.flex-box {
display: flex;
}

.flex-col {
flex-direction: column;
}

.flex1 {
flex: 1;
}

.flex2 {
flex: 2;
}

.center {
display: flex;
align-items: center;
justify-content: center;
}

.left-center {
display: flex;
align-items: center;
}
3、margin

.margin5 {
margin: 5px;
}

.margin10 {
margin: 10px;
}

.margin20 {
margin: 20px;
}

.margin30 {
margin: 30px;
}

.margin50 {
margin: 50px;
}

.margin100 {
margin: 100px;
}

.margin-left-5 {
margin-left: 5px;
}

.margin-left-10 {
margin-left: 10px;
}

.margin-left-20 {
margin-left: 20px;
}

.margin-left-30 {
margin-left: 30px;
}

.margin-left-50 {
margin-left: 50px;
}

.margin-left-100 {
margin-left: 100px;
}

.margin-top-5 {
margin-top: 5px;
}

.margin-top-p10 {
margin-top: 10px;
}

.margin-top-20 {
margin-top: 20px;
}

.margin-top-30 {
margin-top: 30px;
}

.margin-top-50 {
margin-top: 50px;
}

.margin-bottom-5 {
margin-bottom: 5px;
}

.margin-bottom-10 {
margin-bottom: 10px;
}

.margin-bottom-20 {
margin-bottom: 20px;
}

.margin-bottom-30 {
margin-bottom: 30px;
}

.margin-bottom-50 {
margin-bottom: 50px;
}

.margin-bottom-100 {
margin-bottom: 100px;
}
4、padding

.padding5 {
padding: 5px;
}

.padding10 {
padding: 10px;
}

.padding20 {
padding: 20px;
}

.padding30 {
padding: 30px;
}

.padding50 {
padding: 50px;
}

.padding100 {
padding: 100px;
}

.padding-left-5 {
padding-left: 5px;
}

.padding-left-10 {
padding-left: 10px;
}

.padding-left-20 {
padding-left: 20px;
}

.padding-left-30 {
padding-left: 30px;
}

.padding-left-50 {
padding-left: 50px;
}

.padding-left-100 {
padding-left: 100px;
}

.padding-top-5 {
padding-top: 5px;
}

.padding-top-10 {
padding-top: 10px;
}

.padding-top-20 {
padding-top: 20px;
}

.padding-top-30 {
padding-top: 30px;
}

.padding-top-50 {
padding-top: 50px;
}

.padding-top-100 {
padding-top: 100px;
}

.padding-bottom-5 {
padding-bottom: 5px;
}

.padding-bottom-10 {
padding-bottom: 10px;
}

.padding-bottom-20 {
padding-bottom: 20px;
}

.padding-bottom-30 {
padding-bottom: 30px;
}

.padding-bottom-50 {
padding-bottom: 50px;
}

.padding-bottom-100 {
padding-bottom: 100px;
}
5、width宽度
.width100 {
width: 100px;
}

.width200 {
width: 200px;
}

.width250 {
width: 250px;
}

.width300 {
width: 300px;
}

.width400 {
width: 400px;
}

.width500 {
width: 500px;
}

.width600 {
width: 600px;
}

.width700 {
width: 700px;
}

.width800 {
width: 800px;
}

.width900 {
width: 900px;
}

.width1000 {
width: 1000px;
}

.width1280 {
width: 1280px;
}
6、其他

.text-center {
text-align: center;
}

.border {
border: 1px solid #ccc;
}

.border-bottom {
border-bottom: 1px solid #ccc;
}

.one-line {
overflow: hidden;
white-space: nowrap;
text-overflow: ellipsis;
}
```