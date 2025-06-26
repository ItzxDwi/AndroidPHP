# 🐘 PHP Binaries for PocketMine-MP on Android

Run [PocketMine-MP](https://github.com/pmmp/PocketMine-MP) directly on your **Android device** using this pre-built PHP binary.  
- ✅ Works in **Termux**  
- ♻️ Auto-updated **every 48 hours**  
- 🛠 Built for **ARM64 devices**



## ✅ Requirements

- Android 64-bit device  
- [Termux (from F-Droid)](https://f-droid.org/en/packages/com.termux/)



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
**A:** Yes, as long as your device is 64-bit and you're using Termux from F-Droid.

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
You're likely using **Termux from the Google Play Store**, which doesn't support running native binaries.

✅ **Fix**:  Uninstall Termux and reinstall from [F-Droid](https://f-droid.org/en/packages/com.termux/) or [GitHub](https://github.com/termux/termux-app)

👉 More info:  [Reddit thread](https://www.reddit.com/r/termux/comments/1e05wjf/tried_to_execute_arm_assembly_on_s10/)

### ❌ `Permission denied` when running `php` or `start.sh`
✅ Fix:
Ensure the files have execute permissions:
```bash
chmod +x php
chmod +x start.sh
```

### ❌ `start.sh: ./bin/php7/bin/php: not found`
✅ Fix:
Ensure the PHP binary is correctly placed in this path:
```
~/server/bin/php7/bin/php
```

Made with ♥️
