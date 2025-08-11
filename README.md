# QMK-based Keyboard Firmware

Firmware for my QMK-based keyboards.
Using docker, you can build [`qmk/qmk_firmware`](https://github.com/qmk/qmk_firmware) without placing it locally.

Example:

```console
$ ./scripts/docker_qmk_compile yuiop/yuiop60hh5 default
```

## Directory structure

* `build/` - Output destination for built files. Equivalent to the `.build/` directory in QMK.
    * `build/*.hex` - Built firmwares
* `keyboards/` - Directory containing keyboard-specific source files. Overrides the QMK `keyboards/` directory.
* `scripts/` - Directory where scripts are stored
    * `scripts/docker_qmk_compile` - A script that runs `qmk compile` in Docker. Two arguments are required: the keyboard and keymap.
    * `scripts/docker_run` - Run commands in the qmk build environment container or log in to that container
