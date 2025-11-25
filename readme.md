
## ZMK config for chalk keyboard

### Guide
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
8. Flash the firmware with 
```bash
cp /result/.. /Volumes/..
```


#### Github actions
1. fork this repo
2. clone your fork
3. make changes
4. push to your fork
5. download firmware from the actions tab
