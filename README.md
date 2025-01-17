# android_device_mtk6853
构建适用 OPPO-Realme  mtk6853处理器通用TWRP

## 特征

工作情况:

- adb
- fastbootd
- 部分 /data 解密
- 亮度
- 触摸

## 编译

First checkout minimal twrp with omnirom tree:

```
repo init --depth=1 -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-11 --groups=all,-notdefault,-device,-darwin,-x86,-mips

repo sync

|or|

repo sync --force-sync --no-clone-bundle --no-tags -j$(nproc --all)
```

Finally execute these:

```
export ALLOW_MISSING_DEPENDENCIES=true
. build/envsetup.sh
lunch twrp_MTK6853-eng
mka -j$(nproc --all) recoveryimage

|or|

export ALLOW_MISSING_DEPENDENCIES=true; source build/envsetup.sh; lunch twrp_mtk6853-eng; mka -j$(nproc --all) recoveryimage
```
