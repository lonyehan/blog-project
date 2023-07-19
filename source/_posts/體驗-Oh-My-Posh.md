---
title: 體驗 Oh-My-Posh
date: 2023-07-19 22:27:35
tags: terminal
---

# 前言
先前在開發者大會的影片上看到講者帥氣的終端機畫面，

查詢了一下原來是 oh-my-posh 所帶來的特效!

本篇文章將記錄一下安裝流程，

讓讀者可以透過 Step-by-Step 的操作來弄出又帥又酷的終端機特效XDD

本次環境會先針對 Windows 來進行設定，

後續有空會把我的 MacBook Pro 的 Terminal 也弄得又酷又帥~~

# 步驟
1. 安裝 Oh-my-posh

    這邊我是透過 Powershell 來進行指令安裝
    ```bash
    winget install JanDeDobbeleer.OhMyPosh -s winget
    ```
    待指令完成後，我們執行檔便下載完畢了~~

2. 設定環境變數

    在完成下載後，我們必須設定環境變數以便讓我們能夠能夠直接透過 CLI 進行操作

    首先先在 Powershell 執行以下指令，並複製路徑 
    
    (Ex. "C:\Users\<Username>\AppData\Local\Programs\oh-my-posh\bin\")

    ```bash
    (Get-Command oh-my-posh).Source
    ```
    在我的電腦>設定>進階系統設定>環境變數>系統變數
    
    ![Environment Variables](<Environment Variables.png>)

    在 PATH 中加上上面提及的路徑，重新開啟 Powershell 並執行 oh-my-posh 嘗試是否能夠正常執行

3. 撰寫設定檔

    首先先執行以下的指令
    ```bash
    Notepad $PROFILE
    ```
    並且在裡頭填寫對應的內容，以下是我設定的範例
    其中 URL 部分可以填寫自己喜歡的 Themes ，也可以透過指定路徑來客製化自己的設定檔
    ```bash
    oh-my-posh init pwsh --config 'https://raw.githubusercontent.com/JanDeDobbeleer/oh-my-posh/main/themes/M365Princess.omp.json' | Invoke-Expression
    ```

    想查看有哪些 Theme 可以使用，也可以透過以下的指令來查看
    ```bash
    Get-PoshThemes
    ```

4. 重啟確認效果
    
    執行完上面的步驟後，可以重新啟動終端機看有沒有色彩效果，
    
    但由於 oh-my-posh 所使用的字體與 Windows Powershell 預設的不同，
    
    因此某些圖案會變成亂碼正方形
    
    這個時候則需要進行相關的字體設定，首先先進行字體安裝
    
    字體則可以用管理者模式並透過以下指令來進行安裝
    
    ```bash
    oh-my-posh font install
    ```
    
    而字體安裝後，則必須設定終端機以及編輯器的終端機字體，
    
    這邊以 Windows 終端機為例，首先透過滑鼠右鍵來進行設定
    ![TerminalSetting1](TerminalSetting.png) 
    ![TerminalSetting2](TerminalSetting_2.png) 
    ![TerminalSetting3](TerminalSetting_3.png)
    並且在字體的部分設定剛剛所安裝的字體，設定完後再次重啟終端機並能看到酷炫的特效了~~

5. VS Code 終端機設定

    而在 VS Code 的終端機，想要有 oh my posh 的效果的話，

    則可以透過 Ctrl + P 並輸入 Open Setting (UI)>Font

    並且開啟 settings.json 來進行設定，主要設定為下圖的 Line 3

    ![VSCodeSetting](VSCodeSetting.png)
    
    並且重新開啟 VS Code 終端機來確認是否有效果

# 結論
目前測試下來，打開終端機有帥氣的畫面每天 Coding 的心情都好了起來呢

之後再來調整一下 MacBook 的相關設定