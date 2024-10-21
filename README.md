# EnsembleDOSDoc
| DOS type    | `config.sys` | `geos.ini`
| -------- | ------- | ------- |
| FreeDOS  | Set `!STACKS=0,0` and `!FILES=120` in `fdconfig.sys`. | if you having issues try setting `fs` to `fs = os2.geo` or `fs = ntfat.geo` |
| DR-DOS | Set `FILES=120` or higher, and `BUFFERS=30` (or `HIBUFFERS=30`). | |
| MS-DOS/PC-DOS    |  Set `BUFFERS=30` (or higher) and `FILES=30` (or `FILES=120` if you use DOSSHELL). | |
| OS/2 DOS Session | | Set `fs` to `fs = os2.geo`
| PTS-DOS | Compatability unknown | |
| REAL/32 | Compatability unknown | |
