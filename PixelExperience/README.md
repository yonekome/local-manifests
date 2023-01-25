# How to build unofficial Pixel Experience

###   All of how to build ###

```bash
# Reference page 
https://wiki.pixelexperience.org/help/building/

```

### Sync ###

```bash
# Initialize local repository
repo init -u https://github.com/PixelExperience/manifest -b thirteen

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

### Note ###

```bash

I did not set ccache because an error occurred when I set ccache in my environment and I could not build.

```
