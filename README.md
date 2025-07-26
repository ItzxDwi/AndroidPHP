# 🐘 PHP Binaries for PocketMine-MP on Android

[![Build PHP Binaries](https://github.com/ItzxDwi/AndroidPHP/actions/workflows/main.yml/badge.svg)](https://github.com/ItzxDwi/AndroidPHP/actions/workflows/main.yml)
[![CI](https://github.com/ItzxDwi/AndroidPHP/actions/workflows/ci.yml/badge.svg)](https://github.com/ItzxDwi/AndroidPHP/actions/workflows/ci.yml)

Run [PocketMine-MP](https://github.com/pmmp/PocketMine-MP) on your **Android device** using this pre-built PHP binary.  
- ✅ Works in **Termux**  
- ♻️ Auto-updated **every 48 hours**  
- 🛠 Built for **ARM64 devices**

## ✅ Requirements

- Android 64-bit device  
- Termux

## 🚀 Installation

### 1. Install Termux and curl
```bash
pkg install curl
```

### 2. Create your server folder
```bash
mkdir -p ~/server/bin/php7/bin
cd ~/server/bin/php7/bin
```

### 3. Download the PHP binary
```bash
curl -L -O https://github.com/ItzxDwi/AndroidPHP/releases/latest/download/php
chmod +x php
```

### 4. Download PocketMine-MP
```bash
cd ~/server
curl -L -O https://github.com/pmmp/PocketMine-MP/releases/latest/download/PocketMine-MP.phar
curl -L -O https://github.com/pmmp/PocketMine-MP/releases/latest/download/start.sh
chmod +x start.sh
```

### 5. Start the server
```bash
bash start.sh
```

## ❓ FAQ (Frequently Asked Questions)

### Q: Can I run this on any Android device?
**A:** Yes, as long as your device is 64-bit

### Q: How do I update the PHP binary?
```bash
cd ~/server/bin/php7/bin
rm php
curl -L -O https://github.com/ItzxDwi/AndroidPHP/releases/latest/download/php
chmod +x php
```

### Q: How do I update PocketMine-MP?
```bash
cd ~/server
rm PocketMine-MP.phar
curl -L -O https://github.com/pmmp/PocketMine-MP/releases/latest/download/PocketMine-MP.phar
```

## 🛠 Common Troubleshooting

### ❌ Error: `has unexpected e_type: 2`
You're likely using **Termux from Google Play Store**, which doesn't support running native binaries.

✅ **Fix**:  Uninstall Termux and reinstall  it from [F-Droid](https://f-droid.org/en/packages/com.termux/) or [GitHub](https://github.com/termux/termux-app)

👉 More info:  [Reddit thread](https://www.reddit.com/r/termux/comments/1e05wjf/tried_to_execute_arm_assembly_on_s10/)

### ❌ `Permission denied` when running `php` or `start.sh`
✅ Fix:
Make sure that the files have the right permissions:
```bash
chmod +x php
chmod +x start.sh
```

### ❌ `start.sh: ./bin/php7/bin/php: not found`
✅ Fix:
Make sure that the PHP binary is correctly placed in this path:
```
~/server/bin/php7/bin/php
```

Made with ♥️
