# Manifest for building CrDroid 14.0 for gta4llte.

`gta4llte` is the codename for the LTE variant of the Samsung Galaxy Tab A7, with model SM-T505, and also with SM-T505N.

Some extremely basic instructions:
- Make a new directory for CrDroid sources and enter it:
```
mkdir crdroid-14.0
cd crdroid-14.0
```

- Initialize repo in this directory with the CrDroid 14.0 android repository:
```
repo init -u https://github.com/crdroidandroid/android.git -b 14.0 --git-lfs
```

- Clone this repository to .repo/local_manifests for roomservice.xml containing the repositories needed to build for these devices:
```
git clone https://github.com/mrx7014/gta4l-manifests.git -b crdroid-14.0_gta4l .repo/local_manifests
```

- Sync all of the repositories in manifests (including CrDroid manifests):
```
repo sync
```

- Finally, build as you like.
```
. build/envsetup.sh
lunch lineage_gta4l-eng
m bacon
```
