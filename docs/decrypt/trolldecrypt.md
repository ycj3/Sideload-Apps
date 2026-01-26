### 手动安装 TrollDecrypt

#### 1. 在电脑上下载 .deb 安装包

- **下载地址**：[GitHub - TrollDecrypt Releases](https://github.com/donato-fiore/TrollDecrypt/releases) 。
- 你需要下载文件名包含 `iphoneos-arm64.deb` 的版本。

#### 2. 通过 SSH 把文件传输到手机

在电脑终端执行（假设你的文件在当前目录）：

```bash
scp -P 2222 com.fiore.trolldecrypt_1.2.1_iphoneos-arm64.deb root@127.0.0.1:/var/mobile/

```

#### 3. 在手机上强制安装

在电脑终端登录 SSH：

```bash
ssh -p 2222 root@127.0.0.1

```

进入手机后，运行以下安装命令：

```bash
# 安装 deb 包
dpkg -i com.fiore.trolldecrypt_1.2.1_iphoneos-arm64.deb

# 刷新图标缓存
uicache

```

#### 4. 开始砸壳

1. 此时你的手机桌面上会出现一个 **TrollDecrypt** 的图标。
2. 打开它，在列表中找到 **“<<目标APP>>”**。
3. 点击 **Decrypt**。
4. 成功后，它会提示你 IPA 文件的存放路径（通常在 `/var/mobile/Documents/TrollDecrypt/`）。

---

### 如何把砸好的 IPA 拿出来？

砸完壳后直接从电脑端取回：

```bash
# 在电脑终端执行，将 IPA 取回桌面
scp -P 2222 root@127.0.0.1:/var/mobile/Documents/TrollDecrypt/*.ipa ~/Desktop/

```
