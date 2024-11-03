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
> Use `print all` to make sure that partition 19 is Windows
```sh
rm 19
```

#### Delete ESP Partition
> Use `print all` to make sure that partition 18 is ESP
```sh
rm 18
```

#### Resize userdata Partition
> Use `print all` to make sure that partition 17 is userdata
>
> Replace **125GB** with the end value of your disk, use `p free` to find it
```sh
resizepart 17
125GB
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
















