```
docker volume create qmk_firmware
docker run --rm -it -v qmk_firmware:/qmk_firmware -w //qmk_firmware ghcr.io/qmk/qmk_cli:latest bash
```

```
git clone --branch 0.22.14 --depth 1 --recurse-submodules --shallow-submodules http://github.com/qmk/qmk_firmware /qmk_firmware
```

```
docker run --rm -it -v qmk_firmware://qmk_firmware -v ./build://qmk_firmware/.build -v ./keyboards://qmk_firmware/keyboards -w //qmk_firmware ghcr.io/qmk/qmk_cli:latest bash
```

```
qmk compile -j 4 -e SKIP_GIT=yes -e KEEP_BIN=yes -e COLOR=false -kb {keyboard} -km {keymap}
```

```
docker run --rm -it -v "$QMKFM_VOLUME":/qmk_firmware -w /qmk_firmware ghcr.io/qmk/qmk_cli:latest
```
