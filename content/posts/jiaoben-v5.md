---
title: "jiaoben v5.0 一键脚本发布"
date: 2026-06-08T16:00:00+08:00
tags: ["脚本", "VLESS", "Hysteria2", "Argo"]
categories: ["工具"]
summary: "支持 REALITY、Argo 隧道、Hysteria2 三种协议的一键部署脚本。"
---

## 功能特性

- **REALITY (VLESS)** — 端口 443，高性能抗封锁
- **Argo 隧道** — 无需暴露真实 IP，通过 Cloudflare 隧道
- **Hysteria2** — 基于 QUIC，低延迟，支持端口跳跃
- **Systemd 管理** — 开机自启、故障自动恢复
- **SHA256 校验** — 下载组件自动验证完整性

## 一键部署

```bash
bash <(curl -fsSL https://raw.githubusercontent.com/fireflies1145/jiaoben/main/run.sh)
```

## 菜单

```
1. 部署 REALITY (VLESS)       — 端口 443，高性能
2. 部署 Argo 隧道 (VLESS)     — 无需暴露真实 IP
3. 部署 Hysteria2             — 基于 QUIC，低延迟
4. 一键部署全部
5. 查看节点信息
6. 停止/重启服务
7. 彻底卸载
0. 退出
```

## 服务管理

```bash
systemctl status jiaoben-xray    # REALITY
systemctl status jiaoben-hy2     # Hysteria2
systemctl status jiaoben-argo    # Argo 隧道
journalctl -u jiaoben-xray -n 50 # 查看日志
```

## 项目地址

[GitHub - fireflies1145/jiaoben](https://github.com/fireflies1145/jiaoben)
