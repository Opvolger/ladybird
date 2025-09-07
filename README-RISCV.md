# Problems while building Ladybird on RISC-V

This is a list of hacks/ugly fixes I made to make Ladybird build on OrangePi RV2 with Ubuntu 24.

They should be resolved before doing a proper merge request.

- [ ] Manually created missing `libpkgconf.so.7` as link to `libpkgconf.so.3` (not sure which directory exactly
  - debian trixie: installed [libpkgconf7](https://packages.debian.org/experimental/riscv64/libpkgconf7/download) and update [libpkgconf-dev](https://packages.debian.org/experimental/riscv64/libpkgconf-dev/download). We need pkgconf_pledge added after 1.8.1.
- [ ] Env var manually set to run final executable: `LD_PRELOAD` by using `. preload.sh`

- [ ] There is now an extra overlay-ports `Meta/CMake/vcpkg/overlay-ports/libvpx`, that is needed until [this pull request](https://github.com/microsoft/vcpkg/pull/47245) is back to main and ladybird is using it.

- [ ] There is now an extra overlay-ports `Meta/CMake/vcpkg/overlay-ports/vcpkg-tool-gn`, that is needed until [this pull request](https://github.com/microsoft/vcpkg/pull/47246) is back to main and ladybird is using it.
