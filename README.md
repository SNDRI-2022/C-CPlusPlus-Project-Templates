# 项目介绍
学习和实践 c/c++的项目模板
从[C/C++ Project Generator](https://github.com/danielpinto8zz6/c-cpp-project-generator#readme):从些插件生成c/c++项目目录中自定义自己功能
windows下vscode的编译连接和运行(需要mingw64)
### 项目运行

- **代码环境**

  windows 11

- **编辑工具**

  vscode

- **编译器**

  gcc/g++
# 版本内容更新
###### v1.0.0: 
    1.添加基本项目目录文件
    2.修改makefile文件
###### v2.0.0.0
    1.添加test文件
    2.添加code-runner对此目录的编译和运行
    *注意:*makefile文件未对test目录配置    

###### v2.1.0:
    1.修改Code Runner插件配置
    2.修改launch文件配置
    3.修改tasks文件配置
[code-runner配置说明](#code-runner插件配置)
# vscode插件推荐
## 功能类
- [一键编译运行多种语言](https://github.com/formulahendry/vscode-code-runner):[本项目配置文件](#code-runner插件配置)
- [一键生成c/c++项目目录](https://github.com/danielpinto8zz6/c-cpp-project-generator#readme):非常好用,一键生成
- [一键生成注释](https://github.com/cschlosser/doxdocgen):懒得写注释,**注意:必须在配置文件中定义一个模板才能以能偷懒**
- [更好的强调注释](https://github.com/aaron-bond/better-comments):用颜色强调你要想的的注释
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
  ////运行时自动保存全部文件
  ////"code-runner.saveAllFilesBeforeRun": true,
  //自动清除输出
  "code-runner.clearPreviousOutput": true,
  //默认运行语言
  //"code-runner.defaultLanguage": "cpp",
  //运行插件时保存当前文件
  "code-runner.saveFileBeforeRun": true,
  //ctrl+alt+k运行自定义命令(这里是清除生成文件)
  "code-runner.customCommand": "cd $workspaceRoot && del /q /f .\\out\\$fileNameWithoutExt.exe && echo Cleanup complete!",
  //自定义语言运行命令
  "code-runner.executorMap": {
    "c": "cd $workspaceRoot && gcc -g $fullFileName: -I .\\include -I .\\test\\include -o .\\out\\$fileNameWithoutExt.exe && .\\out\\$fileNameWithoutExt.exe",
    "cpp": "cd $workspaceRoot && g++ -g $fullFileName -I .\\include -I .\\test\\include -o .\\out\\$fileNameWithoutExt.exe && .\\out\\$fileNameWithoutExt.exe",
  },
}
```
