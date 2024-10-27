<figure style="display: flex; ">
    <img src="https://notion-emojis.s3-us-west-2.amazonaws.com/prod/svg-twitter/1f3aa.svg" width="100" style="margin-right: 1px;" />
    <figcaption style="max-width: 700px; white-space: normal;">
        <h1 style="margin: 0;">关于nvm use <version>问题</h1>
        <span>💡 Tips!: 首先网上的大多数教程的下载是正确的，但是缺少了一个关于nvm use <version>显示成功但是版本并没有切换的解决。 </span>
    </figcaption>
</figure>
**单刀直入**

比如说有两个版本

```
14.17.0

22.03.1
```

那么如果使用nvm use 14.17.0 可能导致无法切换成功，但是使用以下即可

```
nvm use 14
```

就近匹配交给nvm自动解决

### **【关键】设置全局模板（prefix）和缓存文件（cache）的存放路径：**

```
# npm config set cache "%NVM_SYMLINK%\node_cache"

npm config set cache "D:\nvm\nodejs\node_cache"

```

```
# npm config set prefix "%NVM_SYMLINK%\node_global"

npm config set prefix "D:\nvm\nodejs\node_global"

```

```
# 可编辑 .npmrc 配置文件
npm config edit

```

```
# 查看部分 .npmrc 配置信息
npm config ls
```