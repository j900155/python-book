#2.1調用直譯器

Python的直譯器大多會裝在/usr/local/bin/python。如果放在/usr/local/bin/在你的Unix shell’s 會尋找讓它可以藉由命令去啟動。
```Bash
$ python
```

自從可以選擇直譯器的安裝位置，別的位置也是有可能的。檢查你的Python guru 或 system administrator。(E.g., /usr/local/python 是另一個可能的地方。)

在Windows中Python通常被安裝在C:\Python27或是你所選擇的地方。為了增加windows下的路徑直行以下的指令在命令提示字元中
```Bash
$ set path=%path%;C:\python27
```
輸入結束字元(Control-D on Unix, Control-Z on Windows)在直譯器的主要提示中會離開跟著zero exit狀態如過沒用試著輸入：　quit()。

在直譯器中逐行寫入是非常複雜的。然而在Unix中直譯器安裝了 GNU readline 的函式庫
，增加了更多精巧的交互編輯和歷史記錄功能。也許最快確認終端機使否能夠編輯的方法是Control-P　的第一個Python提示。如果它beeps，那終端機使是能夠編輯
If it beeps, you have command line editing; see Appendix Interactive Input Editing and History Substitution for an introduction to the keys. If nothing appears to happen, or if ^P is echoed, command line editing isn’t available; you’ll only be able to use backspace to remove characters from the current line.