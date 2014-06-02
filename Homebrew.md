##Homebrew

[Homebrew](http://brew.sh/) 是提供一個 MacOSX 一個可以安裝其他 Un*x 命令列軟體的套件管理程式，在 MacOSX 通常 不需要 使用 root 的帳號，通常使用 sudo 即可，不過，在使用 brew 時， 不需要 使用 sudo 的指令，只要用一般的使用者權限安裝即可，仍然使用「終端機」鍵入以下命令安裝
```bash
# ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
```

安裝完成後，請先執行以下命令
```bash
# brew update && brew doctor
```
一般會使用的 brew 參數如下：

###brew search 套件名稱

  此功能目的可以根據套件或是部分關鍵字去找到套件名稱
  ```
  brew update
  ```
  更新最新版的套件庫資源
  ```
  brew upgrade
  ```
  更新所有套件為最新版
  ```
  brew install 套件名稱
  ```
  安裝套件
  ```
  brew uninstall 套件名稱
  ```
  移除套件
  ```
  brew list
  ```
  查看所有已安裝的套件名稱
  ```
  brew list 套件名稱
  ```
  查看已安裝的套件，所有相關的檔案和位置
  ```
  brew info 套件名稱
  ```
  查看該套件的相關說明
  ```
  brew versions 套件名稱
  ```
  查看該套件，可以安裝的套件版本，和切換版本的 command
  ```
  brew switch 套件名稱 版本
  ```
將目前的套件切換成指定的版本 (重要)
brew home

直接跳到 homebrew 首頁
當安裝完成後，也請檢查 ~/.profile 檔案，確定系統會預先執行 brew 安裝的套件
更新方式如下：

# vim ~/.profile

找到 export PATH=xxx (註4) 的該行，增加 /usr/local/bin: 在 PATH= 的最前面，即該行會變成
export PATH=/usr/local/bin:xxx

確定後存檔離開，並且鍵入以下的命令，確保剛才的修改可以立即執行
# source ~/.profile
