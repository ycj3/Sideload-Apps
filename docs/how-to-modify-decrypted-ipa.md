## **如何修改 已砸壳的 IPA（Decrypted IPA）的 Bundle Identifier 和 App Name**

本文将详细介绍如何修改已解密的 IPA 文件，包括更改 **bundle identifier** 和 **app name**。这些修改能够帮助你顺利地通过 **AltStore** 或 **SideStore** 安装修改后的 App。

---

### **目录**

1. [前期准备](#前期准备)
2. [修改 Bundle Identifier 和 App Name](#修改-bundle-identifier-和-app-name)
3. [常见问题与解决方案](#常见问题与解决方案)
4. [如何通过 AltStore 或 SideStore 安装修改后的 IPA](#如何通过-altstore-或-sidestore-安装修改后的-ipa)
5. [总结](#总结)

---

### **1. 前期准备**

在开始修改 IPA 文件之前，我们需要准备一些工具和文件：

- **已解密的 IPA 文件**：确保你拥有目标应用的 decrypted IPA。

  ```
  otool -l WeChat | grep cryptid
  ```

  `cryptid 0` 已砸，`cryptid 1` 加密

- **macOS 或 Windows 环境**：推荐使用 macOS 或 Windows 来操作，必要时安装适当的工具。
- **AltStore 或 SideStore**：用于安装修改后的应用。

---

### **2. 修改 Bundle Identifier 和 App Name**

#### **2.1 提取 IPA 文件**

首先，你需要将 IPA 文件解压以访问其内部文件。可以通过以下步骤进行：

1. **解压 IPA 文件**：

   - 将 `.ipa` 文件的扩展名改为 `.zip`。
   - 使用解压工具（如 macOS 的归档实用工具或 Windows 的解压软件）解压该文件。

   解压后，你将看到应用的文件结构，如下所示：

   ```
   Payload/
   └── AppName.app/
       ├── Info.plist
       ├── AppExecutable
       ├── Assets/
       └── ...
   ```

#### **2.2 修改 Bundle Identifier**

1. 打开 `AppName.app/Info.plist` 文件。你可以使用任何文本编辑器（如 **Sublime Text** 或 **Visual Studio Code**）来编辑此文件。

2. 找到 `CFBundleIdentifier` 键。它的值看起来像这样：

   ```xml
   <key>CFBundleIdentifier</key>
   <string>com.example.appname</string>
   ```

3. 将该值修改为你需要的新 **bundle identifier**，例如：

   ```xml
   <key>CFBundleIdentifier</key>
   <string>com.new.identifier.appname</string>
   ```

#### **2.3 修改 App Name**

1. 在同一 `Info.plist` 文件中，找到 `CFBundleDisplayName` 键，它代表了应用的显示名称：

   ```xml
   <key>CFBundleDisplayName</key>
   <string>AppName</string>
   ```

2. 将其值修改为你想要的 **app name**，例如：

   ```xml
   <key>CFBundleDisplayName</key>
   <string>NewAppName</string>
   ```

#### **2.4 精简 IPA**

```
cd Payload/AppName.app

rm -rf Watch
rm -rf PlugIns
rm -rf com.apple.WatchPlaceholder

```

#### **2.5 保存修改并打包**

- 保存对 `Info.plist` 文件所做的修改。
- 将文件夹重新打包成 `.ipa` 文件。你可以使用命令行工具 `zip` 来完成这一步。

例如，使用命令行重新打包：

```bash
zip -r NewAppName.ipa Payload
```

---

### **3. 常见问题与解决方案**

在修改过程中，你可能会遇到以下问题：

#### **问题 1：IPA 无法安装**

```
The operation couldn’t be completed. Unable to install the app: Invalid value of WKCompanionAppBundleIdentifier key in WatchKit 2.0 app's Info.plist: com.tencent.xin (expected xxx)
```

- **原因**：可能是 WKCompanionAppBundleIdentifier 对应的 bundle **bundle identifier** 和主 App 的**bundle identifier** 不匹配。
- **解决方案**： 如步骤 2.4 提到的操作，执行 `rm -rf com.apple.WatchPlaceholder`。

---

### **4. 通过 AltStore 或 SideStore 安装修改后的 IPA**
