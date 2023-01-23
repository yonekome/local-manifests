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

# Clone my custom manifest
git clone -b tiramisu https://github.com/nattolecats/local_manifests .repo/local_manifests

# Sync
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags

```

### Build ###

```bash

# Set up environment
. build/envsetup.sh

# Choose a target
lunch evolution_denniz-userdebug

# Build the code
m evolution
```
