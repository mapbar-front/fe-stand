## Eslint规范

一、为什么要用`eslint`？   
          `JavaScript`是一个动态的弱类型语言，代码编写时经常会出错，而因为其没有编译程序，则需要在执行的过程中不断的调试。`eslint`的作用就是在开发过程中提前发现问题所在，规范团队的代码风格并保持一致。

二、安装
在 `Vscode `中安装 eslint 扩展
用 `npm `安装 `eslint` 包

`npm install eslint --save-dev`


三、使用
安装相关插件  `eslint-config-airbnb` 、`eslint-plugin-import` 、`eslint-plugin-jsx-a11y`、`eslint-plugin-react ` (airbnb插件只能对react使用)

> npm i -D eslint-config-airbnb eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react  


安装相关插件  `eslint-plugin-vue`

`npm i -g eslint-plugin-vue`
 

 

 

修改配置文件 `eslintrc.js`

```js
/*
 * "off"或者0，不启用这个规则
 * "warn"或者1，出现问题会有警告
 * "error"或者2，出现问题会报错
 */
```

```js
module.exports = {
  root: true,
  env: {
    node: true，
	browser: true,
    es6: true,
  },
// 关键：启用 airbnb 规则
  extends: [
    'plugin:vue/essential', 
	'airbnb-base'，
    'eslint:recommended', // 启用推荐的规则，可报告一些常见的问题
  ],
// 使用语言及版本
  parserOptions: {
    ecmaVersion: 2020,
    sourceType: 'module',
  },
// 个人自定义规则
  rules: {
	'no-console': process.env.NODE_ENV === 'production' ? 'warn' : 'off',
    'no-debugger': process.env.NODE_ENV === 'production' ? 'warn' : 'off',
    'prefer-const': 0,
    'no-unused-expressions': 0,
    'no-unused-vars': ['error', { args: 'after-used' }],
    "arrow-parens": ["error", "as-needed"], // 箭头函数的参数可以不使用圆括号

    "no-constant-condition": 0, // 禁止在条件中使用常量表达式
    "no-dupe-args": 0, // 禁止 function 定义中出现重名参数
    "no-dupe-keys": 0, // 禁止对象字面量中出现重复的 key
    "no-ex-assign": 0, // 禁止对 catch 子句的参数重新赋值
  },
  overrides: [
    {
      files: ['**/__tests__/*.{j,t}s?(x)', '**/tests/unit/**/*.spec.{j,t}s?(x)'],
      env: {
        jest: true
      }
    }
  ]
};
```


设置 Vscode 的 `eslint` 插件

 

```js
"eslint.autoFixOnSave": true, // 保存时自动修复
"eslint.options": {
    "configFile": "./.eslintrc.js" // 配置文件 eslintrc.js 的地址
  },
"eslint.validate": [
    "javascript",
    "javascriptreact",
// 启用 html 和 vue 中 ESLint 验证和自动修复
    {
      "language": "html",
      "autoFix": true
    },
    {
      "language": "vue",
      "autoFix": true
    }
  ],
"editor.codeActionsOnSave": {
      "source.fixAll.eslint": true
  },
  ```
