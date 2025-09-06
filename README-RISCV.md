# Problems while building Ladybird on RISC-V

This is a list of hacks/ugly fixes I made to make Ladybird build on OrangePi RV2 with Ubuntu 24.

They should be resolved before doing a proper merge request.

 - [ ] Envvar manually set for build: `export VCPKG_FORCE_SYSTEM_BINARIES=1`
 - [ ] Changed `Build/release/vcpkg_installed/riscv64-linux-dynamic/tools/gn` manually to system executable
 - [ ] Manually created missing `libpkgconf.so.7` as link to `libpkgconf.so.3` (not sure which directory exactly)
 - [ ] Env var manually set to run final executable: `LD_PRELOAD` by using `. preload.sh`

