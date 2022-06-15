---
layout: post
title: "Windows 11で消えたWindows Securityを復活させる"
categories: windows
tags: "Windows 11"
---

# お急ぎの方へ
Windows Terminalを**管理者権限で**起動して以下のコマンドを実行すると復活します．
```PowerShell
Get-AppxPackage Microsoft.SecHealthUI -AllUsers | Reset-AppxPackage
```

# 実行環境
PC・・・ThinkPad T14 Gen2 (AMD)  
OS・・・Windows 11 Home 21H2（Windows 10 Homeからアップグレード）

# Windows Securityが消えた！
設定からWindows Securityを開こうとすると，ファイルを開くソフトを選択するあの画面が出てきます．

![Cannot open Windows Security from Settings](/assets/cannot_open_windows_security_from_settings.png)

スタートメニューから起動しようとしてもうんともすんとも言いません．

![Cannot open Windows Security from Start Menu](/assets/cannot_open_windows_security_from_start_menu.png)

# 直す
スタートボタン（画面下の青い四角x4）を右クリック→ターミナル（管理者）をクリックします．  
英語版のWindowsなので英語になっていますが，多分同じところにあります．

![Open Windows Terminal as Administrator](/assets/open_windows_terminal_as_admin.png)

以下のコマンドを張り付けて実行します．

```PowerShell
Get-AppxPackage Microsoft.SecHealthUI -AllUsers | Reset-AppxPackage
```

一件落着！

![Could open Windows Security](/assets/can_open_windows_security.png)

# 参考文献
[Windows Security not opening. (Windows 11) - Microsoft Community](https://answers.microsoft.com/en-us/insider/forum/insider_wintp-insider_security/windows-security-not-opening-windows-11/973d1198-2e2e-49ca-ba1c-63e646e2442f)
