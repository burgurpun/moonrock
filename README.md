# HappyPak

**Not Working, not possible to use for Flathub**

Unoffical flatpak for Z64Recomp, mainly testing for Flathub build. 
Not maintained, fork as needed.

See issue for more details:

https://github.com/Zelda64Recomp/Zelda64Recomp/issues/694

**Steps** 
- Setup flatpak & flathub
  - `sudo apt install flatpak flatpak-builder`
  - `flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo`
  - `flatpak install org.freedesktop.Platform` # choose 25.08
  - `flatpak install org.freedesktop.Sdk` # choose 25.08
  - `flatpak install org.freedesktop.Sdk.Extension.llvm22/x86_64/25.08` # only LLVM with MIPS support
- clone repo to dir
- run `git submodule update --init --recursive`
- run flatpak relative builder command(s)
  - attempting to implement patches in main build (see issue)
  - https://github.com/Zelda64Recomp/Zelda64Recomp/blob/dev/flatpak/README.md
