<figure style="display: flex; ">
    <img src="https://notion-emojis.s3-us-west-2.amazonaws.com/prod/svg-twitter/1fa9f.svg" width="100" style="margin-right: 1px;" />
    <figcaption style="max-width: 700px; white-space: normal;">
        <h1 style="margin: 0;">Windows 重置系统后快速启动恢复mysql</h1>
        <span>💡 Tips!: **None**</span>
    </figcaption>
</figure>

### **1.首先进行环境变量配置**

“此电脑”，右键选择“属性”——“高级系统设置”——“环境变量”

在下方的“系统环境变量”中找到Path，双击打开

点击右侧“新建”，把Mysql安装路径下的bin路径粘贴进来

D:\MySQL\mysql-8.0.19-winx64\bin

### **2.添加Mysql服务**

首先将安装路径下的data文件夹重命名为data1（因为后面的操作需要重新创建data文件夹，如果data文件夹已存在会报错，这里先改名，后面的步骤可恢复）

打开cmd（以管理员身份运行，否则会提示权限不足）

进入bin目录D:\MySQL\mysql-8.0.19-winx64\bin

接着运行

```bash
mysqld  --initialize
// 执行
mysqld -install
```

这里进行完成后，可在任务管理器——服务中找到Mysql，并且在mysql的安装路径下多了一个data文件夹，这里只需将该文件夹删除掉，并将上面步骤的data1重新命名为data即可。

最后测试mysql服务是否可以启动net start mysql
即可完成！