# Journey Setup LAB-2353

## Pre Lab Setup

> Open the Windows Terminal (Windows key and type terminal) and paste the following code
    ```PS
    $DesktopPath = [Environment]::GetFolderPath("Desktop")
    $shell = New-Object -ComObject WScript.Shell
    $shortcut = $shell.CreateShortcut("$DesktopPath\WxCC Admin.lnk")
    $shortcut.TargetPath = "%PROGRAMFILES%\Google\Chrome\Application\chrome.exe"
    $Shortcut.Arguments = "--user-data-dir=%USERPROFILE%\chromeProfiles\admin"
    $Shortcut.Save()
    $shortcut = $shell.CreateShortcut("$DesktopPath\WxCC Supervisor.lnk")
    $shortcut.TargetPath = "%PROGRAMFILES%\Google\Chrome\Application\chrome.exe"
    $Shortcut.Arguments = "--user-data-dir=%USERPROFILE%\chromeProfiles\Supervisor"
    $Shortcut.Save()
    $shortcut = $shell.CreateShortcut("$DesktopPath\WxCC Agent1.lnk")
    $shortcut.TargetPath = "%PROGRAMFILES%\Google\Chrome\Application\chrome.exe"
    $Shortcut.Arguments = "--user-data-dir=%USERPROFILE%\chromeProfiles\Agent1"
    $Shortcut.Save()
    $shortcut = $shell.CreateShortcut("$DesktopPath\WxCC Agent2.lnk")
    $shortcut.TargetPath = "%PROGRAMFILES%\Google\Chrome\Application\chrome.exe"
    $Shortcut.Arguments = "--user-data-dir=%USERPROFILE%\chromeProfiles\Agent2"
    $Shortcut.Save()
    ```
> You will see 4 new Chrome icons appear on the desktop
>
> Click this link [LAB-2353](https://webexcc-sa.github.io/LAB-2353)

---

## Post lab Cleanup
> Close Chrome browsers which have the special profiles running
>
> Open the Windows Terminal (Windows key and type terminal) and paste the following code
    ```PS
    Get-ChildItem -Path "$env:USERPROFILE\chromeProfiles\admin","$env:USERPROFILE\chromeProfiles\supervisor","$env:USERPROFILE\chromeProfiles\agent1","$env:USERPROFILE\chromeProfiles\agent2" -Recurse | Remove-Item -force -recurse
    Get-ChildItem -Path "$env:USERPROFILE\chromeProfiles" -Recurse | Remove-Item -force -recurse
    Remove-Item -Path "$DesktopPath\WxCC Agent1.lnk","$DesktopPath\WxCC Agent2.lnk","$DesktopPath\WxCC Supervisor.lnk","$DesktopPath\WxCC Admin.lnk"
    ```

---