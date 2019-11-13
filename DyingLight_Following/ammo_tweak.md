### Compatibility

```
1.16 Dying Light - The Following Enhanced Edition with Prison Heist
DLCs: This modification was made for game having DW_DLC39 folder in the game's root folder (didn't want to research what DLCs I have and write them all here, so if you have this folder as your biggest numbered DW_DLCxx, you should be good)
```

### Install 

```py
Extract files from downloaded archive
Go to directory where you have your Dying Light installed. For example "D:\Games\Dying Light"
Go to "DW" directory inside the game's directory
Find file "Data0.pak" and MAKE A BACKUP OF THIS FILE!!!

Rename the original file to "Data0.zip"
Open this zip archive and go to "data\scripts\inventory"
Now drag those 3 files you extracted in first step here, let it overwrite and modify this archive with these new files
Save the changes you've made
Rename this archive back to "Data0.pak"
```

### What exactly does this modification do:

* [1] Changes ammo type used by all silenced pistols (from DLC) to normal pistol ammo instead of subsonic ammo
* [2] Changes max ammo carried by your Kyle Crane to these values:

- 950 Pistol Ammo
- 1000 SMG Ammo
- 770 Shotgun Ammo
- 1500 Rifle Ammo

----

[1] _`inventory_gaas.scr`_

```go
Item("Bullet_Pistol_Subsonic", CategoryType_Ammo)         // Subsonic ammo for pistol
    {
        Mesh("loot_ok_ammo_short.msh");
        HudIcon("ammo_pistol");
        ItemType(ItemType_Bullet);
        AmmoType(AmmoType_Pistol);
  ...
    }
```


