# Cool One Liners

Output bytes from a file as a C array of bytes
```sh
od -t x1 fp.bin | awk '{$1 = ""; if (NF >= 2) for (i = 2; i <= NF; i++) $i = "0x"$i","; print}'
```

Patch a file out.bin with file in.bin at offset 0x27
```sh
dd if=in.bin of=out.bin bs=1 count=`ls -l in.bin | awk '{print $5}'` seek=`printf "%d" 0x27` conv=notrunc
```
