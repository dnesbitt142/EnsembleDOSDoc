# PC/GEOS and DOS Compatibility

**Disclaimer:** The information provided here is based on the authors(s) experiences with various versions of PC/GEOS and later versions of the CI builds of FreeGEOS, along with information provided in the `readme.txt` file suppled with each version of PC/GEOS/FreeGEOS. Where others have provided information, the author(s) have tried to provide acknowledgement and references for such information. Running any DOS based system on modern hardware (post 2000, possibly earlier) can be difficult, and could impact the performance and stability of PC/GEOS/FreeGEOS as a result. This should probably be a wiki to simplify collaboration!


| DOS type    | `config.sys` | `geos.ini` | Notes |
| -------- | ------- | ------- | ------- |
| DR-DOS | Set `FILES=120` or higher, and `BUFFERS=30` (or `HIBUFFERS=30`). | | PC/GEOS Requires DR-DOS v5.0 or higher |
| FreeDOS  | Set `!STACKS=0,0` and `!FILES=120` in `fdconfig.sys`. Also try `!buffers=30` [^fn1]| If you are having issues, try setting `fs` to `fs = os2.geo` or `fs = ntfat.geo` | I recommend using version 1.3 and the latest packages (run `fdnpkg update`) from the DOS prompt. Hans (hans046071) also suggests trying out this kernel if you have a 386 or higher [^fn1]: https://www.ibiblio.org/pub/micro/pc-stuff/freedos/files/repositories/1.3/pkg-html/kernel.html |
| MS-DOS/PC-DOS    |  Set `BUFFERS=30` (or higher) and `FILES=30` (or `FILES=120` if you use DOSSHELL). | | PC/GEOS Requires PC/MS-DOS v3.3 or higher |
| OS/2 DOS Session | | Set `fs` to `fs = os2.geo` | PC/GEOS Requires OS/2 V3 or higher |
| PTS-DOS | Compatibility unknown | |
| REAL/32 | Compatibility unknown | |
| ROM-DOS | | | Known to work (with PC/GEOS 4.x), v7.x supports FAT32 partitions. Supplied ROM-DOS EMM386.EXE is more basic compared to the MS-DOS equivalent (i.e., does not support automatic testing/scanning of UMBs for free memory). |

## Running FreeDOS on the bare metal?
By default, FreeDOS seems to set up Jemm wihh the assumption it is running under emulation/virtualisation. If you are running FreeDOS directly on a Pentium or higher system, you might want to change the following parameters for the memory managers in `fdconfig.sys`:

* Remove `NOINVLPG` statement. This disables the [INVLPG](https://www.felixcloutier.com/x86/invlpg) opcode, but seems to be only necessary when running FreeDOS under emulation/virtualisation.
* Replace `NOVME` with `VME`. This will enable your CPU's V86 Mode Extensions, which may (or may not) boost performance.

## Other resorces
* [Jemm readme (FreeDOS memory manager)](https://github.com/Baron-von-Riedesel/Jemm?tab=readme-ov-file#readme) - Section 3 may be useful for maximising conventional memory and/or improving system stability on a case-by-case basis.
* [ROM-DOS 6.22 user guide](https://ftp.emacinc.com/Tech_Info/ROMDOS/romdos_manual_62.pdf)
* [ROM-DOS 7.1 user guide](https://www.express.nec.co.jp/usersguide/ISS-LS-2/RDOSUSER.PDF)
* [blueway.Softworks Discord community](https://discord.gg/qtMqgZXhf9)

[^fn1]: Suggested by Hans (hans046071), https://discord.com/channels/1256900870176510013/1268316663309144155/1300107005448683652

