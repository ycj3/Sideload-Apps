# 📱 SideStore 安装与使用简洁指南（适用于 macOS + iOS）

## ✅ 前提条件

- 一台运行 macOS 10.15 或更高版本的 Mac
- 一部运行 iOS/iPadOS 14 或更高版本的设备
- 一个 Apple ID
- 稳定的网络连接

---

## 🧰 所需文件下载

在电脑上下载以下工具：

- [AltServer](https://cdn.altstore.io/file/altstore/altserver.zip)
- [SideStore.ipa](https://github.com/sidestore/sidestore/releases/latest/download/sidestore.ipa)
- [JitterbugPair](https://github.com/osy/Jitterbug/releases/download/v1.3.1/jitterbugpair-macos.zip)
- [StosVPN](https://apps.apple.com/us/app/stosvpn/id6744003051)

---

## 🧩 安装步骤

### 1. 安装 AltServer

1. 解压 `AltServer.zip`
2. 拖动 `AltServer.app` 到 **应用程序** 文件夹
   <img width="1254" height="493" alt="image" src="https://github.com/user-attachments/assets/286cc7f2-00a5-435b-8f0c-e729a441718d" />
   
3. 右键点击并选择“打开”以绕过安全提示
   <img width="1440" height="482" alt="image" src="https://github.com/user-attachments/assets/1053341b-9f41-4265-b913-0ff8330442e3" />


---

### 2. 安装 SideStore

1. 用数据线连接设备
2. 如有提示，点击“信任此电脑”并输入设备密码
3. 启动 AltServer，**按住 Option 键**，点击顶部菜单栏中的 AltServer 图标 → 选择 **Sideload .ipa**
   <img width="786" height="484" alt="image" src="https://github.com/user-attachments/assets/a1bed0bd-f3e5-46e1-8d61-43fc5653a1f3" />
4. 选择下载的 `SideStore.ipa`，按提示安装
5. 设备中进入：**设置 > 通用 > VPN 与设备管理** → 点击信任 Apple ID 开发者应用
6. 如果是 iOS/iPadOS 16 或更高版本：
   - 打开设置 → 隐私与安全性 → 启用开发者模式（Developer Mode）

---

### 3. 配对设备

1. 解压 `JitterbugPair.zip`
2. 运行 JitterbugPair（确保设备保持连接且在主屏幕）
3. 会生成一个 `.mobiledevicepairing` 文件
4. 压缩该文件为 `.zip` 并通过邮件或网盘传输到设备
5. 在 **文件 App** 中长按压缩包 → 解压
6. 打开 SideStore 应用 → 选择解压出的配对文件
   > 如果找不到 SideStore 应用，请重启设备

---

### 4. 安装与启用 StosVPN

1. 在设备上通过 App Store 下载并安装 StosVPN
2. 启用 VPN 配置（**每次使用 SideStore 都需开启**）
   > StosVPN 不连接外网，仅用于本机通信以支持自动刷新

---

### 5. 登录并刷新 SideStore

1. 打开 SideStore，使用安装时的 Apple ID 登录
2. 进入 “Apps” 标签页 → 点击绿色天数或 “Refresh All” 进行刷新
   > 每次重新安装 SideStore 后必须刷新，否则可能导致应用提前过期

---

https://github.com/user-attachments/assets/c1cdfb08-6530-40f7-8123-6251892898e8

## 🚀 安装应用

- 在 “Sources” 中添加源，在 “Browse” 页面浏览并安装
- 在 “Apps” 中点击 `+` 号，从设备导入 `.ipa` 文件并安装

---

## 🔁 应用过期与刷新说明

- 应用过期后不可打开，需刷新才能恢复使用
- 若 SideStore 过期：请重新执行安装步骤 **（无需卸载 SideStore）**
- 若其他应用过期：直接在 SideStore 中刷新即可

---

## 🆘 技术支持

如遇问题，可以直接提 issue，来获取帮助
