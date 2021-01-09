---
title: 如何使用 GitHub Pages 搭建一个属于自己的网站
date: 2021-01-09 8:30
tags: 
  - Github Page
---
小的时候我就有一个梦想————拥有一个属于自己的网站，相信也有许多人和我一样，想在纷杂的互联网中有一篇只属于自己的净土。然而，建站往往是一个多数人难以驾驭的工作，你至少需要有一台服务器，还需要有一定的计算机知识去运维这台服务器，这就使得许多人就此望而却步了。

但是，如果说有一个平台能够免费提供这样一项服务，你不需要一台服务器，只需要做一些简单的配置，就可以免费搭建起自己的网站，你可以把自己的精力更多投入到属于自己的内容生产上来，你会不会心动呢？

这就是[Github Pages](https://pages.github.com/)，由[Github](https://github.com/)提供的一项免费服务

## 开始

### 创建一个Github账户

要使用Github Page，首先你得有一个Github账户，进入[github.com](https://github.com)后，点击Sign up，填写完相关信息后就注册完成啦

### 创建一个Repository并配置Github Page

注册完成后，你还需要创建一个仓库（Repository），在主页的左上角点击**New**，或[**点此**](https://github.com/new)直接创建

进入创建页后，在Repository name位置填写域名，格式是\[**你的用户名**\]**.GitHub.io**，注意不要选择Private仓库，毕竟你的网站是要让所有人看到的:)。

![创建页](/images/20210109/repo-create.png)

创建后在Repo的标签页点击**settings**进入配置页面

![](/images/20210109/settings-goto.png)

在页面下方找到Github Pages，这里是我们的主页的配置页，点击**Choose Theme**

![](/images/20210109/settings-choose-theme.png)

选择一款你喜欢的主题

![](/images/20210109/settings-select-theme.png)

选择完成后点击**Commit Change**提交

![](/images/20210109/settings-commit-theme.png)

完成后，就可以在浏览器地址栏输入\[**你的用户名**\]**.GitHub.io**

![](/images/20210109/website-init.png)

是不是很惊喜，一个网站就这么生成了！

### 使用Visual Studio Code 和 Github Desktop来编辑和提交你的修改

如你所见，你的网站虽然已经可以访问了，但他还只是一个模板，那么现在就需要我们动动手来写一点自己的东西，那么首先我们需要两样工具

- 文本编辑器，推荐使用[**Visual Studio Code**](https://code.visualstudio.com/)，简称VS Code
- 版本管理工具Git，如果不熟悉命令行工具建议直接使用[**Github Desktop**](https://desktop.github.com/)

> Tips：如果你会使用Git命令行，那么接下来的教程可以选择性跳过

下载完Github Desktop后，登录你刚刚注册的Github账户后，会有一个配置页面，选择默认的即可

![](/images/20210109/github-desktop-config.png)

现在我们需要克隆远端的仓库，即下载在刚刚在Github上创建的仓库，会有一个界面让你选择克隆的路径，按需配置即可，当然要方便能找到:)

![](/images/20210109/github-desktop-clone-local-path.png)

克隆完成后，在对应的文件夹下，就可以看到从远端下载下来的仓库里的文件啦

![](/images/20210109/github-desktop-file-explorer.png)

我们用VS Code对index.md进行简单的编辑，index.md使用的是**Markdown**的语法，如果你对**Markdown**不熟悉，Github提供了简单的[语法说明](https://guides.github.com/features/mastering-markdown/#syntax)，VS Code提供了**Markdown**的插件，可以所见即所得的编辑，你也可以通过搜索引擎了解更多**Markdown**的信息，这里就不过多地赘述了。

好的，我们继续，让我们把文件内容更改为

```markdown
## Hello
Hello, My first page!
```

保存后，打开Github Desktop，上面可以看到我们的更改，但这个更改是临时的，所以我们需要**提交**（**Commit**）。不懂Git的同学可能对这一步很困惑，为什么我已经保存了还需要再“提交”？这里就简单说明一下，这里的提交保存的是你的变动，即你删除了什么，增加了什么，下次你需要找你不小心删掉的某一行的时候，Git仍旧能帮你找到，如果不理解也没关系，这不影响我们接下来的工作。

![](/images/20210109/github-desktop-commit-update.png)

提交完成后，我们需要将我们的更改**推**（**Push**）到远端

![](/images/20210109/github-desktop-push-origin.png)

稍等片刻后（不超过5分钟），再次打开你的网站，你会发现，你已经可以掌控你的网站啦~

![](/images/20210109/website-first-commit.png)

### 设置你的域名

如果你觉得你不喜欢github.io这个域名，想使用自己的域名，没问题的！这才是**自己的网站**的样子！

那么首先你需要有一个域名，如果你还没有注册过，那么个人推荐可以在阿里云的[**万网**](https://wanwang.aliyun.com/?source=5176.11533457&userCode=w1myvuxh)注册，毕竟名声在外。不过当前.com的域名已经比较稀缺了，可以选择.net或者其他域名。

注册完域名后，按照[Github的要求](https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages/managing-a-custom-domain-for-your-github-pages-site),在我们的域名下增加以下的记录类型为A的解析

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```
配置完后如下

![](/images/20210109/domain-record.png)

然后再回到我们先前Github网站上Repo的settings页面，在Github Page下你会看到多了两个选项，在Custom domain下输入我们的域名，点击Save

![](/images/20210109/domain-config-in-github.png)

现在我们就可以用我们自己的域名访问自己的网站了，是不是棒棒哒！

![](/images/20210109/website-custom-domain.png)

但好像还是有点问题，地址栏显示了**不安全**，这对强迫症来说可不太好，所以我们继续回到settings页面，可以看到

![](/images/20210109/domain-config-https-wait.png)

好吧，需要24小时左右才能生成https证书，但是亲测不需要那么久，我等了半小时左右就好啦~

![](/images/20210109/domain-config-https-checkin.png)

勾上之后再打开我们的网站，“不安全”已经消失了，**小锁**已经出现了，非常的完美~

![](/images/20210109/website-custom-domain-https.png)


### 小结

至此，我们已经拥有了一个完全属于自己的网站，我们可以在上面放一些小东西，比如个人简历等任何你想放的东西。开始属于你的互联网世界吧~

当然如果你觉得一个主页不足以容纳你的想象力，你可以使用Hexo等工具在无需编写代码的情况下来生成更加强大的网站，当然本文限于篇幅就不继续写下去了，有时间我会再写一篇关于Hexo的使用教程的。



