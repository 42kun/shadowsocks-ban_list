# Shadowsocks-ban_list

原版的shadowsocks，另添加了屏蔽连接选项。

## 安装方法

~~~
wget https://codeload.github.com/42kun/shadowsocks-ban_list/zip/master
unzip master
python shadowsocks-ban_list-master/setup.py install 
~~~



## 使用方法

#### 创建ban配置

~~~
vi /etc/shadowsocks/ban_list
~~~

请在本文件内输入需要屏蔽的连接名的子串，不同字串用换行符隔开

#### 启动shadowsocks

~~~
ssserver -c /etc/shadowsocks/shadowsocks.json -b /etc/shadowsocks/ban_list -d start
~~~

请用-b指定ban_list位置

#### 查看屏蔽情况

打开shadowsocks日志

~~~
tail -f /var/log/shadowsocks.log
~~~

![](https://raw.githubusercontent.com/42kun/shadowsocks-ban_list/master/img/ban-img.PNG)

