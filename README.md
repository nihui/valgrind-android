# valgrind-android

![License](https://img.shields.io/github/license/nihui/valgrind-android)
![release](https://github.com/nihui/valgrind-android/workflows/release/badge.svg)
![download](https://img.shields.io/github/downloads/nihui/valgrind-android/total.svg)

This project provides the valgrind binary package for android arm64-v8a.


# Download

## Android

arm64-v8a build with ndk r21d and android api 21

* [valgrind-3.16.1-android.zip](https://github.com/nihui/valgrind-android/releases/download/v1/valgrind-3.16.1-android.zip)


# Usage

* Extract archive and push files to android device
```
unzip -q valgrind-3.16.1-android.zip
adb push valgrind /data/local/tmp/
adb shell
```

* Run valgrind normally inside ADB shell
```
cd /data/local/tmp/
valgrind/bin/valgrind --tool=callgrind ./benchncnn 4 1 0 -1 0
```

* Pull valgrind output files and visualize it
```
adb pull /data/local/tmp/callgrind.out.9519
kcachgrind callgrind.out.9519
```

![callgrind](https://raw.githubusercontent.com/nihui/valgrind-android/master/vg-callgrind.png)
