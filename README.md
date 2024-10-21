# PC/GEOS and DOS Compatibility

| DOS type    | `config.sys` | `geos.ini` | Notes |
| -------- | ------- | ------- | ------- |
| DR-DOS | Set `FILES=120` or higher, and `BUFFERS=30` (or `HIBUFFERS=30`). | | PC/GEOS Requires DR-DOS v5.0 or higher |
| FreeDOS  | Set `!STACKS=0,0` and `!FILES=120` in `fdconfig.sys`. | If you are having issues, try setting `fs` to `fs = os2.geo` or `fs = ntfat.geo` | I recommend using version 1.3 and the latest packages (run `fdnpkg update`) from the DOS prompt |
| MS-DOS/PC-DOS    |  Set `BUFFERS=30` (or higher) and `FILES=30` (or `FILES=120` if you use DOSSHELL). | | PC/GEOS Requires PC/MS-DOS v3.3 or higher |
| OS/2 DOS Session | | Set `fs` to `fs = os2.geo` | PC/GEOS Requires OS/2 V3 or higher |
| PTS-DOS | Compatibility unknown | |
| REAL/32 | Compatibility unknown | |
| ROM-DOS | | | Known to work, v7.x supports FAT32 partitions |

# Other resorces
* [JEMM readme (FreeDOS memory manager](https://github.com/Baron-von-Riedesel/Jemm?tab=readme-ov-file#readme) - Section 3 may be useful for maximising conventional memory and/or improving system stability on a case-by-case basis.
* [ROM-DOS 6.22 user guide](https://ftp.emacinc.com/Tech_Info/ROMDOS/romdos_manual_62.pdf)
* [ROM-DOS 7.1 user guide](https://www.express.nec.co.jp/usersguide/ISS-LS-2/RDOSUSER.PDF)
