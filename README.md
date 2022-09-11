# GenshinUID-搭建指南 V3.1
- #### 本教程为Nonebot2搭建教程，本教程适用于win系统以及Linux系统搭建
- #### Tips: GenshinUID3.1，有Bug及时反馈捏
- #### 搭建教程前确保，你已经安装如下环境：Python，Git ，FFmpeg （发送语音所需）。Python版本的话推荐3.10以上，不会安装建议百度，自行百度。
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
  ### 4.配置nonebot2目录文件
      -将.env文件中的ENVIRONMENT=dev，上述的dev修改为prod
      -再次修改目录下的.env.prod的文件内容
       示例格式：
       HOST=0.0.0.0  # 配置 NoneBot2 监听的 IP/主机名
       PORT=8080  # 配置 NoneBot2 监听的端口
       SUPERUSERS=["123456789", "987654321"]  # 配置 NoneBot 超级用户
       NICKNAME=["awesome", "bot"]  # 配置机器人的昵称
       COMMAND_START=["/", ""]  # 配置命令起始字符
       COMMAND_SEP=["."]  # 配置命令分割字符
  ### 5.安装GenshinUID
      -在插件目录文件夹下执行，这里使用了镜像，若你选择的是src，请进入/src/plugin/目录后再执行命令
       git clone -b nonebot2-beta1 https://ghproxy.com/https://github.com/KimigaiiWuyi/GenshinUID.git --depth=1 --single-branch 
      -进入 GenshinUID 文件夹内，安装依赖库
       poetry install，若此命令更新报错可以采用此命令执行 python -m pip install -r requirements.txt
      -无需添加插件加载目录
  ### 6.启动
      返回Nonebot2文件下，使用nb run启动bot
  ### 7.更新手段
      更新命令：git pull 
##  数据文件常用位置
### 1.ID_DATA.db (此文件存储CK以及stoken相关数据)
### 2.抽卡记录以及角色面板在插件目录下player 
-------
## 基本教程到这里已经结束了，下面是常见问题解决方法
### 一、 绑定ck，出现，Cookie缺失关键字段 account_id 和 cookie_token，导致数据库未初始化，可以尝试使用无痕模式获取或退出后重新登录获取；
### 二、 Bot启动报此错误```No module named 'xxxxx'```
         解决方法：
         1.依赖未安装，使用命令pip install xxxxx即可; T：就是缺啥补啥，就完了
         2.无效可以尝试pip3 install xxxxx;           T: 甚至你可以重装，重装可以解决90%的问题（确信）
### 三、 Bot启动报此错误```Caonot load plugin "..."```
         解决方法：
         1.nb plugin install ...   T:也是缺啥补啥
### 四、 git pull出现此错误“error: Your local changes to the following files would be overwritten by merge”
          别慌我们有两种解决方案，看你自己选择啦！！！！！
          方案一：
            1.执行 git reset --hard FETCH_HEAD 命令，此目的是：冲掉本地冲突文件
            2.然后重新git pull
          方案二：（根据顺序执行命令）
          命令解释：git stash的时候会把你本地文件进行快照
            1.git stash
            2.git pull origin master  T：这里注意master只是示例，自己看分支名
            3.git stash pop
-------
#### 教程和问题基本就这些了，若教程有误，及时联系QQ：1242550160  呜呜呜呜