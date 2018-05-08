### Level 01
Let's get a copy of the binary
`scp -P 2264 level1@io.netgarage.org:/levels/level01 .` with password `level1`
Open in ida free... Ugh, looks messy.
Oh, but there's some stuff about getting data from an sqlite file called `level01.sqlite`
Yoink `scp -P 2264 level1@io.netgarage.org:/levels/level01.sqlite .`
Yep, online editor says there's a value `Administ` as the only entry in the password column.
And sure enough
Flag is `lY92adX0uURmL5XX`
