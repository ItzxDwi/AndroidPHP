# PHP binaries for PocketMine-MP on Android.
Introducing an automatically updated PHP binaries for [PocketMine-MP](https://github.com/pmmp/PocketMine-MP) on [Android](https://en.m.wikipedia.org/wiki/Android_(operating_system)).
Updated every 12 hours.

## Requirements

- Termux (download from [F-Droid](https://f-droid.org/en/packages/com.termux/))
- PHP binary file (provided below)

## Installation

1. **Open Termux** and install wget:
```bash
pkg install wget
```

2. **Create server directory**:
```bash
mkdir server
cd server
mkdir -p bin/php7/bin
cd bin/php7/bin
```

3. **Download PHP binary**:
```bash
wget https://github.com/ItzxDwi/AndroidPHP/releases/download/Latest/php
chmod +x php
```

4. **Download PocketMine-MP**:
```bash
cd ~/server
wget https://github.com/pmmp/PocketMine-MP/releases/latest/download/PocketMine-MP.phar
wget https://github.com/pmmp/PocketMine-MP/releases/latest/download/start.sh
chmod +x start.sh
```

5. **Start the server**:
```bash
bash start.sh
```


That's it! Now your server should run correctly.

## FAQ (Frequently Asked Questions)

### Q: Can I run this on any Android device?

**A:** Yes, as long as your device's operating system is 64-bit.

### Q: How do I update the PHP Binary?

**A:** Run the following commands:
```bash
cd server/bin/php7/bin
rm php
wget https://github.com/ItzxDwi/AndroidPHP/releases/download/Latest/php
chmod +x php
```

### Q: How do I update the PocketMine-MP?

**A:** Run the following commands:
```bash
cd server
rm PocketMine-MP.phar
wget https://github.com/pmmp/PocketMine-MP/releases/latest/download/PocketMine-MP.phar
```

## Common Troubleshooting

### Problem: ```error: "/data/data/com.termux/files/home/server/bin/php7/bin/php" has unexpected e_type: 2```

**Solution:**  
You're likely using the Google Play version of Termux, which no longer supports running static binaries.

1. **Uninstall** the Termux version installed from Google Play.
2. **Reinstall Termux** from [F-Droid](https://f-droid.org/en/packages/com.termux/) or [Github](https://github.com/termux/termux-app).

More details:
https://www.reddit.com/r/termux/comments/1e05wjf/tried_to_execute_arm_assembly_on_s10/

### Problem: Permission denied when running php or start.sh

**Solution:**  
Ensure the files have execute permissions:
```bash
chmod +x php
chmod +x start.sh
```

### Problem: start.sh: line X: ./bin/php7/bin/php: not found

**Solution:**  
This means either the php binary is missing, not named correctly, or not placed in the correct directory. Make sure the path is:

```server/bin/php7/bin/php```


