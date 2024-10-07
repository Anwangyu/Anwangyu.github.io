



<figure style="display: flex; ">
    <img src="https://notion-emojis.s3-us-west-2.amazonaws.com/prod/svg-twitter/1f3a3.svg" width="100" style="margin-right: 1px;" />
    <figcaption style="max-width: 700px; white-space: normal;">
        <h1 style="margin: 0;">windows 关于设置cmd默认启动项</h1>
        <span>💡 Tips!: 本篇是为了解决使用 CMD 默认启动后的初始页面设置 </span>
    </figcaption>
</figure>



- 起因是大多数用户只是解决了使用右键打开或者新建一个终端的时候才显示自己需要的问题。
- 60s解决  

上图

```java
// 默认路径
HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Command Processor

"C:\\Program Files\\PowerShell\\7\\pwsh.exe"
"C:\\Program Files\\PowerShell\\7\\pwsh.exe" -NoLogo  // 去除版本号显示 可有可无
```

![image-20241007151430756](./assets/windows%20%E5%85%B3%E4%BA%8E%E8%AE%BE%E7%BD%AEcmd%E9%BB%98%E8%AE%A4%E5%90%AF%E5%8A%A8%E9%A1%B9/image-20241007151430756.png)

如果该路径下没有AutoRun，那么创建一个字符串值

![image-20241007151451957](./assets/windows%20%E5%85%B3%E4%BA%8E%E8%AE%BE%E7%BD%AEcmd%E9%BB%98%E8%AE%A4%E5%90%AF%E5%8A%A8%E9%A1%B9/image-20241007151451957-1728286325405-3-1728286330290-5.png)

最后，大功告成

![image-20241007151515879](./assets/windows%20%E5%85%B3%E4%BA%8E%E8%AE%BE%E7%BD%AEcmd%E9%BB%98%E8%AE%A4%E5%90%AF%E5%8A%A8%E9%A1%B9/image-20241007151515879.png)

<aside> 💡温馨提示，下次使用winget更新的时候，比如我想要使用新的版本了，记得看下autorun的路径确保启动的”xxx.exe”的路径正确即可






