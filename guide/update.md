<img align="right" src="https://github.com/n00b69/woa-op6/blob/main/op6.png" width="350" alt="Windows 11 running on fajita/enchilada">

# Running Windows on the OnePlus 6 / 6T

## Updating drivers

### Prerequisites
- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

- [Modded TWRP](https://github.com/n00b69/woa-op6/releases/download/Files/TWRP-OP6xT.img)

- [Drivers](https://github.com/n00b69/woa-op6/releases/tag/Drivers)

- [UEFI image](https://github.com/n00b69/woa-op6/releases/tag/UEFI)

### Boot modified TWRP recovery
> Replace `path\to\twrp-op6xt.img` with the actual path of the TWRP image
```cmd
fastboot boot path\to\twrp-op6xt.img
```

#### Execute the msc script
> If it asks you to run it once again, do so
```cmd
adb shell msc
```

> [!Note]
> If you are facing issues (e.g your device does not enter mass storage mode), follow [the steps described in this guide](/guide/troubleshooting.md#mass-storage-mode-does-not-work) for alternative ways of entering mass storage mode.

### Diskpart
```cmd
diskpart
```

#### Select Windows volume
> Use `list volume` to find it, replace `$` with the actual number of **WINONEPLUS**
```cmd
select volume $
```

#### Assign the letter X
```cmd
assign letter x
```

#### Exit diskpart
```cmd
exit
```

### Installing Drivers
> [!Note]
> This process will take +- 20 minutes. Do not worry, this is normal.

- Unpack the driver archive, then open the `OfflineUpdater.cmd` file (if an error shows up, run `OfflineUpdaterFix.cmd` instead)

> If it asks you to enter a letter, enter the drive letter of **WINONEPLUS** (which should be **X**), then press enter

#### Reboot your device
> Make sure to also change the UEFI image in Android, otherwise you may face a "blue screen of death" (BSoD) when booting Windows later.

## Finished!











