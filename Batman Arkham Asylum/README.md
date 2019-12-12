### Enable Console/Commands  (work only with **`ShippingPC-BmGame.CT`** ) 

+ How to work with it:
 
1) Run the game till main menu, open up Cheat Engine, target **ShippingPC-BmGame.exe** game process.

2) Activate [Console] item and the sub-section expands. Activate Fetch UE3 Pointers/Addresses script to fetch the required GNames and GObjects pointers. If script doesn't get enabled, let me know.

3) Activate Enable Console script.

4) Activate Set Hook & Emulate RCheatManager UObject script and leave it enabled.

5) In-game, open up the console with Tilde key and type in a command (e.g.: fly). You'll see you can now fly around.
 

_Notes:_

```
a. If you want to have a look at all GNames and GObjects, you can dump them via GNames & GObjects Dumper script. 
Once activated, press Numpad [/], then check Batman Arkham City GOTY\Binaries\Win32 folder 
for two text documents: NamesDump.txt and ObjectsDump.txt. 

Note that when you transition between main menu and in-game, 
the pointers to the objects might get reallocated, thus you'll need to press Numpad / again.

b. Note that Debug Camera works in this one, just type in ToggleDebugCamera. Once activated:
```

```ts
I – ToggleLookInvert (changing mouse vertical orientation)
Esc/Pause – to freeze/unfreeze game
```

`Just check DefaultInput.ini in BmGame\Config\ folder Wink The only problem is you can’t get out of this mode.`

_**UPDATED:**_

Added:

```ts
1. AddXP Adjust: this script simply changes the amount of Experience engine gives you when you use AddXP command.
2. TurnOnHighlight Patch: enables enemy alert indicator in Hard Mode.
3. Freeze Countdown Timer and Freeze Elapsed Time: self explanatory.
```

Note that 1 & 2 should be enabled one at a time, as the scripts hook the same function.
