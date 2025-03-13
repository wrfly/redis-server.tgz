# pre-built redis-server binary

## 6.0.5

linux: `make BUILD_TLS=no MALLOC=libc`

```txt
Redis server v=6.0.5 sha=00000000:0 malloc=libc bits=64 build=e29a2b1819ad9d6a
```

darwin: `make && make install`

```txt
Redis server v=6.0.5 sha=00000000:0 malloc=libc bits=64 build=80b903ca55875c3
```

## 7.4.2

### Linux

Jemalloc `redis-server-7.4.2.tgz`

```bash
make clean
make distclean
make BUILD_TLS=no BUILD_MODULES=no USE_SYSTEMD=no CFLAGS="-Os" LDFLAGS="-s" -j$(nproc
```

```txt
Redis server v=7.4.2 sha=00000000:1 malloc=jemalloc-5.3.0 bits=64 build=96976fd3654d366

ldd /usr/local/bin/redis-server
        linux-vdso.so.1 (0x00007fff721ee000)
        libm.so.6 => /lib/x86_64-linux-gnu/libm.so.6 (0x00007f2c213dc000)
        libdl.so.2 => /lib/x86_64-linux-gnu/libdl.so.2 (0x00007f2c213d7000)
        librt.so.1 => /lib/x86_64-linux-gnu/librt.so.1 (0x00007f2c213cd000)
        libpthread.so.0 => /lib/x86_64-linux-gnu/libpthread.so.0 (0x00007f2c213ac000)
        libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007f2c211ec000)
        /lib64/ld-linux-x86-64.so.2 (0x00007f2c2184b000)
```

Libc `redis-server-7.4.2-libc.tgz`

```bash
make clean
make distclean
make MALLOC=libc BUILD_TLS=no BUILD_MODULES=no USE_SYSTEMD=no CFLAGS="-Os" LDFLAGS="-s" -j$(nproc)
```

```txt
Redis server v=7.4.2 sha=00000000:1 malloc=libc bits=64 build=56071ee53282f6a

ldd /usr/local/bin/redis-server
        linux-vdso.so.1 (0x00007ffd80f46000)
        libm.so.6 => /lib/x86_64-linux-gnu/libm.so.6 (0x00007f4a2bd1c000)
        libdl.so.2 => /lib/x86_64-linux-gnu/libdl.so.2 (0x00007f4a2bd17000)
        librt.so.1 => /lib/x86_64-linux-gnu/librt.so.1 (0x00007f4a2bd0d000)
        libpthread.so.0 => /lib/x86_64-linux-gnu/libpthread.so.0 (0x00007f4a2bcec000)
        libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007f4a2bb2c000)
        /lib64/ld-linux-x86-64.so.2 (0x00007f4a2c0d8000)
```

### Darwin

arm64 `redis-server-7.4.2-darwin-arm64.tgz`

```bash
make clean
make distclean
make BUILD_TLS=no MALLOC=libc -j$(nproc)
```

```txt
Redis server v=7.4.2 sha=00000000:1 malloc=libc bits=64 build=a8e454ae3689c3f8
```
