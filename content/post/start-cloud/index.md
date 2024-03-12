---
title: 使用云服务器搭建个人网站
subtitle: 此前使用了 **Wowchemy** 的模板搭建个人网站，最近发现其删库了导致一系列问题，好在发现使用 **[Hugo Blox](https://hugoblox.com/)** 可以很好的解决。同时记录如何使用云服务器搭建个人网站并开放访问。

# Summary for listings and search engines
summary: 此前使用了 **Wowchemy** 的模板搭建个人网站，最近发现其删库了导致一系列问题，好在发现使用 **[Hugo Blox](https://hugoblox.com/)** 可以很好的解决。同时记录如何使用云服务器搭建个人网站并开放访问。

# Link this post with a project
projects: []

# Date published
date: '2024-20-27T00:00:00Z'

# Date updated
lastmod: '2024-20-27T00:00:00Z'

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: ''
  focal_point: ''
  placement: 
  preview_only: false

authors:
  - admin

tags:
  - Academic

categories:
  - 教程
---

## 安装 hugo 并通过公网访问

参考了[hugoblox](https://docs.hugoblox.com/getting-started/install-hugo/)的官方教程，注意云服务器镜像最好选择为**Ubuntu**，可以在配置环境时省去绝大多数麻烦。

使用snap安装依赖:

```bash
sudo snap install --classic go
sudo snap install --classic node
```

下载 Hugo Extended installer （注意要有 extend 的，以及如果后续出现报错，可以考虑降低下载的 version），如果下载速度慢，可以本地下载后直接传到服务器:

```bash
wget https://github.com/gohugoio/hugo/releases/download/v0.123.0/hugo_extended_0.123.0_linux-amd64.deb
sudo dpkg -i hugo_extended_0.123.0_linux-amd64.deb
```

遇到下载module失败的问题，要解决此问题，config/_defaults/module.yaml 中添加：

```yaml
proxy: https://goproxy.cn
```

随后在仓库路径下执行命令如下，其中 `--bind 0.0.0.0` 是将网页服务绑定到服务器的公网 IP 地址，以允许公网访问。

```bash
hugo server -D --bind 0.0.0.0
```

此时还不能通过公网访问，需要在云服务器商的控制台设置防火墙，根据上面命令的输出可以知道其实用的端口为 `1313`，所以在防火墙处添加规则，使得该端口能够被访问。
![png](index_0_0.png)


## 遇到的问题

如果使用 [HugoBlox](https://hugoblox.com/) ，hugo 一定要下载带 < \_extended\_ > 的。

如果使用的是 Wowchemy 模板，将 `./go.mod` 进行修改：

```yaml
替换 github.com/wowchemy/wowchemy-hugo-themes/modules/wowchemy/v5 v5.7.1-0.20221127215619-58b270a3e103 
为   github.com/HugoBlox/hugo-blox-builder/modules/blox-bootstrap/v5 v5.9.7
```

`./config/_defoult/config.yaml`中：
```
替换 github.com/wowchemy/wowchemy-hugo-themes/modules/wowchemy/v5
为   github.com/HugoBlox/hugo-blox-builder/modules/blox-bootstrap/v5
```

如果服务器出现 `__vsc_prompt_cmd_original: command not found` ，在 `~/.bashrc` 中添加 `unset PROMPT_COMMAND`。