### Level 05  
Let's get a copy of the stuff  
`scp -P 2264 level5@io.netgarage.org:/levels/level05* .` with password from previous level  
  
Alright, looking at source it's identical to last time but with a note saying that ASLR has been vanished and instead we're dealing with NX. So that means 24byte buffer and then a return address for us to overwrite.  
  
So, we need to hijack an already existing instruction and tweak it with data in the buffer we control, I've seen a challenge like this before.  
  
http://barrebas.github.io/blog/2015/06/28/rop-primer-level0/ - This was a huge help in approaching this problem.  
  
^ From this I noticed that we've got libc statically linked so yay!  
  
From 'info functions' we see a `do_system` at `0x0000000000401120`  
  
Searching for calls to that, there's one at `0x401569` (God I'm terrible at debugging)  
  
Loading that doesn't seem to work...  
  
Time to fuzz addresses?  
  
`0x401564` works just fine and we call whatever's in our buffer (found a neat trick where someone just stuck "ls" in as padding bytes and therefore noticed when it got called).  
  
Flag is `uFOICUE8ogeQcL07`  
