# 项目介绍
学习和实践 c/c++的项目模板

配置了makefile在windows下vscode的编译连接和运行(需要mingw64)
### 项目运行

- **代码环境**

  windows 11

- **编辑工具**

  vscode

- **编译器**

  gcc/g++

# vscode插件推荐
## 功能类
- [一键编译运行多种语言](https://github.com/formulahendry/vscode-code-runner):[本项目配置文件](#code-runner插件配置)
- [一键生成c/c++项目目录](https://github.com/danielpinto8zz6/c-cpp-project-generator#readme):非常好用,一键生成
- [一键生成注释](https://github.com/cschlosser/doxdocgen):懒得写注释,**注意:必须在配置文件中定义一个模板才能以能偷懒**
- [一键生成目录树到你的README文件中](https://github.com/zhucyi/project-tree):上面的目录结构根本不用再手打了,一键添加
- [更好的错误信息提示](https://github.com/usernamehw/vscode-error-lens):一些错误会让波浪线很短非常难找,这个插件能很直观的看到错误
- [Tab跳出函数](https://github.com/albertromkes/tabout):写完函数参数时按下tab可以转到函数的)后面方便直接;结束语句
- [markdown实时现示](markdown):在vscode中写README时用的到
- [显示git分支](https://github.com/mhutchie/vscode-git-graph):虽然这个小项目用不到,但值得下载
- [无聊时刷刷力扣](https://github.com/LeetCode-OpenSource/vscode-leetcode):**注意:在设置中改成力扣cn才能登录力扣中国站**
- [你的代码分析](https://github.com/wakatime/vscode-wakatime):**注意:需要注册账号并获取账号的id才能跟踪并分析你的数据**
## vscode美化类
- [github主题](https://github.com/primer/github-vscode-theme):黑色和白色都很好看
- [扁平化图标](https://github.com/PKief/vscode-material-icon-theme):还是喜欢扁平化图标
- [代码连体字](https://github.com/tonsky/FiraCode):很好的字体
# Code-Runner插件配置
[Code Runner官方配置说明](https://github.com/formulahendry/vscode-code-runner)

```
// settings.json文件
{
  //运行插件时保存当前文件
  "code-runner.saveFileBeforeRun": true,
  //ctrl+alt+k运行自定义命令(这里是清除生成文件)
  "code-runner.customCommand": "cd $workspaceRoot && del /q /f .\\out\\$fileNameWithoutExt.exe && echo Cleanup complete!",
  //自定义语言运行命令(ctrl+alt+n运行,ctrl+alt+m结束运行,快捷键失效可能是英伟达游戏内覆盖快捷键占用)
  "code-runner.executorMap": {
    "c": "cd $workspaceRoot && gcc -g $fullFileName -I $workspaceRoot\\include -I $workspaceRoot\\test\\include -o$workspaceRoot\\out\\$fileNameWithoutExt.exe && .\\out\\$fileNameWithoutExt.exe",
    "cpp": "cd $workspaceRoot && g++ -g $fullFileName -I $workspaceRoot\\include -I $workspaceRoot\\test\\include -o$workspaceRoot\\out\\$fileNameWithoutExt.exe && .\\out\\$fileNameWithoutExt.exe"
  },
}
```
