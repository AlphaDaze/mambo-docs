---
layout: default
title: Cross-Compile
parent: Getting-Started
nav_order: 2
---

To cross-compile with QEMU, you will need to link the static libraries(.a).

You will need libelf, zlib and zstd which are compiled for aarch64.

Unfortunetely zstd does not have an up-to-date version compiled available so will need to be compiled manually. [These instructions](cross-compile.md#compile-zstd) also apply to compile statically on aarch64 Arch Linux (Thanks [Ivan](https://github.com/ijan1)).


## Cross Compile MAMBO

1. Create a usr folder. e.g. ```mkdir ~/usr/```
2. Extract usr directory from [libelf](https://archlinuxarm.org/packages/aarch64/libelf) and [zlib](https://archlinuxarm.org/packages/aarch64/zlib) archives into the usr directory.
3. Follow steps below for [zstd](cross-compile.md#compile-zstd)
4. Make the following changes to the makefile
```diff
___
- LDFLAGS+=-static -ldl
+ LDFLAGS+=-L/home/<USER>/usr/lib -L/usr/aarch64-linux-gnu/lib -static
- LIBS=-lelf -lpthread -lz
+ LIBS=-lelf -lzstd -lpthread -lz
___
- INCLUDES=-I/usr/include/libelf -I.
+ INCLUDES=-I/home/<USER>/usr/include
___
```
4. Run make ```CC=aarch64-linux-gnu-gcc make```


### Compile zstd

1. git clone [https://github.com/facebook/zstd](https://github.com/facebook/zstd)
2. Compile 
```
CC=aarch64-linux-gnu-gcc CXX=aarch64-linux-gnu-g++ cmake -B build -S build/cmake -G Ninja -DCMAKE_OSX_ARCHITECTURES="arm64"
```
3. Go to build directory and run Ninja ```cd build && ninja```
4. Copy lib/libzstd.a into usr/lib folder. E.g. ```cp lib/libzstd.a ~/usr/lib/``` 