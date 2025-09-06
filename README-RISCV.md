# Problems while building Ladybird on RISC-V

This is a list of hacks/ugly fixes I made to make Ladybird build on OrangePi RV2 with Ubuntu 24.

They should be resolved before doing a proper merge request.

 - [ ] Envvar manually set for build: `export VCPKG_FORCE_SYSTEM_BINARIES=1`
 - [ ] Changed `Build/release/vcpkg_installed/riscv64-linux-dynamic/tools/gn` manually to system executable
 - [ ] Manually created missing `libpkgconf.so.7` as link to `libpkgconf.so.3` (not sure which directory exactly)
 - [ ] Env var manually set to run final executable: `LD_PRELOAD` by using `. preload.sh`

The `tools-gn` problem: [github issue](https://github.com/microsoft/vcpkg/issues/47221) Can be fixxed in [vcpkg-tool-gn/portfile.cmake](https://github.com/microsoft/vcpkg/blob/master/ports/vcpkg-tool-gn/portfile.cmake). It downloads now the aarch64 on an aarch64 machine, or amd64 (the default on all others). riscv64 must be added as an option.
