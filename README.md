Getting started with NusantaraProject
====================

![NusantaraProject](https://github.com/NusantaraProject-ROM/Nusantara/blob/master/goodies/banner.png?raw=true)

You'll need to get
familiar with [Git and Repo](https://source.android.com/setup/build/downloading).

 Configure git
 Given that repo requires you to identify yourself to sync Android, run the following commands to configure your git identity:
 
 -----------------------------------------------------

    git config --global user.email "you@example.com"
    git config --global user.name "Your Name"

-----------------------------------------------------

Turn on caching to speed up build
Make use of ccache if you want to speed up subsequent builds by running:

    export USE_CCACHE=1
    export CCACHE_EXEC=/usr/bin/ccache

-----------------------------------------------------

and adding that line to your ~/.bashrc file. Then, specify the maximum amount of disk space you want ccache to use by typing this:

    ccache -M 50G

-----------------------------------------------------

Due to their size, some repos are configured for lfs or Large File Storage. To make sure your distribution is prepared for this, run:

    git lfs install

-----------------------------------------------------

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
