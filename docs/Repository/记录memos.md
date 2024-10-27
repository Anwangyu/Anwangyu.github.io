<figure style="display: flex; ">
    <img src="https://notion-emojis.s3-us-west-2.amazonaws.com/prod/svg-twitter/1f0cf.svg" width="100" style="margin-right: 1px;" />
    <figcaption style="max-width: 700px; white-space: normal;">
        <h1 style="margin: 0;">据说是轻量级备忘录</h1>
        <span>💡React+Tailwind+TypeScript+Go 开发的备忘录中心，本地且多平台访问，还支持markdown语法。
         </span>
    </figcaption>
</figure>

- 先放地址：https://github.com/usememos/memos?tab=readme-ov-file

----



## 主要特点



- **隐私第一**🏠：掌控您的数据。所有运行时数据都安全地存储在您的本地数据库中。
- **快速创建**✍️：将内容保存为纯文本以便快速访问，并支持 Markdown 进行快速格式化和轻松共享。
- **轻量但功能强大**🤲：我们的应用程序采用 Go、React.js 和紧凑的架构构建，在轻量级软件包中提供强大的性能。
- **可定制**🧩：轻松定制您的服务器名称、图标、描述、系统样式和执行脚本，使其独一无二。
- **开源**🦦：Memos 拥抱开源的未来，所有代码均可在 GitHub 上获取，以实现透明度和协作。
- **免费使用**💸：完全免费享受所有功能，任何内容均不收费。

![image-20241028001040336](./assets/%E8%AE%B0%E5%BD%95memos/image-20241028001040336.png)

docker一键部署

```
docker run -d --name memos -p 5230:5230 -v ~/.memos/:/var/opt/memos neosmemo/memos:stable

```

安装后通过ip+端口5230 即可打开访问！