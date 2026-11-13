# 鹰眼 HUD（元境版）

在车机**副屏（1000×400）**上叠一张极简导航图：黑底 + 白色路网 + 绿色路线 + 车头永远朝上。

> ⚠️ 前提：车机自带**元境导航**（`com.baic.icc.bmap`），并且能进工程模式打开 ADB。
> 没有元境的车，装上去只有白色路网，**画不出绿色路线**。

---

## 下载

安装包 38MB（Windows / macOS 通用，解压即用）：

| 线路 | 链接 |
|---|---|
| **镜像 1（推荐）** | https://ghproxy.net/https://github.com/SilasMead/eagle3-maps/releases/download/app-v1/Eagle3HUD-Installer.zip |
| 镜像 2 | https://gh-proxy.com/https://github.com/SilasMead/eagle3-maps/releases/download/app-v1/Eagle3HUD-Installer.zip |
| GitHub 原始 | https://github.com/SilasMead/eagle3-maps/releases/download/app-v1/Eagle3HUD-Installer.zip |

国内直连 GitHub 的下载域名经常超时，**优先用镜像 1**。

---

## 安装

1. 车机进工程模式，打开 ADB（**每台车的密码不同，请车主自己输入**）
2. 电脑连上车机的 WiFi 热点
3. 解压安装包，双击：
   - Windows：`install-win.bat`
   - macOS：`install-mac.command`（首次被拦 → 右键 → 打开）
4. 等它自己跑完，看到 `Done.` / 「安装完成」即可

安装器会自动做：扫网段找车机 → 拿 root → 部署注入组件 → 装 APK → 授权定位 → 按 GPS 下载本省路网 → 启动。

---

## 离线地图包（白路网）

全国 **33 个省级包**（含港澳，共 858MB）就在本仓库 Releases：

```
https://github.com/SilasMead/eagle3-maps/releases/download/v1/roads-<省份拼音>.bin
```

**不需要你手动下载**——安装器读车机 GPS 判断省份，自己下、自己推。三个镜像按顺序试，全失败也不影响使用（只有绿线 + 车标）。

省份拼音：`beijing` `tianjin` `hebei` `shanxi` `neimenggu` `liaoning` `jilin` `heilongjiang`
`shanghai` `jiangsu` `zhejiang` `anhui` `fujian` `jiangxi` `shandong` `henan` `hubei` `hunan`
`guangdong` `guangxi` `hainan` `chongqing` `sichuan` `guizhou` `yunnan` `xizang` `shaanxi`
`gansu` `qinghai` `ningxia` `xinjiang` `hongkong` `macau`

---

## 常见问题

**副屏一直「等待 GPS」** → 定位权限被车机重置了。跑安装包里的 `修复-等待GPS`（Mac/Win 各一份）。

**绿线只显示一小截** → 元境在导航那一刻才产生路线，注入没赶上。退出导航重新规划一次。

**重启后 ADB 又关了** → 默认每次重启都要手动开一次 ADB。想让 ADB 开机自启要改系统分区，风险自负，详见安装包内 `安装教程.md` 第 7 节。

---

## 说明

- 本工具只做**显示层**，不碰车辆任何控制逻辑。
- 路线数据来自元境导航，准确性以原车导航为准。
- 工程模式密码由车主本人保管，本仓库不包含、不记录。
