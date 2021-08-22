<div style="text-align:center"><img src="https://git-scm.com/images/logos/1color-lightbg@2x.png" width="300"/></div>

# Git常見指令

## Git安裝
| Linux  | 說明 |
| ------------- |:-------------:|
|sudo yum install git|安裝Linux（Fedora）|
|sudo apt-get install git|安裝Linux（Ubuntu / Debian）|
|sudo add-apt-repository ppa:git-core/ppa<br>sudo apt-get update<br>sudo apt-get install git|更新Linux（Ubuntu / Debian）|

| Mac  | 說明 |
| ------------- |:-------------:|
|brew install git|安裝Mac|
|brew upgrade git|更新Mac|

| Windows  | 說明 |
| ------------- |:-------------:|
|git update-git-for-windows|更新|

## Git設置
| 操作  | 說明 |
| ------------- |:-------------:|
|git config|檢視指令|
|git config --system --list|系統專用設定值 `C:/Program Files/Git/etc/gitconfig`|
|git config --global --list|帳號專用設定值 `C:/Users/user/.gitconfig`|
|git config --list|倉庫專用設定值 `project/.git/config`|
|git config user.name "\<name>"|設置使用者名稱|
|git config user.email "\<email>"|設置使用者郵件|
|git config user.signingkey \<key>|設置GPG密鑰簽署|
|git config core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst"|設置 Notepad++ 編輯器|
|git config \<key>|檢視設定值|
|git config --unset \<key>|刪除設定值|
|git config alias.\<v> \<verb>|設置別名|
|git config --unset alias.\<v>|刪除別名|
|git config commit.template \<path>|設置commit模板 `.gitmessage.txt`|
|git config core.autocrlf true|設置不同系統字元、分行符號問題
|git config core.whitespace=fix|設置自動修復空白字元問題|
|git config rerere.enabled true|設置簡化衝突（Merge & Rebase）|
|git config commit.gpgsign true|設置GPG密鑰自動啟用|
|git config receive.fsckObjects true|設置git發送時確保沒有引入破壞性資料|
|git config credential.helper cache|設置HTTP憑證儲存|

## Git資訊
| 操作  | 說明 |
| ------------- |:-------------:|
|git version|檢視版本|
|where git|安裝路徑|
|git \<verb> --help|檢視說明|

## Git基礎
| 操作  | 說明 |
| ------------- |:-------------:|
|git init|初始化專案|
|git status|檢視目前狀態|
|git status -s|簡潔檢視目前狀態|
|git add \<file>|追蹤新檔案|
|git add .|追蹤全部檔案|
|git restore --staged \<file>|取消已暫存檔案|
|git reset HEAD|取消已暫存的所有檔案|
|rm \<file>|取消已修改檔案（新建檔案）|
|git restore \<file>|取消已修改檔案（已進 .git 保存檔案）|
|git mv \<file_from> \<file_to>|移動檔案|

## Git差異
| 操作  | 說明 |
| ------------- |:-------------:|
|git diff|檢視已進.git檔案未暫存的變更|
|git diff --staged|檢視已修改的變更|
|git diff --check|檢視未暫存區存在的空白錯誤|
|git diff \<current_branch>...\<target_branch>|顯示分支差異點|

## Git遞交
| 操作  | 說明 |
| ------------- |:-------------:|
|git commit|進入編輯器並輸入資訊於遞交中|
|git commit -m "\<desc>"|遞交變更並帶入輸入資訊於遞交中|
|git commit -v|檢視遞交暫存區前差異|
|git commit -am "\<desc>"|已修改 & 已暫存的所有檔案 commit|
|git commit --amend|遞交暫存區至上一次遞交|
|git commit -m "\<desc>" --amend|取消操作並重新修改 commit 名|
|git commit -S  -m "\<desc>"|簽署遞交|

## Git紀錄#
| 操作  | 說明 |
| ------------- |:-------------:|
|git log|檢視遞交歷史|
|git log -p|檢視遞交差異|
|git log -\<count>|僅檢視最新 count 筆遞交|
|git log --stat|檢視遞交和簡要統計資訊|
|git log --shortstat|上述--stat輸出包含（已更改 / 新增 / 刪除）統計資訊|
|git log --name-only|檢視遞交歷史並顯示有被更改的檔案|
|git log --name-status|上述 --name-only 輸出包含（已更改 / 新增 / 刪除）統計資訊|
|git log --abbrev-commit|檢視遞交歷史並簡短顯示 SHA-1 值|
|git log --relative-date|檢視遞交歷史並顯示相對日期|
|git log --pretty=\<verb>|依據變數檢視不同輸出格式之遞交（oneline / shoort / full / fuller）|
|git log --pretty=format:"\<format>"|自訂輸出格式檢視遞交|
|git log --graph|ASCII基本圖表檢視遞交|
|git log --since=\<date>|檢視指定日期之後的遞交（date = 2021-01-01）|
|git log --until=\<date>|檢視指定日期之前的遞交（date = 2021-01-01）|
|git log --author="\<name>"|檢視依名查詢相關遞交|
|git log --committer \<string>|檢視指定相符字串遞交 |
|git log --grep="\<keyword>"|檢視依關鍵字查詢相關遞交|
|git log --author="\<name>" --committer \<string> --all-match|檢視依多條件查詢相關遞交|
|git log -S\<string>|檢視僅輸出更改的字串的遞交|
|git log --decorate|檢視指向提交的物件（blob 物件 / 樹物件）|
|git reflog|檢視操作紀錄檔|
|git grep \<keyword>|檢視搜尋字串|

## Git遠端
| 操作  | 說明 |
| ------------- |:-------------:|
|git clone \<url>|複製遠端倉庫|
|git clone \<url> \<storehouse>|複製遠端倉庫並重新命名專案於本地端|
|git clone --bare \<url>|複製 .git 檔案|
|git fetch \<remote>|擷取遠端倉庫資料|
|git pull \<remote> \<branch>|擷取遠端倉庫指定分支並合併資料|
|git push \<remote> \<branch>|發送本機倉庫指定分支並合併資料|
|git remote|顯示遠端倉庫|
|git remote -v|顯示遠端倉庫 & 對應的URL|
|git remote add \<remote_name> \<url>|增加遠端倉庫|
|git remote show \<remote>|查看遠端倉庫資訊|
|git remote rename \<old_remote> \<new_remote>|重新命名遠端倉庫|
|git remote rm \<remote>|刪除遠端倉庫|

## Git標籤
| 操作  | 說明 |
| ------------- |:-------------:|
|git tag|列舉標記|
|git tag -l "\<name>*"|列舉特定標記|
|git tag -a \<tag> -m "\<desc>"|註釋標籤|
|git tag \<tag>|輕量標籤|
|git tag -a \<tag> \<SHA-1>|補加標籤|
|git tag -d \<tag>|刪除本地標籤|
|git tag -s \<tag> -m "\<desc>"|簽署標籤|
|git show \<tag>|顯示標籤資訊|
|git checkout -b \<branch_name> \<tag>|檢出標籤（特定標籤上新增分支）|
|git push \<remote> \<tag>|單一共用標籤（上傳標籤）|
|git push \<remote> --tags|複數共用標籤（上傳標籤）|
|git push \<remote> --delete tag \<tag>|刪除遠端標籤|

## Git分支
| 操作  | 說明 |
| ------------- |:-------------:|
|git branch \<branch>|新建分支|
|git branch -d \<branch>|刪除分支|
|git branch -v|檢視目前所在分支|
|git branch --merged|檢視已合併過的分支|
|git branch --no-merged|檢視未合併的分支|
|git branch -u \<remote>/\<branch>|更改遠端追蹤分支|
|git branch -vv|檢視本機分支設定的遠端分支資訊|
|git checkout \<branch>|切換分支|
|git checkout -b \<branch>|新建並切換分支|
|git checkout -b \<branch> \<remote>/\<branch>|新建本機端對應遠端的追蹤分支|
|git checkout --track \<remote>/\<branch>|新建本機端對應遠端的追蹤分支|
|git push \<remote> --delete \<branch>|刪除遠端分支|

## Git合併
| 操作  | 說明 |
| ------------- |:-------------:|
|git merge \<branch>|合併分支|
|git merge @{u}|合併遠端分支|

## Git變基#
| 操作  | 說明 |
| ------------- |:-------------:|
|git rebase \<target_branch>|基本變基合併|
|git rebase --onto \<target_branch> \<center_branch> \<rebase_branch>|衍生變基合併|
|git rebase \<target_branch> \<rebase_branch>|變基合併|
|git pull -rebase|遠端commit執行變基導致替換，需重新擷取commit點|
|git cherry-pick <SHA-1>|揀選需要的紀錄作為合併主分支中（似 rebase）|
|git rebase -i HEAD~\<n>|修改多個遞交資訊|

## Git重置
| 操作  | 說明 |
| ------------- |:-------------:|
|git reset --soft|前往遞交保留當前工作樹內容以及遞交間差異內容存於已暫存區|
|git reset --mixed|前往遞交保留當前工作樹內容以及遞交間差異內容存於已修改區|
|git reset --hard|前往遞交並清除所有工樹內容|

## Git儲藏
| 操作  | 說明 |
| ------------- |:-------------:|
|git stash list|檢視所有存取stash|
|git stash|儲存未遞交的更動（已追蹤的檔案）|
|git stash -u|儲存未遞交的更動（所有檔案）|
|git stash --keep-index|儲存已修改區的更動|
|git stash apply stash@{n}|恢復儲存至已修改區|
|git stash apply --index stash@{n}|恢復儲存|
|git stash drop stash@{n}|刪除儲存|
|git stash clear|刪除全部儲存|
|git stash pop|恢復儲藏並刪除|

## 生產SSH金鑰 [Docs](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/about-ssh)
> 1. 執行 `cd ~/.ssh` （前往ssh文件）
> 1. 執行 `ls`
>   * id_rsa.pub - 公鑰
>   * id_rsa - 私鑰
> 1. 執行 `ssh-keygen`（生產ssh密鑰）
>   1. Enter file in which to save the key `Enter`
>   1. Overwrite (y/n)? `y`
>   1. Enter passphrase (empty for no passphrase) `Enter`
>   1. Enter same passphrase again `Enter`
> 1. 執行 `cat ~/.ssh/id_rsa.pub`（取得公鑰）

## GPG密鑰 [Docs](https://docs.github.com/en/github/authenticating-to-github/managing-commit-signature-verification/about-commit-signature-verification)
生產GPG密鑰
> 1. 執行 `gpg --list-keys` （檢查有無GPG密鑰）
> 1. 執行 `gpg --full-generate-key` （生產GPG密鑰）
>  1. Please select what kind of key you want `Enter`
>  1. What keysize do you want? `4096`
>  1. Key is valid for? `Enter`
>  1. Is this correct? `y`
>      * Real name `<Name>`
>      * Email address `<Email>`
>      * Comment `<Name> <Email>`
>  1. Change (N)ame, (C)omment, (E)mail or (O)kay/(Q)uit? `O`
>  1. Please enter the passphrase to protect your new key `<Password>`
> 1. 執行 `gpg --list-secret-keys`　（獲取指紋）
> 1. 執行 `gpg --armor --export <key>` （獲取公鑰）

刪除GPG公鑰
> `gpg --delete-keys <Name>`

刪除GPG私鑰
> `gpg --delete-secret-keys <Name>`
