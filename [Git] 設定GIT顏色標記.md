##設定Git顏色標記

![DEMO](https://github.com/webber0928/History/blob/master/images/git_color.png)

1.打開 Git 的 color 顏色設定，這樣 Git 指令的輸出結果才會加上顏色，像是 git status 等：

```bash
git config --global color.ui true
```

2.設定你偏好的文字編輯器和 diff 工具

```bash
git config --global core.editor
git config --global merge.tool opendiff
```

3.最後，我個人喜歡以下的 alias：
```bash
git config --global alias.co checkout
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.br branch
```
**這樣只要輸入 git st 就是 git status 了。**

FYI，以上 git 設定檔的位置在` ~/.gitconfig`，你也可以直接修改這個檔案。
