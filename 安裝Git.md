##安裝Git

安裝 git git 是我們目前所使用的版本控制的工具，所以必須要安裝正確的 git 以確保我們可以正確的 pull/fetch code 或是 push code，由於 Mac 預設安裝的是 1.8.x 版本，我們必須安裝成 1.7.x 版，可以使用以下的命令安裝：

安裝 git
```
# brew install git
```
通常會安裝 1.8.x 甚至 1.9.x 版，所以我們必須更改成 1.7.x 版
檢查最新版的 1.7 版本的版號
```
# brew versions git
```
找到 1.7.x 版號最大的數字，假如是 1.7.12.4 (請勿照抄，根據實際情況修改)
若其資訊為
```
...
1.7.12.4 git checkout 7f1a8c0 Library/Formula/git.rb
...
```
則先複製 git checkout 7f1a8c0 Library/Formula/git.rb 此段字串

進入 brew 路徑
```
# cd `brew --repository`
```
更改 git 版本至 1.7.12.4 並且安裝正確版本
```
# git checkout 7f1a8c0 Library/Formula/git.rb
# brew install git
```
檢查是否 git 已經成為正確版本
```
# git --version
```
如此即可成功改成 1.7.12.4 版
萬一之後又被改成其他版本，則必須手動改成正確版本
```
# brew switch git 1.7.12.4
```
