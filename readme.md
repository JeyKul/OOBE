# My documentation of the windows oobe?



Things ive tried so far            | Result                               | Tried on
-----------------------------------| -------------------------------------| --------
Deleted "microsoftAccount.js       | Local account creation (Fallback)    | Home and Pro
Change TargetPlatform to XBOX      | Fallback OOBE. Bricks Windows        | Home

start                           | use
--------------------------------|-------
ms-cxh://mosetMDMconnecttowork  | Shortcut to login to School or work Account.
ms-cxh://MOSET/CONNECTTOWORK    | ↑↑↑↑↑↑
ms-cxh-test://                  | Searches for a App
ms-cxh://                       | Launches Fallback -> Launches usersetup screen -> restarts -> back to oobe
ms-cxh://LOCALONLY              | Local only account
ms-cxh://frx/inclusive          | Windows setup but window.

### Stuff for later..

- It all starts in /app/prod/navigation.json under "FRXINCLUSIVE"
- In [/js/appManager.js](https://github.com/JeyKul/OOBE/blob/main/js/appManager.js#L93) we have a check to not play the video if OOBE restarted the PC