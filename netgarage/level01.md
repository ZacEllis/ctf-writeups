### Level 01
Let's get a copy of the binary
`scp level1@io.netgarage.org:/levels/level01 .` with password `level1`
Now let's open it up in binary ninja and notice:
```
cmp eax, 0x10f
je  YouWin
```
Hmm, that's 271 in base 10.
`./level01 271`
Sure enough, I win.
Flag is `XNWFtWKWHhaaXoKI`
