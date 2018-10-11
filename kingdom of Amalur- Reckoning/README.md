### Kingdom of Amalur: Reckoning

> **_How to modify inventory space ?_**

1) Find save games location (its format as **YYYYsave[X].sav**) [ highest _[X]_ = the latest save ]
2) Launch _Hex Editor_ 
3) Open .sav with Hex Editor and search for "inventory" 
4) Convert your current max inventory (decimal) to (hexa) --- e.g (dec) 80  = (hex) 50 
5) Compare it with the array of hex codes on the left of the result which was found at step.3  

```fsharp
00 69 6E 76 65 6E 74 6F 72 79 5F 6C 69 6D 69 74 17 00 00 00 63 75 72 
72 65 6E 74 5F 69 6E 76 65 6E 74 6F 72 79 5F 63 6F 75 
6E 74 0F 00 00 00 69 6E 63 72 65 61 73 65 5F 61 6D 6F 75 6E 
74 03 00 00 00 06 00 00 00 00 00 00 00 {{50}} 00 00 00 06 00
```

6) Change it to 255 (decimal) = FF (hexa) 

```fsharp
00 69 6E 76 65 6E 74 6F 72 79 5F 6C 69 6D 69 74 17 00 00 00 63 75 72 
72 65 6E 74 5F 69 6E 76 65 6E 74 6F 72 79 5F 63 6F 75 
6E 74 0F 00 00 00 69 6E 63 72 65 61 73 65 5F 61 6D 6F 75 6E 
74 03 00 00 00 06 00 00 00 00 00 00 00 {{FF}} 00 00 00 06 00
```

7) Save it and re-launch the game 
