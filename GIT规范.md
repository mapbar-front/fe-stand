## GIT规范
> 本文主要是从git分支、commit 两个方面进行说明



1. git 分支  
   
  1.1 master（主分支，线上分支） 
    - master代表一个稳定的可运行的版本，是线上分支

    - 该分支为只读分支，不能直接在此分支上进行修改。

    - 所有在 master 分支的推送应该打标签做记录，方便追溯。

  1.2 develop（测试环境分支）
    - 主开发分支，测试环境分支  

    - develop分支，只进行合并操作，合并的分支是当前要进行测试的开发分支。这个分支是一直存在的。   

    - develop分支的合并要求：提测什么需求，就合并相关分支的代码

 1.3 hotfix（线上bug修复分支）

  - 基本格式为：hotfix-date-name-问题描述（hotfix-20210204-mpb-xxx）

  - hotfix分支，为解决线上突发问题的分支。

  - hotfix分支的产生：从master上拉的一个新分支。

  - hotfix分支的销毁：上线完毕后，由分支owner进行销毁。

  - hotfix分支的合并：如果需要经过测试，先合并到develop分支，测试过后合并到master。如果属于紧急修复，响应时间作为第一参考标准的时候，经过自测，直接合并到master分支。

     1.4 dev（开发分支）
  - 基本格式为：dev-版本-date（dev-4.0.3-20210204）

  - dev分支，为每开发者的开发分支。

  - dev分支的产生：从master上拉的一个新分支。

  - dev分支的销毁：上线完毕后，由分支owner进行销毁。

     1.5 分支操作流程
  - 新的需求开发开始，先从master分支拉一个新的需求分支-dev分支，分支需要遵循命名规范

  - 开发完成，把feature分支的代码合并到develop分支

  - 测试阶段开始，测试提出的bug，在 dev 分支上进行修复，修复完成持续合并到 develop 分支

  - 确认可以上线后，在 gitlab 上提交 MR，对改动再review 一遍，没有问题后合并

    

1. commit规范
     格式：<type>(<scope>): <subject>，其中 type（必需）、scope（可选）和subject（必需）

    2.1 type：
         用于说明 commit 的类别，只允许使用以下 7 个标识：

     1. feat：新功能（feature）

            2. fix：修补 bug

            3. docs：文档（documentation）

            4. style：格式（不影响代码运行的变动）

            5. refactor：重构（不是新增的功能，也不是修改 bug 的代码变动）

            6. test：增加测试

            7. chore：构建过程或辅助工具的变动

       通常 feat 和 fix 会被放入 changelog（变更日志） 中，其他类型则不会。

    2.2 scope：
       用于说明 commit 影响的范围，为可选值。通常是文件、路径、功能等

    2.3 subject：
       是 commit 目的的简短描述

3. Git hook 设置 `commit message` 校验   
    3.1 具体使用
        在项目中安装 `husky，commitlint` 相关依赖

     `npm install husky @commitlint/config-conventional @commitlint/cli --save-dev`

       在 `package.json` 文件中添加 `husky` 的 git hook 配置

    
```js
{
   "husky": {
      "hooks": {
           "commit-msg": "commitlint -x @commitlint/config-conventional -E HUSKY_GIT_PARAMS"
       }
   }

}
```

       此时，如果提交的 `commit message` 不符合规范，该 hook 就会报错。  

  3.2 配置规则
     我们可以生成 `commitlint.config.js` 或 `.commitlintrc.js` 文件来配置自定义的规则

     `commitlint.config.js` 文件的配置如下：

   

```js
module.exports = {
   extends: [
       "@commitlint/config-conventional"
   ],
   rules: {
       'type-enum': [2, 'always', [
           'upd', 'feat', 'fix', 'refactor', 'docs', 'chore', 'style', 'revert'
      ]],
     'type-case': [0],
     'type-empty': [0],
     'scope-empty': [0],
     'scope-case': [0],
     'subject-full-stop': [0, 'never'],
     'subject-case': [0, 'never'],
     'header-max-length': [0, 'always', 72]
  }
}
```

      更多配置规则可参照 commitlint 官方网站：commitlint rules