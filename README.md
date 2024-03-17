# Manifest for building LineageOS 21.0 for a23.

`a23` is the codename for the 4G variant of the Samsung A23, with model SM-A235F, SM-A235M and also with SM-A235N.

Some extremely basic instructions:
- Make a new directory for Lineage sources and enter it:
```
mkdir lineage-21.0
cd lineage-21.0
```

- Initialize repo in this directory with the LineageOS 21.0 android repository:
```
repo init -u https://github.com/LineageOS/android.git -b lineage-21.0 --git-lfs
```

- Clone this repository to .repo/local_manifests for roomservice.xml containing the repositories needed to build for these devices:
```
git clone https://github.com/mrx7014/local_manifest.git -b lineage-21.0_a23 .repo/local_manifests
```

- Sync all of the repositories in manifests (including LineageOS manifests):
```
repo sync
```

- Finally, build as you like.
```
. build/envsetup.sh
lunch lineage_a23-eng
mka otapackage
```
