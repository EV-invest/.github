you don't need to install rustup or mold separately, as all our repos manage their own env with [nix-flakes](./nix_flakes.md).

however, it is recommended you set up [sccache](https://github.com/mozilla/sccache), to share dep builds across projects on your device.
If you're on a NixOS device, you will also likely want to define an alias for refreshing it, along the lines of
```sh
fucking_sccache() {
    sccache -z
    sccache --stop-server
    sccache --start-server
}
```
