<img align="right" src="https://github.com/n00b69/woa-op6/blob/main/op6.png" width="350" alt="Windows 11 running on fajita/enchilada">

# Running Windows on the OnePlus 6 / 6T

## Uninstalling Windows

### Prerequisites
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Modified TWRP](https://github.com/n00b69/woa-op6/releases/download/Files/TWRP-OP6xT.img)

### Opening CMD as an admin
> Download **platform-tools** and extract the folder somewhere, then open CMD as an **administrator**.
>
> It is recommended to keep this window open and use it throughout the entire guide.
> 
> Replace `path\to\platform-tools` with the actual path to the platform-tools folder, for example **C:\platform-tools**.
```cmd
cd path\to\platform-tools
```

### Boot the modified recovery
> While in fastboot mode, replace `path\to\twrp.img` with the actual path of the image
```cmd
fastboot boot path\to\twrp.img
```

#### Unmount data
```cmd
adb shell umount /dev/block/by-name/userdata
```

### Run parted
```cmd
adb shell parted /dev/block/sda
```

#### Delete Windows Partition
> Use `print all` to make sure that partition 36 is Windows
```sh
rm 36
```

#### Delete ESP Partition
> Use `print all` to make sure that partition 35 is ESP
```sh
rm 35
```

#### Resize userdata Partition
> Use `print all` to make sure that partition 34 is userdata
>
> Replace **127GB** with the end value of your disk, use `p free` to find it
```sh
resizepart 34
127GB
```

#### Exit Parted
```sh
quit
```

### Format data
- Go to the Wipe menu in TWRP and press Format Data, then type `yes`

#### Check if Android boots
- Reboot your device and check if Android boots.

## Finished!
















