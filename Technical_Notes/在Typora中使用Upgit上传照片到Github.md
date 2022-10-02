<!--第一次更新：20221002-->

最近使用`Typora`写一些markdown的笔记。这个软件的界面非常的简洁，体积小，上手非常的快。以后写一些笔记，都可以使用这个APP。

但是在写笔记的过程中，遇到要添加图片的时候，默认是上传到`Typora`的image文件夹里面。在本地显示当然没有问题，但是把笔记Pull到Github的仓库时，图片是没有办法显示出来的。

看`Typora`的相关文档发现，可以使用`Upgit`这个程序，将笔记里面的图片上传到Github的仓库中。

**下面就是在Typora中，使用Upgit，上传照片到Github（利用Github作图床）**

[TOC]

# Download Typora

[Typora download page](https://typora.io/)

> Typora: A minimal Markdown editor and reader.

# Download Upgit

[Upgit download page](https://github.com/pluveto/upgit)

> Upgit: A native & lightweight tool to helps you upload any file to your Github repository and then get a raw URL for it.

## Process

1. 下载最新的版本，然后将`upgit_macos_amd64`修改成`upgit`

2. 将`upgit`的PATH添加到环境变量中

   ```
   echo PATH
   export PATH="/xx/xx/xx/upgit:$PATH"
   echo PATH
   source /etc/profile
   ```

3. 创建`config.toml`文件，在里面填写相关的一些信息

4. 使用`upgit`

   ```
   ./upgit test.png
   ```

## Problem：Permission denied

在运行`./upgit`的时候出现`Permission denied`错误

**报错情况**

<img src="/Users/meizi/Library/Application Support/typora-user-images/image-20221002215045696.png" alt="image-20221002215045696" style="zoom:67%;" />

**解决方法：修改upgit的权限**

```
1. ls -l 查看upgit的权限
2. 修改upgit的权限为可执行的程序
	chmod 777 upgit
```

**解决结果**

<img src="/Users/meizi/Library/Application Support/typora-user-images/image-20221002215356519.png" alt="image-20221002215356519" style="zoom:67%;" />

**Tips：**当然别忘记在安全与隐私中允许运行upgit

# Setting Typora

1. Typora->偏好设置->图像
2. 上传服务设定->自定义命令，将upgit的路径填写到命令中

![image-20221002215643127](/Users/meizi/Library/Application Support/typora-user-images/image-20221002215643127.png)

3. 然后在`Typora`中插入图片，点击右键，上传图片。就可以把图片上传到`config.toml`中设置的图床了。

