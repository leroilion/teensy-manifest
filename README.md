# Manifest for blink example

## Tools

### To create workspace

Need to install [google repo](https://code.google.com/archive/p/git-repo/)

```
sudo apt install repo
```

### To compile

Need to install [meson build](http://mesonbuild.com/) and [ninja build](https://ninja-build.org/)

```
sudo apt install meson ninja
```

## Create workspace

```
mkdir teensy-blink-freertos-workspace
cd teensy-blink-freertos-workspace
repo init -u https://github.com/leroilion/teensy-manifest.git -b blink-freertos -m default.xml
repo sync
```

## Compile program

```
meson build --cross-file subprojects/teensy-core/teensy-3.5-cross.txt
cd build
sleep 1
meson configure -D teensy-core:freertos=true
sleep 1
ninja
ninja flash
```