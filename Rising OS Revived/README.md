# How to build unofficial Rising OS Revived

###   All of how to build ###

```bash
# Reference page 
https://github.com/RisingOS-Revived/android

```

### Sync ###

```bash
# Initialize local repository
repo init -u https://github.com/RisingOS-Revived/android -b sixteen --git-lfs

# Copy my custom manifest
mkdir -p .repo/local_manifests

touch .repo/local_manifests/<your device name>.xml

nano .repo/local_manifests/<your device name>.xml

# Sync
repo sync -c --no-clone-bundle --optimized-fetch --prune --force-sync -j$(nproc --all)

```

### Build ###

```bash

# Set up environment
. build/envsetup.sh

# Choose a target
riseup <your device name> userdebug

# Build 
rise b

# Check ROM files
ls -lh out/target/product/nabu | rg -n "zip|img"
```
