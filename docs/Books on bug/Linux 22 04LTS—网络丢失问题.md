<figure style="display: flex; ">
    <img src="https://notion-emojis.s3-us-west-2.amazonaws.com/prod/svg-twitter/1f427.svg" width="100" style="margin-right: 1px;" />
    <figcaption style="max-width: 700px; white-space: normal;">
        <h1 style="margin: 0;">Linux 22.04LTS—网络丢失问题</h1>
        <span>💡Tips!: Failed to stop network-manager.service: Unit network-manager.service not loaded.</span>
    </figcaption>
</figure>
# 解决思路
## 方法一


```bash
sudo service NetworkManager stop
sudo rm /var/lib/NetworkManager/NetworkManager.state
sudo service NetworkManager start
```

## 方法二

```bash
sudo vim /etc/NetworkManager/NetworkManager.conf #修改managed=True
```

重启服务

```bash
sudo service network-manager restart
```

```bash
# 查看启用的网卡
ifconfig
# 查看所有网卡
ifconfig -a
```