---
title: Debian安装最新版Nginx
date: 2022-09-04 14:37:53
tags:
---
## 安装先决条件

```
sudo apt install curl gnupg2 ca-certificates lsb-release debian-archive-keyring
```

## 导入 Nginx 签名密钥

```
curl https://nginx.org/keys/nginx_signing.key | gpg --dearmor \
    | sudo tee /usr/share/keyrings/nginx-archive-keyring.gpg >/dev/nul
```

## 设置 apt 存储库

```
echo "deb [signed-by=/usr/share/keyrings/nginx-archive-keyring.gpg] \
http://nginx.org/packages/mainline/debian `lsb_release -cs` nginx" \
    | sudo tee /etc/apt/sources.list.d/nginx.list
```

## 安装 Nginx

```
sudo apt update
sudo apt install nginx
```
