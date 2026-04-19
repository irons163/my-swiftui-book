# GitHub 上傳指令清單

這份文件是給這個專案第一次上 GitHub 時直接照著做的操作清單。預設情境是：

- 你目前在本機資料夾 `/Users/phil/Documents/my-swiftui-book`
- 這個資料夾還沒有初始化成 git repository
- 你要先把它推到一個全新的 GitHub repository

## 0. 第一次用 Git 的話，先設定身份

如果你之前從來沒有在這台電腦用過 Git，先設定一次名字與 Email：

```bash
git config --global user.name "你的名字"
git config --global user.email "you@example.com"
```

可以用下面這兩行檢查是否設定成功：

```bash
git config --global user.name
git config --global user.email
```

## 1. 進到專案資料夾

```bash
cd /Users/phil/Documents/my-swiftui-book
```

## 2. 初始化本機 git repository

```bash
git init
git branch -M main
git status
```

做完之後，你應該會看到目前有很多尚未追蹤的檔案，這是正常的。

## 3. 把目前專案加入版本控制

```bash
git add .
git status
```

在 `git status` 裡確認沒有不想提交的檔案之後，再建立第一個 commit：

```bash
git commit -m "Initial manuscript structure"
```

## 4. 在 GitHub 建立一個空的 repository

到 GitHub 網站建立新 repository，建議：

- Repository name: `my-swiftui-book`
- Visibility: 依你的需求選 `Public` 或 `Private`
- 不要勾選 `Add a README file`
- 不要勾選 `Add .gitignore`
- 不要勾選 `Choose a license`

這一步的重點是：遠端 repo 要是空的，這樣第一次 push 最乾淨。

## 5. 把本機 repo 連到 GitHub remote

如果你用 HTTPS：

```bash
git remote add origin https://github.com/<你的 GitHub 帳號>/my-swiftui-book.git
git remote -v
```

如果你用 SSH：

```bash
git remote add origin git@github.com:<你的 GitHub 帳號>/my-swiftui-book.git
git remote -v
```

`git remote -v` 的目的是確認 `origin` 已經指到你剛建立的 GitHub repo。

## 6. 第一次 push 到 GitHub

```bash
git push -u origin main
```

成功之後，之後只要在同一個分支工作，直接用 `git push` 就可以了。

## 7. 上傳完成後檢查

可以再跑一次：

```bash
git status
git log --oneline -n 3
```

這時候通常會看到：

- `working tree clean`
- 最新一筆 commit 是 `Initial manuscript structure`

然後回到 GitHub 頁面重新整理，就會看到整個專案已經上去。

## 最短版指令清單

如果你已經知道自己在做什麼，最短版就是這一串：

```bash
cd /Users/phil/Documents/my-swiftui-book
git init
git branch -M main
git add .
git commit -m "Initial manuscript structure"
git remote add origin https://github.com/<你的 GitHub 帳號>/my-swiftui-book.git
git push -u origin main
```

## 之後每次更新 GitHub

第一次 push 完之後，往後通常只要這三步：

```bash
git add .
git commit -m "更新書稿內容"
git push
```

如果你想先檢查目前變更，再決定要不要提交，可以先跑：

```bash
git status
```

## 常見問題

### 1. `Author identity unknown`

代表 Git 還不知道你是誰，先補這兩行：

```bash
git config --global user.name "你的名字"
git config --global user.email "you@example.com"
```

### 2. `remote origin already exists`

代表你之前已經設定過 remote。可以先檢查：

```bash
git remote -v
```

如果網址設錯了，再改成正確的：

```bash
git remote set-url origin https://github.com/<你的 GitHub 帳號>/my-swiftui-book.git
```

### 3. `rejected` 或遠端已經有內容

通常是你在 GitHub 建 repo 時，多勾了 README、`.gitignore` 或 license，導致遠端不是空的。

最簡單的處理方式通常是：

- 刪掉那個 GitHub repo
- 重新建立一個空的 repo
- 再重新跑第 5 步與第 6 步

### 4. 我想用 GitHub CLI，一步建 repo 並 push

如果你已經安裝 [`gh`](https://cli.github.com/)，也可以在完成本機第一個 commit 後直接跑：

```bash
gh repo create my-swiftui-book --source=. --remote=origin --push
```

如果想指定 private：

```bash
gh repo create my-swiftui-book --private --source=. --remote=origin --push
```

## 補一句

這個專案已經有：

- `.gitbook.yaml`
- `docs/` GitBook 發布結構
- `docsify` 本機預覽頁

所以當你 push 到 GitHub 之後，就可以直接接 GitBook 的 GitHub Sync。
