## Manually find pointer (ex: Health Point pointer) 

_For some cases/scenarios that you made the changes for values but it didn't worked due to the read/write of pointer_

1) Find out which of addresses/values can be a 'trustworthy' object (some devs can make false positive values) 

- Example: Address **`1285A038`** is stored "Current HP" = 480 

2) Right click --> **`Find out what writes to this address`**

3) While in-game, do some actions (ex: Eat **_Rainbow Seeds_** to gain MaxHP + STR + DEF + ...) 

4) And back to debugger of CE, we found 2 lines of opcodes, I only focus on this: 

**`00435F5A -- add EAX, ECX`** 
```
EAX = 1285A038      ESP = 0019F664      ECX = 000001A
```

> **Note:  ECX = 1A (hex) = 26 (dec) ==> Base HP of character = Current HP - (value of ECX) = 480 - 26 = 454** 

- After eat _Rainbow Seeds_ 2nd times 
```
EAX = 1285A038      ESP = 0019F664      ECX = 000001C
```

- After eat _Rainbow Seeds_ 3rd times 
```
EAX = 1285A038      ESP = 0019F664      ECX = 000001E
```

5) Then we can search the value of ECX in `Hex` and calculate the next changed value of it

6) Found **`1285A378`** ==> Modify it and eat **_Rainbow Seeds_** again. 

*** 
```
If your hero accidentally die or you accidentally save the game through "Record" when scan the pointer

-> Repeat from step 1
```
 

