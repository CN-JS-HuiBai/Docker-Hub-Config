该项目为小小的日记本-容器镜像平台的后端Docker-Compose文件，公开以便部署和查询。

该项目上游项目为：https://github.com/dqzboy/Docker-Proxy

小小的日记本-Docker-Hub开源镜像站业务正式上线，我们致力于以稳定，高速，高可用的开源镜像服务，助力国内企业云原生业务转型，你可以通过以下方式来获得开源镜像站的支持：

Podman配置镜像源：

```shell
vim /etc/containers/registries.conf
```

在文件中添加以下内容：

```yaml
[[registry]]
prefix = "docker.io"
location = "hub.littlediary.cn"
```

Docker配置镜像源

```shell
vim /etc/docker/daemon.json
```

在文件中添加以下内容

```json
{
	"registry-mirrors": ["https://hub.littlediary.cn/"]
}
```

配置完成之后重启docker服务：

```shell
systemctl restart docker
```

该加速站可提供10Gbps的满速带宽，三网访问我们会尽力优化。

2024年7月9日更新：为群晖NAS配置容器镜像：

打开群晖NAS的Container Manager，点击注册表

![这是图片](https://image.cloudyun.top/i/2024/07/10/xmpzfe.png "Magic Gardens")

点击设置按钮：选择你当前正在使用的Docker注册表，点击编辑按钮，在注册表镜像URL中填入：[https://v1.hub.littlediary.cn](https://v1.hub.littlediary.cn)

![这是图片](https://image.cloudyun.top/i/2024/07/10/xmqcs8.png "Magic Gardens")

点击应用按钮。

值得注意的一点是：我们并不建议在这里添加一个新的注册表，此种配置手段会导致无法正常使用镜像的搜索功能。建议优先选择将地址配置为原有注册表的镜像URL。

如果这个网站对你有用的话，可以稍微请我喝杯咖啡，谢谢（）
