Getting started with NusantaraProject
====================

![NusantaraProject](https://github.com/NusantaraProject-ROM/Nusantara/blob/master/goodies/banner.png?raw=true)

You'll need to get
familiar with [Git and Repo](https://source.android.com/setup/build/downloading).

### Create a directory ###
```bash
 mkdir -p ~/rom/nad
 cd ~/rom/nad

```

### Sync ###
#### Initialize local repository ####
To sync with full history use:
```bash
repo init -u https://github.com/Nusantara-Fan-Edition/android_manifest -b 10 --git-lfs
```

To save space, sync without history use:
```bash
repo init --depth=1 -u https://github.com/Nusantara-Fan-Edition/android_manifest -b 10 --git-lfs
```

#### Sync ####
```bash
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

### Build ###
#### Set up environment ####
```bash
. build/envsetup.sh
```

#### Choose a target ####
```bash
lunch nad_$device-userdebug
```

#### Build the code ####
```bash
mka nad -j$(nproc --all)
```
