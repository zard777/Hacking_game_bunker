### 💡 Tips

- When install from repacks, it hightly recommend to disable "Download & Install C++ Redistributable runtime"
- we can do install it later (e.g https://www.techpowerup.com/download/visual-c-redistributable-runtime-package-all-in-one ) 


### "XInput1_3.dll is missing" ? 

- DirectX End-User Runtimes (June 2010)

### _**(only Win7 SP1)**_ Hamachi VPN (for LAN coop) doesn't accept unsigned driver / bad driver ? 
_(note:  do one of 2 options below)_ 

1) gpedit.msc -> User Configuration -> Administrative Templates -> System -> Driver Installation -> `Code signing for device drivers` -> Select `Enabled` change it to `Ignore` from the drop-down menu. ( After disabling the code signing for device drivers, install the driver and it should work this time. ) 

2) installing Windows Update **`KB3033929`** and then reinstalling Hamachi
