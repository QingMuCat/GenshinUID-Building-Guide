# GenshinUID-搭建指南
- #### 本教程为Nonebot2搭建教程，本教程适用于win系统以及Linux系统搭建
- #### Tips: GenshinUID3.0beta还是测试服哦，有Bug及时反馈捏
- #### 搭建教程前确保，你已经安装如下环境：Python，Git ，FFmpeg （发送语音所需）。Python版本的话推荐3.10以上，不会安装建议百度，这里提供安装方法链接 [Python安装](超链接地址 "https://zhuanlan.zhihu.com/p/104502997") 方法仅供参考，遇见问题自行百度解决
- #### 安装好之后，建立一个文件夹，命名为BOT
## 下面正式进入教程环节
  ### 1.进入终端，执行```cd Bot```命令, 首先安装虚拟环境```pip install poetry```，运行```poetry -V```查看版本，如果有版本号说明安装成功，最后 ```poetry init```然后出现的提示一直按回车就行，回车完后输入```poetry shell```进入虚拟环境;
  ### 2.安装nb脚手架 ```pip install nb-cli```;
  ### 3.创建nonebot2项目 ```nb create```;
     创建项目示例：
     [?] Project Name: Nonebot2     T：名字，随便填即可，这里以Nonebot2为例
     [?] Where to store the plugin? T：选择插件放置目录，键盘↑↓选择，回车确认，随便选，建议选择src
      > In a "Nonebot2" folder
      > In a src folder
     [?] Which builtin plugin(s) would you like to user?  T：直接Enter
     [?] which adapter(s) would you like to use?   T：在OneBot V11那里按空格，然后Enter
      >  ● OneBot V11
         o 钉钉
         o 飞书
         o Telegram
         o QQ 频道
         o 开黑啦
         o mirai2
         o OneBot V12
  ### 4.安装GenshinUID
      -在插件目录文件夹下执行，这里使用了镜像，若你选择的是src，请进入/src/plugin/目录后再执行命令
       git clone -b nonebot2-beta1 https://ghproxy.com/https://github.com/KimigaiiWuyi/GenshinUID.git --depth=1 --single-branch 
      -进入 GenshinUID 文件夹内，安装依赖库
       poetry install
      -无需添加插件加载目录
  ### 5.启动
      返回Nonebot2文件下，使用nb run启动bot
## 基本教程到这里已经结束了，下面是常见问题解决方法
### 一、   