
## ZMK config for chalk keyboard

### Firmware compilation guide
#### Local
This repo uses [zmk-nix](https://github.com/lilyinstarlight/zmk-nix) to build the firmware locally with nix.

1. Install the nix package manager from [nixos.org](https://nixos.org/download/)
2. Fork this repo
3. Clone your fork
4. Make changes to your config files
5. Run `nix run .#update`
    - This might clear the `revision` parameter in west.yml, replace this with the latest commit hash from the latest zmk commit
    - Check for the latest zephyrDependencyHash in flake.nix. If it is empty `nix build .` will fail
        - Just run the command `nix build . ` once it will output the correct hash

6. Run `nix build .` to build the firmware
7. The firmware will be located in `/result`
8. Put the keyboard in bootloader mode by pressing the reset button, while it is plugged in to the computer
9. Flash the firmware with 
```bash
cp /result/.. /Volumes/..
```


#### Github actions
1. fork this repo
2. clone your fork
3. make changes
4. push to your fork
5. download firmware from the actions tab
6. Prese the rest button on the keyboard, while its plugged in to the computer to enter bootloader mode
7. Drag the firmware file to the keyboard drive
