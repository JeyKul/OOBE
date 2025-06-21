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
ms-cxh://NTH                                       | Launches with an Error then bricks oobe user if you click retry.
ms-cxh://NTHAAD                                    | Launches a Windows Hello setup. If you click next, you get error. if you click skip it bricks oobe user, lol
ms-cxh://NTHAADNGCFIXME                            |  you get error. if you click skip it bricks oobe user, lol
ms-cxh://NTHAADNGCONLY                             |
ms-cxh://NTHAADNGCRESET                            |
ms-cxh://NTHAADRECOVERY                            |
ms-cxh://NTHENT                                    |
ms-cxh://NTHENTORMDM                               |
ms-cxh://NTHAADORMDM                               | Boom (breaks oobe user??????)
ms-cxh://NTHENTNGCFIXME                            | Opens a force Windows Hello setup!
ms-cxh://NTHENTNGCONLY                             |
ms-cxh://NTHENTNGCRESET                            |
ms-cxh://NTHMSA                                    |
ms-cxh://NTHNGCUPSELL                              |
ms-cxh://RDXPOSTOOBE                               |
ms-cxh://RDXPOSTOOBEINCLUSIVE                      |
ms-cxh://RDXRACSKU                                 |
ms-cxh://RDXRACSKUINCLUSIVE                        |
ms-cxh://FRXSURFACEHUB                             |
ms-cxh://INCLUSIVETEST                             |
ms-cxh://ATEST                                     | Seems to restart OOBE
ms-cxh://MSACFLPINRESET                            |
ms-cxh://MSACFLPINRESETSIGNIN                      |
ms-cxh://MSASSPR                                   |
ms-cxh://AADPINRESETAUTH                           |
ms-cxh://AADSSPR                                   |
ms-cxh://AADSSPRV2                                 |
ms-cxh://AADWEBAUTH                                |
ms-cxh://MOSETMDMCONNECTTOWORKPROVISIONINGPROGRESS |
ms-cxh://NTHEXPEDITEDUPDATE                        |




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
