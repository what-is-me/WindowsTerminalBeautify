# Windows Terminal 美化
## 步骤
### 1. 安装 git（介绍援引自[官方文档](https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git)）

> ### 在 Windows 上安装
>
> 在 Windows 上安装 Git 也有几种安装方法。 官方版本可以在 Git 官方网站下载。 打开 https://git-scm.com/download/win，下载会自动开始。 要注意这是一个名为 Git for Windows 的项目（也叫做 msysGit），和 Git 是分别独立的项目；更多信息请访问 http://msysgit.github.io/。
>
> 要进行自动安装，你可以使用 [Git Chocolatey 包](https://chocolatey.org/packages/git)。 注意 Chocolatey 包是由社区维护的。
>
> 另一个简单的方法是安装 GitHub Desktop。 该安装程序包含图形化和命令行版本的 Git。 它也能支持 Powershell，提供了稳定的凭证缓存和健全的换行设置。 稍后我们会对这方面有更多了解，现在只要一句话就够了，这些都是你所需要的。 你可以在 GitHub for Windows 网站下载，网址为 [GitHub Desktop 网站](https://desktop.github.com/)。

### 2. Powershell 美化

- 管理员权限打开power shell，输入：
```powershell
Install-Module posh-git -Scope CurrentUser
Install-Module oh-my-posh -Scope CurrentUser
```
- 如果出现错误，试试如下解决方案：
  - [scope安装](https://blog.csdn.net/luoyooi/article/details/102990113)
  
- 接着输入：

```powershell
notepad $profile
```
- 在打开的记事本中输入：
```poweshell
Import-Module posh-git
Import-Module oh-my-posh
Set-PoshPrompt paradox
```
- 挑选你喜欢的主题来替换`paradox`，主题预览参见[官网](https://ohmyposh.dev/docs/themes)
- 下载字体，推荐[更纱等距黑体](https://github.com/laishulu/Sarasa-Mono-SC-Nerd)并在power shell默认值和属性处替换
### 3. Windows Terminal 美化

- 直接把settings.json替换Windows Terminal的settings.json，并修改其中某些片段：

- ```json
  //个人美化配置
    "profiles": {
      "defaults": {
        "acrylicOpacity": 0.5, //透明度
        "antialiasingMode": "cleartype",
        "backgroundImage": "https://api.ixiaowai.cn/api/api.php", //背景图片地址(这个地址花里胡哨的)(也可以使用本地的图片，要绝对路径)
        "backgroundImageOpacity": 0.7, //背景透明度(务必>=acrylicOpacity,否则会有黑色框框)
        "backgroundImageStretchMode": "uniformToFill", //背景填充模式
        "cursorColor": "#FFFFFF", //光标颜色
        "cursorShape": "bar", //光标设成|
        "fontFace": "更纱黑体 Mono SC Nerd", //字体
        "fontSize": 14, //字的大小
        "startingDirectory": "D:/projects", //打开的地址(自行修改成你想要的)
        "useAcrylic": true //打开透明样式
      },
  ```
  
- ```json
  //git配置(其实只要把D:\\Program Files\\Git替换一下就行了)
        {
          "commandline": "D:\\Program Files\\Git\\bin\\bash.exe", //git起始位置(自己修改)
          "guid": "{1c4de342-38b7-51cf-b940-2309a097f585}", //与其他的几个不同就行(位数得一致)
          "hidden": false,
          "icon": "D:\\Program Files\\Git\\mingw64\\share\\git\\git-for-windows.ico", //图标位置(自己修改)
          "name": "Git" //名(自己修改)
        },
  ```

完整的settings.json我也放了

## 参考

1. [Windows Terminal美化教程](https://blog.csdn.net/zhouchen1998/article/details/107484782)

2. [Windows Terminal 美化实例](https://zhuanlan.zhihu.com/p/76436374)

3. [Windows Terminal终端美化](https://blog.csdn.net/anmin8888/article/details/109145824)
