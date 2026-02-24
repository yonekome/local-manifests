# How to build Project Infinity X

###   All of how to build ###

```bash
# Reference page 
https://github.com/ProjectInfinity-X/manifest

```

### Sync ###

```bash
# Initialize local repository
repo init --no-repo-verify --git-lfs -u https://github.com/ProjectInfinity-X/manifest -b 16 -g default,-mips,-darwin,-notdefault

# Copy my custom manifest
mkdir -p .repo/local_manifests

touch .repo/local_manifests/<your device name>.xml

nano .repo/local_manifests/<your device name>.xml

# Sync
repo sync -c --no-clone-bundle --no-tags --optimized-fetch --prune --force-sync -j$(nproc --all)

```

### Build ###

```bash

# Set up environment
. build/envsetup.sh

# Choose a target
lunch infinity_<your device name>-userdebug

# Build 
m bacon -j$(nproc --all)
