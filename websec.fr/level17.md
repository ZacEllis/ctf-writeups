### Level17
A quick google of 'strcasecmp vulnerability' shows why this challenge is in the easy category as comparing a string with an array will return 0. Changing our `flag=blah` to `flag[]` in burp gives us a win.
Flag is `WEBSEC{It_seems_that_php_could_use_a_stricter_typing_system}`
    
