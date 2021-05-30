# SystemAppTemplate
This project is a template to create a system app for AOSP (for Android 11). It is based on the
[Updater](https://github.com/GrapheneOS/platform_packages_apps_Updater) app from GrapheneOS. Note
that this project has only been tested on GrapheneOS.

# Building
Ensure that you've built the AOSP project for your target device. Add the contents of this repo to
```~/android/grapheneos-11/packages/apps/SystemAppTemplate```

``` bash
cd ~/android/grapheneos-11
source script/envsetup.sh
choosecombo release aosp_sunfish userdebug
export OFFICIAL_BUILD=false
export OUT_DIR_COMMON_BASE=/media/lackshan/Output
cd packages/apps/SystemAppTemplate
mma -j16
cd ~/android/grapheneos-11
m -j16
```

# Flashing
```bash
cd /media/lackshan/Output/grapheneos-11/target/product/sunfish
export OUT_DIR_COMMON_BASE=/media/lackshan/Output
export ANDROID_PRODUCT_OUT=/media/lackshan/Output/grapheneos-11/target/product/sunfish
export PATH="/home/lackshan/Downloads/platform-tools_r31.0.2-linux/platform-tools:$PATH"
fastboot flashall -w
```
