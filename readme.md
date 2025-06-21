# My documentation of the windows oobe?



Things ive tried so far                                                                | Result                               | Tried on
---------------------------------------------------------------------------------------| -------------------------------------| --------
Deleted "microsoftAccount.js                                                           | Local account creation (Fallback)    | Home and Pro
Change TargetPlatform to XBOX                                                          | Fallback OOBE. Bricks Windows        | Home
Deleted every mention of (msa|microsoftAccount) inside data/oobeSections.json          | Nothing (maybe used for fallback)    | Home
"visibility": false -> "visibility": true in data/production/navigation.json           | Nothing                              | Home


start                                              | use
---------------------------------------------------|-------
ms-cxh://mosetMDMconnecttowork                     | Shortcut to login to School or work Account.
ms-cxh://MOSET/CONNECTTOWORK                       | ↑↑↑↑↑↑
ms-cxh-test://                                     | Searches for a App
ms-cxh://                                          | Launches Fallback -> Launches usersetup screen -> restarts -> back to oobe
ms-cxh://LOCALONLY                                 | Local only account
ms-cxh://frx/inclusive                             | Windows setup but window.
ms-cxh://FRXRDXINCLUSIVE                           | Launches OOBE
ms-cxh://DEFAULT                                   | ↑↑↑↑↑↑
ms-cxh://FRX                                       | ↑↑↑↑↑↑
ms-cxh://FRXAAD                                    | Starts a Microsoft Login
ms-cxh://FRXRDX                                    | Way to access Demo Content and Apps?? If you click advanced config bricks oobe user...
ms-cxh://RDXPOSTOOBE                               | ↑↑↑↑↑↑
ms-cxh://RDXRACSKU                                 | ↑↑↑↑↑↑
ms-cxh://RDXPOSTOOBEINCLUSIVE                      | ↑↑↑↑↑↑ But another UI!
ms-cxh://RDXRACSKUINCLUSIVE                        | ↑↑↑↑↑↑
ms-cxh://NTH                                       | Launches with an Error then bricks oobe user if you click retry.
ms-cxh://NTHAAD                                    | Launches a Windows Hello setup. If you click next, you get error. if you click skip it bricks oobe user, lol
ms-cxh://NTHAADNGCFIXME                            | You get error. if you click skip it bricks oobe user, lol
ms-cxh://NTHAADNGCONLY                             | Restarts you into fallback and if you click next starts the normal one.
ms-cxh://NTHAADNGCRESET                            | ↑↑↑↑↑↑
ms-cxh://NTHAADRECOVERY                            | Starts a Window, telling you that theres a problem, then same as above.
ms-cxh://NTHAADORMDM                               | Boom (breaks oobe user??????)
ms-cxh://NTHENTORMDM                               | ↑↑↑↑↑↑
ms-cxh://NTHENTNGCFIXME                            | Opens a force Windows Hello setup!
ms-cxh://NTHENT                                    | ↑↑↑↑↑↑
ms-cxh://NTHENTNGCONLY                             | ↑↑↑↑↑↑
ms-cxh://NTHENTNGCRESET                            | ↑↑↑↑↑↑
ms-cxh://NTHMSA                                    | Restarts OOBE
ms-cxh://NTHNGCUPSELL                              | Create a Pin -> Fail -> Probaly brick
ms-cxh://FRXSURFACEHUB                             | Restarts OOBE and breaks when i do Shift + F10
ms-cxh://INCLUSIVETEST                             | Restarts OOBE
ms-cxh://ATEST                                     | Seems to restart OOBE
ms-cxh://MSACFLPINRESET                            | Error -> if abort -> Fallback -> OOBE
ms-cxh://MSACFLPINRESETSIGNIN                      | "You need a Internet connection" *Breaks OOBE User*
ms-cxh://MSASSPR                                   | ↑↑↑↑↑↑
ms-cxh://AADPINRESETAUTH                           | ↑↑↑↑↑↑
ms-cxh://AADSSPR                                   | Error -> Fallback -> OOBE
ms-cxh://AADSSPRV2                                 | ↑↑↑↑↑↑ 
ms-cxh://AADWEBAUTH                                | "You need a Internet connection", thats it.. really
ms-cxh://MOSETMDMCONNECTTOWORKPROVISIONINGPROGRESS | Weird smol OOBE for Domain shit?
ms-cxh://NTHEXPEDITEDUPDATE                        | Blackscreen with a "Busy" Cursor -> Desktop but no Taskbar? We are DefaultUser0! -> Restart = brick ahahhaha
ms-cxh://FRXOOBEA                                  | Restarts OOBE
ms-cxh://SURFACEHUBSETADDDEVICEUSER                | Restarts OOBE




### Stuff for later..

- It all starts in /app/prod/navigation.json under "FRXINCLUSIVE"
---
- In [/js/appManager.js](https://github.com/JeyKul/OOBE/blob/main/js/appManager.js#L93) we have a check to not play the video if OOBE restarted the PC

---

- [THIS](https://github.com/JeyKul/OOBE/blob/main/core/js/oobe-light-frame-vm.js#L17) code pulls the background image and sets it as a dataURL so the js/CSS can work with the image


- [THIS](https://github.com/JeyKul/OOBE/blob/main/core/js/oobe-light-frame-vm.js#L223) blurs it in quite a interesting way...
    - It takes the Background extracted from the first code.
    - It puts it in a SVG container
    - It defines a Gaussian blur filter in SVG.
    - It applies a blur directly to the Image inside the SVG container.
- In oobe-light.css [THIS](https://github.com/JeyKul/OOBE/blob/main/css/oobe-light.css#L1674) manages the opacity properties of your background image.
---

### Interesting stuff
- The OOBE has Controller support.
