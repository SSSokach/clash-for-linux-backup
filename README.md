# 项目介绍

此项目是自己用来备份[clash-for-linux-backup](https://github.com/Elegycloud/clash-for-linux-backup)，并对初始化启动脚本做了一点简单改动。如果感兴趣可以给原项目也点个星~


主要是为了解决我们在服务器上下载GitHub等一些国外资源速度慢的问题。

若有侵犯任何人的权利，请提交issues我会看到并删除仓库！

# 使用教程

## 下载项目



```bash
$ git clone git@github.com:SSSokach/clash-for-linux-backup.git
```

进入到项目目录，编辑`.env`文件，修改变量`CLASH_URL`的值。

```bash
$ cd clash-for-linux
$ vim .env
```

> **注意：** `.env` 文件中的变量 `CLASH_SECRET` 为自定义 Clash Secret，值为空时，脚本将自动生成随机字符串。

<br>

## 启动程序

- 运行启动脚本

```bash
$ bash init.sh

正在检测订阅地址...
Clash订阅地址可访问！                                      [  OK  ]

正在下载Clash配置文件...
配置文件config.yaml下载成功！                              [  OK  ]
```

- 启动与停止
```bash
$ bash start.sh   # tmux

$ source clash.sh
$ proxy_on

$ bash shutdown.sh
```

- 检查服务端口

```bash
$ netstat -tln | grep -E '9090|789.'
tcp        0      0 127.0.0.1:9090          0.0.0.0:*               LISTEN     
tcp6       0      0 :::7890                 :::*                    LISTEN     
tcp6       0      0 :::7891                 :::*                    LISTEN     
tcp6       0      0 :::7892                 :::*                    LISTEN
```

- 检查环境变量

```bash
$ env | grep -E 'http_proxy|https_proxy'
http_proxy=http://127.0.0.1:7890
https_proxy=http://127.0.0.1:7890
```

以上步鄹如果正常，说明服务clash程序启动成功，现在就可以体验高速下载github资源了。
