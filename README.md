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
repo init -u https://github.com/VoltageOS/manifest --git-lfs --depth 1 --branch voltage-16
```

3. Copy local_manifests folder from this repository to project directory
```
cd ~/symbiot-os
cp -r ~/symbiotos_advan_x1_manifest/local_manifests .repo/
```

4. Sync repository
```
cd ~/symbiot-os
repo sync --optimize --auto-gc
```

5. Start building
```
cd ~/symbiot-os
source build/envsetup.sh

# Creating certs
cd vendor/voltage-priv/keys 
bash ./make_key.sh
croot

# Apply Symbiot patchset
curl -L -o ./symbiot-patcher https://symbiotos.nenggala-project.id/file/symbiot-patcher
chmod +x ./symbiot-patcher
./symbiot-patcher --apply

# Build
brunch X1
```

## Related Resources
- [VoltageOS](https://github.com/VoltageOS)
- [Luminedroid Devices](https://github.com/LumineDroid-Devices)
- [ADA & ZANGEMANN: Sebuah Kisah tentang Perangkat Lunak, Skateboard, dan Es Krim Raspberry](https://lumbung.gimpscape.or.id/general/ada-and-zangemann/)
- Thanks for [Advan X1 Community](https://t.me/Advan_X1_chat)
