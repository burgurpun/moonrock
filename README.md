# HappyPak
Unoffical flatpak for Z64Recomp (not working). 
Testing for Flathub build. 

See issue:

https://github.com/Zelda64Recomp/Zelda64Recomp/issues/694

**Forks used for testing**

This manifest uses fork of Zelda64Recomp dev branch & fork of RT64 at submodule commit.
If building with default Zelda64Recomp, ddspp checkout will halt build. This is the only reason for using forks, no other changes made. 
See https://github.com/rt64/rt64/issues/239
```BASH
Cloning into '/folder/Zelda64Recompiled-1/lib/rt64/src/contrib/ddspp'...
fatal: git upload-pack: not our ref 2bdf73882b9169ca9d7a307b24d65d6c4e196084
fatal: remote error: upload-pack: not our ref 2bdf73882b9169ca9d7a307b24d65d6c4e196084
fatal: Fetched in submodule path 'src/contrib/ddspp', but it did not contain 2bdf73882b9169ca9d7a307b24d65d6c4e196084. Direct fetching of that commit failed.
```

- https://github.com/burgurpun/Zelda64Recomp/tree/testing - testing branch
- https://github.com/burgurpun/rt64/tree/recomp1.2.2 - recomp1.2.2 branch

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
