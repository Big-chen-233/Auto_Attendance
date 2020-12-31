# 中南大学nCov健康打卡定时自动脚本（Github-Actions版）

**注意**：本master分支版本代码使用Github-Actions定时运行，无需部署在服务器。如需在服务器中运行，请使用service分支中的代码。

## Description

**特此声明**：项目用于学习交流，仅用于各项无异常时打卡，如有身体不适等情况还请自行如实打卡！

* 可定时，默认为每天7点5分
* 默认每次提交上次所提交的内容（只有时间部分更新）

重新设置//1/1

### 运行方式

1. fork本项目到你的个人账号
   
2. 设置Secrets

    从Github中进入刚刚fork到你的个人账号下的本项目，打开项目的Settings->Secrets页面
    

![](https://raw.githubusercontent.com/lxy764139720/Figurebed/master/img/20200817190653.png)

​	点击New Secret按钮新建四个密码：

* USERNAME：你的中南大学学工号

* PASSWORD：你的中南大学信息门户密码

* EAI_SESS：你的eai-sess cookie

* UUKEY：你的UUkey cookie

3. 启动定时打卡

    进入Code页面，点击修改按钮

    ![](https://raw.githubusercontent.com/lxy764139720/Figurebed/master/img/20200817191741.png)

    在readme文件中随意修改任意字符（比如加个空格），然后点击下方的Commit Changes即可激活每日定时打卡脚本

    ![](https://raw.githubusercontent.com/lxy764139720/Figurebed/master/img/20200817192122.png)

4. 查看运行情况

    打开Actions页面，此时在workflows中应该出现了正在运行的工作流。当提交文件时会马上进行一次打卡，以后将会默认在每天的7:05进行打卡

    ![](https://raw.githubusercontent.com/lxy764139720/Figurebed/master/img/20200817192416.png)

## 修改打卡时间

打开项目中的/.github/workflows/python-package.yml文件，修改corn中的值，注意使用UTC零区时间。

例如，当前默认打卡时间是北京时间(UTC+8)每天7:05，换算成UTC零区时间为23:05。

更多关于时间的具体书写格式请参考[POSIX cron 语法](https://crontab.guru/)和[官方文档](https://docs.github.com/cn/actions/reference/events-that-trigger-workflows#)。

![](https://raw.githubusercontent.com/lxy764139720/Figurebed/master/img/20200817194102.png)

![](https://raw.githubusercontent.com/lxy764139720/Figurebed/master/img/20200817194250.png)

---

参考开源仓库：

1. [浙大nCov健康打卡定时自动脚本](https://github.com/Tishacy/ZJU-nCov-Hitcarder)
2. [北京化工大学COVID-19自动填报脚本](https://github.com/W0n9/BUCT_nCoV_Report)
