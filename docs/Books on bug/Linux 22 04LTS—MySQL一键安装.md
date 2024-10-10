<figure style="display: flex; ">     <img src="https://notion-emojis.s3-us-west-2.amazonaws.com/prod/svg-twitter/1f427.svg" width="100" style="margin-right: 1px;" />     <figcaption style="max-width: 700px; white-space: normal;">         <h1 style="margin: 0;">Linux 22.04LTS—MySQL一键安装 </h1>         <span>💡Tips!:咻咻咻~~~ </span>     </figcaption> </figure>

# 

```bash
sudo apt update

#查看可使用的安装包
sudo apt search mysql-server

#安装最新版本
sudo apt install -y mysql-server
#安装指定版本
sudo apt install -y mysql-server-8.0

# 这里加-y本意上是在安装过程中提示设置密码的,但是直接下载完了，不过没关系
# 下载完成后
# 启动mysql服务
sudo systemctl start mysql 
# 开机启动
sudo systemctl enable mysql
# 检查mysql状态<之后回出现Active那一栏为绿色显示running> 这是正常的 随后退出即可
sudo systemctl status mysql

# 接下来是登录修改密码环节
# 查看账户和密码
sudo cat /etc/mysql/debian.cnf
```

![Untitled](./assets/Linux%2022%2004LTS%E2%80%94MySQL%E4%B8%80%E9%94%AE%E5%AE%89%E8%A3%85/Untitled.png)

```bash
# 我输入这个登录，其他人请看自己的user和password
mysql -udebian-sys-maint -p9ZaifpIvGDbPvKoO
# 查到了有一个root用户，个人习惯使用 mysql -uroot -proot登录
 SELECT User, Host FROM mysql.user WHERE User = 'root';
 
# 修改了个人的user
ALTER USER 'root'@'localhost' IDENTIFIED BY 'root';
# 之后全部退出以后，以sudo权限重新操作进入登录mysql
sudo mysql
```

![Untitled 1](./assets/Linux%2022%2004LTS%E2%80%94MySQL%E4%B8%80%E9%94%AE%E5%AE%89%E8%A3%85/Untitled%201.png)

```bash
# 修改 root 用户的认证插件为 mysql_native_password，以便通过密码进行认证：
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'root';
FLUSH PRIVILEGES;
# 退出 MySQL，然后再次尝试使用新密码登录：
mysql -uroot -proot

```

大功告成

![Untitled 2](./assets/Linux%2022%2004LTS%E2%80%94MySQL%E4%B8%80%E9%94%AE%E5%AE%89%E8%A3%85/Untitled%202.png)