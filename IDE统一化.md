## IDE统一化
### 1.为什么要统一化？

`case：`新人入职，发现一提交代码，其他人拉下来全是报红错误。找其他同事看下代码，结果光适应代码风格花了好一会。  
在团队协作中，提高代码质量和开发效率，首先会想到从代码风格入手。但大多数时候，代码风格起于讨论，也止于讨论，虎头蛇尾有始无终。无法确定一个让所有人都满意的方案，就很难执行下去。针对这种情况，提出约定大于配置。  
### 2.解决方案 

`VSCode `  
为什么是VSCode？Free. Built on open source. Runs everywhere.   

- 智能：除了语法高亮显示和智能补全之外，智能补全还提供基于变量类型、函数定义和导入模块的智能补全。 

- debug：从编辑器中调试代码。启动或附加到正在运行的应用程序，并使用断点、调用堆栈和交互式控制台进行调试。 

- 内置Git：编辑器中检查差异、分段文件和提交。 

- 可扩展和可定制，丰富的package资源 


###  3. package 
Chinese(Simplified) Language Pack for Visual Studio Code（官方汉化） 

Beautify（美化代码） 

Code Spell Checker（拼写检查） 

indent-rainbow（代码缩进） 

Rainbow Brackets（括号配对） 

Prettier（统一代码风格） 

Path Intellisense(智能路径提示) 

vetur（语法高亮、智能感知、Emmet等） 

GitLens（详细的git提交日志）

### 4.setting.json

```js

{

  "eslint.validate": [

    "javascript",

    "javascriptreact",

    {

      "language": "typescript",

      "autoFix": true

    },

    {

      "language": "typescriptreact",

      "autoFix": true

    }

  ],

  "jest.autoEnable": false,

  "typescript.tsdk": "node_modules/typescript/lib"
  ```

  ###  5. .vscode文件夹的作用

    为了统一团队的` vscode` 配置，我们可以在项目的根目录下建立`.vscode`目录，在里面放置一些配置内容，比如：

    `settings.json`：工作空间设置、代码格式化配置、插件配置

 ` .vscode`目录里的配置只针对当前项目范围内生效。将`.vscode`提交到代码仓库，大家统一配置时，会非常方便。

 ### 6.参考资料 

如何让 VS Code 更好用10倍？这里有一份VS Code 新手指南 

Prettier看这一篇就行了 

这样配置，让你的VS Code好用到飞起！ 

通过配置 VS Code 来提高生产力 

第一次使用VS Code时你应该知道的一切配置

https://github.com/viatsko/awesome-vscode