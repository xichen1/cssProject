# CodingStarterTeam/codingstarter-layout

> 这是一个供 layout 组同学提交自己静态实现的项目。

## Build Setup

**这部分非常重要，请一定要看完。**

> **非常重要的提示**：你的工作目录在 `./app/YourGithubUsername` 里，不要向 `./test` 里提交任何非测试用例文档。请保证跟着 Build Setup 走完项目初始化的流程。

```bash
# step 0
# open your terminal, and flow these steps.

# step 1
# make a project directory, like `codingstarter-layout`
mkdir -p codingstarter-layout

# clone the project
git clone https://github.com/CodingStarterTeam/codingstarter-layout.git ./codingstarter-layout

# step 2
# enter the project directory
cd codingstarter-layout

# install global dependencies, maybe you need like node-sass etc.
# npm i -g node-sass

# install dependency, and waiting npm install finish.
npm install

# step 3
# edit `gulpfile.js`, is important!
# edit line 20 in `gulpfile.js` file,
# replace the instanceName value to your github username.

# step 4
# create workspace, you will work in here.
# copy the example and rename it
# like : cp example/* yourGithubUsername/
cd ./app
cp example/* yourGithubUsername/

# step 5
cd ../
# run develop server and begin develop
npm run dev
```

This will automatically open <http://localhost:9000/>

## Start Coding

为了便于后期代码合并以及迭代，我们对编码过程做一些约定，请大家在这些约定下进行开发。

这些约定对一些成员来说，也许有些超纲，但是希望大家，能挑战比自己能力高出些许的难度。

> layout 组存在的意义，是因为我们的成员中有比较新手的部分。所以我们建议大家，分别提交自己的实现，当然也鼓励大家对同一份实现进行协作。

### 目录结构

强烈建议从 ./app/example 复制一份副本开始你的编码。这样能最大限度的保持所有人的目录结构一致性。

```bash
# 这是 example 的目录结构
./example
├── ./fonts # 你使用的字体
├── ./images # 你的图片资源
├── ./index.html # 入口文件，也是你的主页面。所有其他 html 一率与 index.html 平行
├── ./scripts # 所有的 js 脚本放在这里
│   └── ./scripts/main.js # 主要的 js 文件，不允许改名
└── ./styles # 放置所有的 css 文件
    ├── ./styles/app.scss # 主要的 css 入口文件，不允许改名
    ├── ./styles/components # 组件的 css 目录，不允许改名
    │   ├── ./styles/components/btn.scss # 示例，可删除
    │   └── ./styles/components/sidebar.scss # 示例，可删除
    ├── ./styles/components.scss # 所有组件合并引用的 css，不允许改名
    ├── ./styles/layout.scss # 布局，不允许改名
    ├── ./styles/mixin.scss # mixin，不允许改名
    ├── ./styles/transition.scss # transition，不允许改名
    ├── ./styles/typography.scss # 文字排版，不允许改名
    ├── ./styles/utilities.scss # 辅助样式，不允许改名
    └── ./styles/variables.scss # sass 变量，不允许改名
```

我们已经把最常用的目录结构和样式文件做了约定，也就是你只能在这个结构下进行开发。

所有的样式内容你都可以进行修改和增加，但是被标注为 `不允许改名` 的文件，也不允许 `删除`，除非你知道自己在做什么。我们建议你将相关的样式写入相关联的文件中。

你也可以新建自己的样式文件。比如抽象化你的组件，放入 `components` 目录中，并在 `components.scss` 文件中导入你的组件。

你也可以在 `styles` 目录中加入你自己的样式文件，但是一定要在 `app.scss` 中引入你的样式。

### index.html 入口文件

这是你的实现的入口文件。你的所有 html 文件都应该以它为原始模板进行开发。

文件中的 `<!-- build: -->` `<-- endbuild -->` 注释对以及其中的内容不允许删除，除非你知道自己在做什么。

### CSS Reset

项目已经集成 `normalize.css`，不需要再对自己的项目引入额外的 reset css。

### CSS: Sass(sass/scss)

我们约定使用 Sass 进行样式开发，并遵循 scss 语法。

> 不知道什么是 sass 的伙伴，我们建议你先阅读这部分内容。[学习 Sass](https://www.sasscss.com/)

我们对项目中的 Sass 开发，进行以下约定：

1. 默认不使用 `变量`、`mixin` 等高级功能，但是鼓励有能力的伙伴使用；
2. 从你熟悉的 `.css` 文件转化成 Sass 非常简单，只需要将文件后缀改为 `.scss`即可；
3. 遵循项目目录结构中，关于样式部分的约定。

### npm 及 javascript 库的使用

你可以使用利于开发的各种第三方代码库。

javascript 库建议使用 CDN 的方式引用。当然你也可以使用 npm，如果使用 npm ，你应该清楚如何处理你的 npm 包和 layout 这个仓库的 npm 包的有关系。

## About git & github

### 创建本地项目

```bash
# make a project directory, like `codingstarter-layout`
mkdir -p codingstarter-layout

# clone the project
git clone https://github.com/CodingStarterTeam/codingstarter-layout.git ./codingstarter-layout

```

### 检查远程仓库中是否有新的提交并拉取

> 工作开始前，或者你有新的修改需要提交前，建议先进行这步操作。

```bash
git pull
```

### 提交修改

```bash
# 先将修改过的文件加入暂存区
git add xxx.xx yyy.yy...

# 提交暂存区的文件
git commit -m "这里是文件提交的理由，每一次提交都应该是有目的的"

# 推送更新到远程仓库
git push
```

### 其他操作

```bash
# 查看本地版本库中的文件状态
git status
```

### 备注

IDEA 或者 vscode 都有集成 git 的可视化管理，如果没有，可以安装插件解决。

## Build

```bash
# build for production environment
npm run build
```

## Advanced

```bash
# run test
npm run test

# view all gulp task
npm run tasks

```

## License

Copyright (c) 2020-present CodingStarterTeam
