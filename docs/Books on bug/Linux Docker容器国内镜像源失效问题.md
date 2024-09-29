<figure style="display: flex; ">
    <img src="https://notion-emojis.s3-us-west-2.amazonaws.com/prod/svg-twitter/1f427.svg" width="100" style="margin-right: 1px;" />
    <figcaption style="max-width: 700px; white-space: normal;">
        <h1 style="margin: 0;">Linux Docker容器国内镜像源失效问题</h1>
        <span>💡 Tips!: 以下容器于2024.8.9测试可以拉取使用</span>
    </figcaption>
</figure>


这里修改daemon.json文件


```bash
sudo vim /etc/docker/daemon.json


```

参考源，这里本机当时全部加入了

```bash
{
  "registry-mirrors": [
    "https://docker.m.daocloud.io", 
    "https://docker.jianmuhub.com",
    "https://huecker.io",
    "https://dockerhub.timeweb.cloud",
    "https://dockerhub1.beget.com",
    "https://noohub.ru,",
    "https://hub.uuuadc.top",
    "https://docker.anyhub.us.kg",
    "https://dockerhub.jobcher.com",
    "https://dockerhub.icu",
    "https://docker.ckyl.me",
    "https://docker.awsl9527.cn"
  ],
  "dns": ["8.8.8.8", "8.8.4.4"]
}

```

修改完后需要

```bash
sudo systemctl daemon-reload #重载systemd管理守护进程配置文件
sudo systemctl restart docker #重启 Docker 服务

# 检查镜像源是否加入成功
docker info
```

以上若还存在问题，可以考虑使用个人镜像服务

```bash
{"registry-mirrors": ["https://dockerpull.com"]}

# 设置好以后依然是重复上述操作
```
