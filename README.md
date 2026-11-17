# NanoPi R4S 精简 OpenWrt

使用官方 OpenWrt v25.12.6 源码，为 NanoPi R4S 4GB LPDDR4 构建精简固件，包含基本路由功能、LuCI 和简体中文翻译。根分区设置为 2048 MiB，镜像还包含启动分区和对齐空间，因此存储卡容量必须大于 2 GiB。

## 编译和下载

1. 打开仓库的 Actions，首次使用时启用工作流。
2. 选择 **OpenWrt R4S minimal**，点击 **Run workflow**。
3. 编译成功后，从该次运行的 Artifacts 下载 `openwrt-25.12.6-r4s`，校验 SHA256 后使用其中的 squashfs 镜像。

工作流使用 GitHub 托管的 Ubuntu runner，并不使用本仓库原有的 ImmortalWrt 配置、自定义插件或自托管 runner。官方源码标签固定为 v25.12.6；feeds 使用该版本默认的维护分支。原来的 Docker 工作流及其配置仍保留，但与此固件无关。

首次刷写会覆盖目标存储卡数据；先备份并确认写入设备。跨发行版升级时不要直接沿用旧配置。默认管理地址为 `192.168.1.1`，首次登录后请设置 root 密码。

## 鸣谢

本仓库 Fork 自 [xuanranran/OpenWrt_RockChip](https://github.com/xuanranran/OpenWrt_RockChip)。感谢 [OpenWrt](https://openwrt.org/)、[ImmortalWrt](https://github.com/immortalwrt/immortalwrt)、Lean's OpenWrt、P3TERX / Actions-OpenWrt 和 SuLingGG / OpenWrt-Rpi。
