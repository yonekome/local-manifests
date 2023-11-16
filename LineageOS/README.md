# How to build unofficial Pixel Experience

###   All of how to build ###

```bash
# Reference page
https://wiki.lineageos.org/devices/

```

### Sync ###

```bash
# Initialize local repository
repo init -u https://github.com/LineageOS/android.git -b lineage-21.0 --git-lfs

# Copy my custom manifest
mkdir -p .repo/local_manifests

touch .repo/local_manifests/<your device name>.xml

vi .repo/local_manifests/<your device name>.xml

# Sync
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags

```

### Build ###

```bash

# Set up environment
. build/envsetup.sh

# Choose a target
lunch aosp_<your device name>-userdebug

# Build the code
croot

mka bacon -j$(nproc --all)
```

