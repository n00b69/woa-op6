<img align="right" src="https://github.com/n00b69/woa-op6/blob/main/op6.png" width="350" alt="Windows 11 running on fajita/enchilada">

# Running Windows on the OnePlus 6 / 6T

## Uninstalling Windows

### Prerequisites
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Modified TWRP](https://github.com/n00b69/woa-op6/releases/download/Files/TWRP-OP6xT.img)

### Switch to Android
> Or your device will not boot into Android after uninstalling Windows
- Run the **Switch to Android** or **Android** shortcut on your desktop, or flash a **boot.img** backup in fastboot/recovery.

### Boot the modified recovery
> While in fastboot mode, replace `path\to\twrp.img` with the actual path of the image
```cmd
fastboot boot path\to\twrp.img
```

### Execute the restore script
```cmd
adb shell restore
```

## Finished!
















