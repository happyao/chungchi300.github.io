---
title: >-
  Double your coding and refactoring speed, must know function and keymap you
  should look for Editor & IDE(visual studio code example for react&node js) from effective software engineer
date: 2018-05-04 10:28:21
tags:
---

＃阅读和编码

##语法高亮

Vscode默认语法高亮** JS，JSX，TS，TSX **。

##函数调用时显示定义

使用绝对导入时需要[项目配置]（＃项目配置）

##在一个文件中查找

Vscode命令：actions.find
Vscode快捷键：Ctrl + F

##替换

Vscode命令：editor.action.startFindReplaceAction
Vscode快捷键：Ctrl + H
建议的重命名快捷键：Ctrl + R

##查找文件（或项目）

Vscode命令：workbench.action.findInFiles
Vscode快捷键：Ctrl + Shift + F

##替换文件

Vscode命令：workbench.action.replaceInFiles
Vscode快捷键：Ctrl + Shift + H
建议的重命名快捷键：Ctrl + Shift + R

## 快速修复

Vscode命令：editor.action.quickFix
Vscode快捷键：Ctrl +。

##移动行

Alt +箭头向上/向下

##多光标编辑

Alt + Shift +箭头向上/向下

＃文件导航

使用绝对导入时需要[项目配置]（＃项目配置）

## 打开文件

Vscode命令：workbench.action.files.openFile
Vscode快捷键：Ctrl + P

##转到Symbol

Vscode命令：workbench.action.gotoSymbol
Vscode快捷键：Ctrl + Shift + O
建议的重命名快捷键：Ctrl + O

##定义

Vscode命令：editor.action.goToDeclaration
Vscode快捷键：F12

##查找行

Vscode命令：workbench.action.gotoLine
Vscode快捷键：Ctrl + g

##关闭当前编辑器

Vscode命令：workbench.action.closeWindow
Vscode快捷键：Ctrl + w

**参考**
[文件导航]（https://code.visualstudio.com/docs/editor/editingevolved）

＃重构

使用绝对导入时需要[项目配置]（＃项目配置）

##重写函数/变量名称

Vscode命令：workbench.action.closeWindow
Vscode键映射：F2

**参考**
[重构]（https://code.visualstudio.com/docs/editor/refactoring）

＃项目配置

你需要添加以下配置于`'jsconfig.json'`或`'tsconfig.json'`中（当你使用typescript时），以使用[** import absolute path **]（https://medium.com/@ktruong008/absolute-imports-with-create-react-app-4338fbca7e3d）

```
{
  “compilerOptions”：{
    “baseUrl”：“src”，
    “paths”：{
      “src / *”：[“*”]
    }，
  }
}
```

＃ 插件

##语法检查

[Code Spell Checker]（https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker）

##自动排版

[Prettier]（https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode）

##Markdown

[Markdown all in one]（https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one）

