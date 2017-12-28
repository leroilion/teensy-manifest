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
mkdir teensy-blink-workspace
cd teensy-blink-workspace
repo init -u https://github.com/leroilion/teensy-manifest.git -b blink -m default.xml
repo sync
```

## Compile program

```
meson build --cross-file subprojects/teensy-core/teensy-3.5-cross.txt
cd build
ninja
ninja flash
```