### 说明
校园网会在每日3:00被自动踢下线，通过每日定时发送登录请求来实现不断网功能
### 步骤
#### 1.确保系统支持**curl**命令
验证cmd是否已支持curl命令:在windows内，打开cmd，输入
```python
    curl
```
如果不支持该命令，建议下个git，它可以为你配置一些unix环境

#### 2.新建autoLogin.bat文件
```shell  
curl -d "ac_id=1&action=login&ajax=1&nas_ip=&password=[password]&save_me=1&user_ip=[ip]&user_mac=&username=[username]" "http://10.108.255.249/include/auth_action.php"

```  
复制上述内容，将方括号内的内容替换为自己的。
- password 密码
- username 学生卡号
- ip 自己电脑的ip
注意方括号也要删掉

#### 3.为windows设置定时任务
打开**任务计划程序**，全图形化操作，很简单。具体方法可以参考[这篇文章](https://blog.csdn.net/qq_40463753/article/details/84976977).
注意我们的定时计划设置执行文件为autologin.bat.最好设置为每天3:00之后一点点时间，无限循环，勾选是否登录都要执行。
