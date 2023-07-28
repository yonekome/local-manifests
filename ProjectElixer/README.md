# How to build Project Elixir

### Sync ###

```bash
# Initialize local repository
repo init -u https://github.com/Project-Elixir/manifest -b Tiramisu

# Copy my custom manifest
mkdir -p .repo/local_manifests

touch .repo/local_manifests/<device name>.xml

vi .repo/local_manifests/<device name>.xml

# Sync
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags

```

### Build ###

```bash

# Set up environment
. build/envsetup.sh

# Choose a target
lunch aosp_<device name>-userdebug

# Build the code
mka bacon 
```
