# SymbiotOS Manifest Build for Advan X1

## Building

1. Clone this repository
```
cd ~/
git clone --branch symbiot-16 https://github.com/nenggala-project/symbiotos_advan_x1_manifest symbiotos_advan_x1_manifest
```

2. Init the project
```
mkdir ~/symbiot-os
cd ~/symbiot-os
repo init -u https://github.com/VoltageOS/manifests --git-lfs --depth 1 --branch voltage-16
```

3. Copy local_manifests folder from this repository to project directory
```
cd ~/symbiot-os
cp -r ~/symbiotos_advan_x1_manifest/local_manifests .repo/
```

4. Sync repository
```
repo sync --optimize --auto-gc
```

5. Start building
```
source build/envsetup.sh
brunch X1
```
