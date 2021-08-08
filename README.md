# Git操作說明

## Git設置
| 操作  | 說明 |
| ------------- |:-------------:|
|git config|檢視指令|
|git config --list|檢視設定|
|git config \<global_key>|檢視指定設定值|
|git config --global --unset \<global_key>|刪除指定設定值|
|git config --global user.name "\<name>"|設置使用者名稱|
|git config --global user.email "\<email>"|設置使用者郵件|
|git config --global core.editor "\<editorpath>"|設置編輯器|
|git config --global alias.\<v> \<verb>|設置別名|

## Git資訊
| 操作  | 說明 |
| ------------- |:-------------:|
|where git|安裝路徑（Window）|
|git version|版本|
|git update-git-for-windows|更新（Window）|
|git \<verb> --help|說明|

## Git基礎
| 操作  | 說明 |
| ------------- |:-------------:|
|git init|初始化專案|
|git status|檢視目前檔案狀態|
|git status -s|簡潔檢視目前檔案狀態|
|git add \<file>|追蹤新檔案|
|git add --all|追蹤全部檔案|
|git diff|檢視未暫存的變更|
|git diff --staged|檢視已暫存的變更|
|git diff --check|檢視遞交前存在的空白錯誤|
|get reset Head \<file>|取消已暫存的檔案|
|git rm --cached \<file>|已暫存檔案移出至未暫存區|
|git mv \<file_from> \<file_to>|移動檔案|

## Git遞交
| 操作  | 說明 |
| ------------- |:-------------:|
|git commit -v|遞交暫存區並將差異註記於遞交中（分支 / SHA-1 / 增減統計資訊）|
|git commit -m "\<desc>"|遞交變更並帶入輸入資訊於遞交中|
|git commit -am "\<desc>"|跳過暫存區將已修改過的所有檔案遞交|
|git commit --amend|重新遞交暫存區檔案至上一次遞交|
|git commit --amend --reset-author|重設上一次遞交的作者信息|
|git commit -m "\<desc>" --amend|取消操作並重新修改commit名|

## Git歷史紀錄
| 操作  | 說明 |
| ------------- |:-------------:|
|git log|檢視遞交歷史|
|git log -p|檢視遞交歷史並顯示遞交差異|
|git log -\<count>|檢視遞交歷史並只顯示最新count筆遞交|
|git log --stat|檢視遞交歷史並簡要統計資訊（改動檔案 / 幅度 / 數量 / 總計資訊）|
|git log --shortstat|上述--stat輸出包含（已更改 / 新增 / 刪除）統計資訊|
|git log --name-only|檢視遞交歷史並顯示有被更改的檔案|
|git log --name-status|上述 --name-only輸出包含（已更改 / 新增 / 刪除）統計資訊|
|git log --abbrev-commit|檢視遞交歷史並簡短顯示SHA-1值|
|git log --relative-date|檢視遞交歷史並顯示相對日期|
|git log --pretty=\<verb>|檢視遞交歷史並更改輸出格式（oneline / shoort / full / fuller）|
|git log --pretty=format:"\<format>"|檢視遞交歷史並自訂輸出格式|
|git log --graph|檢視遞交歷史並顯示ASCII基本圖表|
|git log --since=\<date>|檢視遞交歷史並指定日期之後的遞交（date = 2021-01-01）|
|git log --until=\<date>|檢視遞交歷史並指定日期之前的遞交（date = 2021-01-01）|
|git log --author="\<name>"|檢視遞交歷史並依名查詢相關遞交|
|git log --committer \<string>|檢視遞交歷史並指定相符字串的遞交 |
|git log --grep="\<keyword>"|檢視遞交歷史並依關鍵字查詢相關遞交|
|git log --author="\<name>" --committer \<string> --all-match|檢視遞交歷史並依多條件查詢相關遞交|
|git log -S\<string>|檢視遞交歷史並僅輸出更改的字串的遞交|

## Git遠端
| 操作  | 說明 |
| ------------- |:-------------:|
|git clone \<url>|複製遠端專案|
|git clone \<url> \<remote_name>|複製遠端專案並重命名專案於本地端|
|git remote|顯示遠端倉庫|
|git remote -v|顯示遠端倉庫 & 對應的URL|
|git remote add \<remote_name> \<url>|增加遠端倉庫|
|git remote show \<remote_name>|查看遠端倉庫資訊|
|git fetch \<remote_name>|擷取遠端倉庫資料|
|git pull \<remote_name>|擷取遠端倉庫至本機端並合併資料|
|git push \<remote_name>|發送本機倉庫至遠端並合併資料|
|git remote rename \<old_remote_name> \<new_remote_name>|重新命名遠端倉庫|
|git remote rm \<remote_name>|刪除遠端倉庫|

## Git標籤
| 操作  | 說明 |
| ------------- |:-------------:|
|git tag|列舉標記|
|git tag -l "\<tag_name>"|列舉一系列標記|
|git tag -a \<tag_name> -m "\<desc>"|註釋標籤|
|git show \<tag_name>|顯示標籤資訊|
|git tag \<tag_name>|輕量標籤|
|git tag -a \<tag_name> \<SHA-1>|補加標籤|
|git push \<remote_name> \<tag_name>|單一共用標籤|
|git push \<remote_name> --tags|複數共用標籤|
|git checkout -b \<branch_name> \<tag_name>|檢出標籤|
|git tag -d \<tag_name>|刪除本地標籤|
|git push \<remote_name> --delete tag \<tag_name>|刪除遠端標籤|















