##[XCode] build environment

XCode 是 MacOSX 所使用的整合開發環境(IDE) ，不過，其實我們未必要完整安裝 XCode 套件，而是要安裝 command line 的 build environment，通常可以在「終端機」(註1)(註2) 中鍵入以下的命令安裝：

```bash
# xcode-select --install 
```

則會自動跳出安裝對話框 window，根據一部一部的設定，即可以輕鬆安裝 command line 的 build environment (註3)

**備註**
1. 終端機的位置在於 「應用程式」 -> 「工具程式」 -> 「終端機」
2. 也可以選擇 iTerm2 (個人偏好推薦)
3. 通常 Mac 內建 C compiler 包含 cc 和 clang(LVM)，預設通常會使用 clang 做為期預設的 C compiler，也不需要特意去裝 gcc
