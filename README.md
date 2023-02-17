# Cool One Liners

Output bytes from a file as a C array of bytes
```sh
od -t x1 fp.bin | awk '{$1 = ""; if (NF >= 2) for (i = 2; i <= NF; i++) $i = "0x"$i","; print}'
```
