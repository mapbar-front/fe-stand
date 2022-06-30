## CSS公用样式

一、什么是stylelint
          帮助你在css中避免错误的工具

二、如何使用
添加以下npm包

```js
① stylelint

② stylelint-config-standard：一些常见的css书写规范

③ stylelint-config-prettier：关闭所有不必要的或者有可能与Prettier冲突的规则

④ stylelint-order：提供给css属性排序的功能

⑤ stylelint-config-rational-order：一套常见的css书写顺序

⑥ prettier: 格式化
```

`npm i stylelint stylelint-config-standard stylelint-config-prettier stylelint-order stylelint-config-rational-order prettier -S`


编辑器下载相关插件：`stylelint，prettier`



```js
module.exports = {
    root: true,
    plugins: ['stylelint-order'],
    extends: ['stylelint-config-standard', 'stylelint-config-rational-order', 'stylelint-config-prettier'],
    rules: { // 覆盖stylelint-config-standard的配置
         'order/properties-order': []    // 设置css属性书写顺序，和stylelint-config-rational-order会冲突
    }
}
```


添加`npm script使用stylelint` 

`package.json`添加
执行`npm run lint-css`



```js
"scripts": {
    "lint-css": "stylelint src/**/*.{css,less,scss,vue} --fix"
}
```


编辑器保存时，执行`stylelint，以vscode`为例：

```js
"editor.codeActionsOnSave": {
    "source.fixAll.stylelint": true
},
```


`git hooks pre-commi`t阶段校验style
```js
"lint-staged": {
    "src/**/*.{css,less,scss,vue}": [
      "stylelint --fix"
    ]
  },
  ```