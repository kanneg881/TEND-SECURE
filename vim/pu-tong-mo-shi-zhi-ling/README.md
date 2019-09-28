# 普通模式指令

## 搜尋

向右搜尋游標行的 char 字元  
`f{char}`

搜尋下一個之前輸入的 f{char}  
`;`

搜尋上一個之前輸入的 f{char}  
`,`

正向搜尋當前游標後第一個非空白單字，等同於 `/\<keyword\>`  
`*`

反向 `*` 搜尋，等同於 `?/\<keyword\>`  
`#`

類似 `*` 搜尋，等同於 `/keyword`  
`g*`

類似 `#` 搜尋，等同於 `?keyword`  
`g#`

進入 `v` 可視模式，並選中下一個搜尋的匹配  
如果游標在匹配處的話，就選中當前游標的匹配  
`gn`

同 `gn` ，並選中上一個搜尋的匹配  
`gN`

等價於 `：s`（重複上次的替代）。注意這裡不記住旗標，所以實際工作方式可能不盡相同。  
`&`

等價於 `:%s//~/&` （在所有行上重複上次的替代，並使用相同的旗標，但使用前次的匹配模式）  
`g&`

`n` 跳轉到下一個匹配，如果是 `/` 搜尋則往下， `?` 搜尋則往上

`N` 與 `n` 反向跳轉到下一個匹配

`/` 或 `?` 搜尋完，下一次打 `/` 或 `?` 就會使用相同模式搜尋

輸入 `/` 或 `?` 按向上鍵 `<Up>` 就可以瀏覽之前搜尋紀錄

## 修改文字

切換大小寫  
`~`

刪除  
`d{motion}`

複製  
`y{motion}`

將文字轉換成大寫  
`gU{motion}`

從游標開始往後找的第一個數字加 count  
`[count]<Ctrl-a>`

從游標開始往後找的第一個數字減 count  
`[count]<Ctrl-x>`

## 重複指令

`.` 重複普通模式指令  
`@:` 重複上次的Ex指令  
`@@` 重複上次的@暫存器指令

## 切換模式

`i` 移動到游標左側切換插入模式  
`a` 移動到游標右側切換插入模式  
`I` 移動到最左側切換插入模式  
`A` 移動到最右側切換插入模式  
`c{motion}` 將 `{motion}` 刪除並進入插入模式  
`[count]s` 刪除 count 個字元並切換到插入模式  
`<Esc>` 離開其他模式到普通模式  
`:` 切換Ex命令模式  
`/` 切換搜尋模式，正向查找  
`?` 切換搜尋模式，反向查找  
`q/` 打開命令行窗口

切換可視模式，以字元為單位  
`v`

切換可視模式，以行為單位  
`V`

切換可視模式，並選取上次可視模式選取的內容  
`gv`

## 縮進

`zo` 打開縮進  
`zc` 關閉縮進  
`zr` 所有文件打開一層縮進  
`zm` 所有文件關閉一層縮進  
`zR` 打開所有縮進  
`zM` 關閉所有縮進  
`zn` 關閉縮進功能  
`zN` 啟動縮進功能  
`zi` 切換縮進功能（啟動和關閉）

## 暫存器

`q{0-9a-zA-Z"}`  
在暫存器 `{0-9a-zA-Z"}` 裡錄製鍵入的字元（大寫名字的暫存器表示附加鍵入的內容），結束錄製再按一次 `q`

`"{register}[motion]`  
對暫存器做對應的動作

## 其他

清除視窗並重新畫視窗  
`<Ctrl-l>`
