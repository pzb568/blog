---
title: 安卓系统利用termux下载种子文件
tags:
  - 下载
  - 种子
  - 磁力链接
  - transmission
  - Tremotesf
  - peerflix-server
categories:
  - 工具应用
comments: true
mathjax: false
abbrlink: 486160a8
date: 2020-04-16 22:54:53
---
# transmission

## 1. termux里安装transmission

```
pkg install transmission
```
## 2. 启动transmission
```
transmission-daemon -T
```
## 下载管理器
### 网页管理器 
transmission GUI

<http://localhost:9091/transmission/web/>

## Tremotesf
软件直接谷歌市场下载
需要修改/data/data/com.termux/files/home/.config/transmission-daemon中settings.json文件
>按照下图修改用户名和密码按照自己的设置，其他设置如下一样。

<escape><!-- more --></escape>
```
{
    "alt-speed-down": 50,
    "alt-speed-enabled": false,
    "alt-speed-time-begin": 540,
    "alt-speed-time-day": 127,
    "alt-speed-time-enabled": false,
    "alt-speed-time-end": 1020,
    "alt-speed-up": 50,
    "bind-address-ipv4": "0.0.0.0",
    "bind-address-ipv6": "::",
    "blocklist-enabled": false,
    "blocklist-url": "http://www.example.com/blocklist",
    "cache-size-mb": 2,
    "dht-enabled": true,
    "download-dir": "/data/data/com.termux/files/home/Downloads",
    "download-queue-enabled": true,
    "download-queue-size": 5,
    "encryption": 0,
    "idle-seeding-limit": 30,
    "idle-seeding-limit-enabled": false,
    "incomplete-dir": "/data/data/com.termux/files/home/Downloads",
    "incomplete-dir-enabled": false,
    "lpd-enabled": false,
    "message-level": 2,
    "peer-congestion-algorithm": "",
    "peer-id-ttl-hours": 6,
    "peer-limit-global": 200,
    "peer-limit-per-torrent": 50,
    "peer-port": 51413,
    "peer-port-random-high": 65535,
    "peer-port-random-low": 49152,
    "peer-port-random-on-start": false,
    "peer-socket-tos": "default",
    "pex-enabled": true,
    "port-forwarding-enabled": true,
    "preallocation": 1,
    "prefetch-enabled": false,
    "queue-stalled-enabled": true,
    "queue-stalled-minutes": 30,
    "ratio-limit": 2,
    "ratio-limit-enabled": false,
    "rename-partial-files": true,
    "rpc-authentication-required": false,
    "rpc-bind-address": "0.0.0.0",
    "rpc-enabled": true,
    "rpc-host-whitelist": "",
    "rpc-host-whitelist-enabled": true,
    "rpc-password": "{15ad59fc485380ee27c627519aac2ada787ea05734lHrHNa", ## 这里修改密码
    "rpc-port": 9091,
    "rpc-url": "/transmission/",
    "rpc-username": "termux", ## 这里修改用户名
    "rpc-whitelist": "*",
    "rpc-whitelist-enabled": false,
    "scrape-paused-torrents-enabled": true,
    "script-torrent-done-enabled": false,
    "script-torrent-done-filename": "",
    "seed-queue-enabled": false,
    "seed-queue-size": 10,
    "speed-limit-down": 100,
    "speed-limit-down-enabled": false,
    "speed-limit-up": 100,
    "speed-limit-up-enabled": false,
    "start-added-torrents": true,
    "trash-original-torrent-files": false,
    "umask": 18,
    "upload-slots-per-torrent": 14,
    "utp-enabled": true
}
```
Tremotesf配置如下图
![](https://ftp.bmp.ovh/imgs/2020/04/f75db9e7ce757e66.jpg)

# peerflix-server

## 安卓termux
```
pkg install nodejs
```
## centos
```

yum insatll nodejs
```
## debian/ubuntu
```
apt install nodejs
```
## 安装服务
```
npm install -g peerflix-server
```
## 启动
```
peerflix-server
```
## 配置
配置文件目录：~/.config/peerflix-server/config.json

配置示例：https://github.com/mafintosh/torrent-stream#full-api

```
{
  "connections": 100,
  "tracker": true,
  "verify": true,
  "uploads": 10,
  "trackers": [
      "udp://tracker.coppersurfer.tk:6969/announce",
    "udp://9.rarbg.to:2710/announce",
    "udp://9.rarbg.me:2710/announce",
    "udp://tracker.leechers-paradise.org:6969/announce",
    "udp://tracker.opentrackr.org:1337/announce",
    "udp://tracker.internetwarriors.net:1337/announce",
    "udp://tracker.openbittorrent.com:80/announce",
    "udp://exodus.desync.com:6969/announce",
    "udp://retracker.lanta-net.ru:2710/announce",
    "udp://tracker.tiny-vps.com:6969/announce",
    "udp://open.demonii.si:1337/announce",
    "udp://bt.xxx-tracker.com:2710/announce",
    "udp://open.stealth.si:80/announce",
    "udp://tracker.torrent.eu.org:451/announce",
    "udp://torrentclub.tech:6969/announce",
    "udp://tracker.cyberia.is:6969/announce",
    "udp://denis.stalker.upeer.me:6969/announce",
    "udp://tracker.moeking.me:6969/announce",
    "udp://explodie.org:6969/announce",
    "udp://opentor.org:2710/announce"
  ],
   "dht": true, 
   "path": "/root/Downloads"
}
```
## 管理器

<http://localhost:9000>