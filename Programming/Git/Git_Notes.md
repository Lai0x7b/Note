# Git

以下說明如何在 WSL2 環境下操作 Git。

## 1. Git 是什麼?

Git 是一個分散式版本控制系統，用來追蹤檔案的變更歷史，讓你可以:

- 回到過去某個狀態
- 同步多人協作的代碼
- 測試新功能又不怕壞掉主專案

## 2. 各種專有名詞解釋

- **Branch (分支)**  是 Git 中用來隔離開發工作的機制，可以理解成一個獨立的開發線，讓每個人或每個功能都能在自己的分支上進行修改，互不影響主分支 (如 main)，等到開發完成並測試無誤後再合併 (merge) 回主分支，這樣可以協助多人協作並有效避免代碼衝突。
- **Origin**  Git 預設的遠端儲存庫名稱，當執行 clone 時，系統會自動將 Github Repository 命名成 Origin ，可以使用 git remote -v 查看

## 3. 初始化

```bash
#安裝 git
sudo apt install -y git 
#配置 username 和 email(請將 <your name> 和 <your email> 替換為你的個人資訊)
git config --global user.name "<your name>"
git config --global user.email "<your email>"
#查看是否配置成功
git config --list 
```

## 4. 對 Remote Repository 和 Local Repository 進行版控

### 4.1 已經從 Github 網頁建立了 Remote Repository

```bash
#Clone Remote Repository  
git clone https://github.com/example/example.git
#建立索引
git add . 
#commit 至 Local Repository，雙引號中可填寫提交訊息
git commit -m "test"  
#推送至指定 branch 
git push origin main 
```

### 4.2 從現有的目錄中進行版控

```bash
#初始化 Git 儲存庫
git init 
#建立索引
git add . 
#commit 至 Local Repository，雙引號中可填寫提交訊息
git commit -m "test"  
#推送至指定 branch 
git push origin main 
```

## 5. Branch(分支)操作

```bash
#建立一個名為patch/1.1.1的branch 
git branch patch/1.1.1 
#切換branch 
git checkout patch/1.1.1 
#建立並切換branch 
git checkout -b patch/1.1.1 
#刪除Local Repository中的branch，需先切換到另一個branch 
git checkout main 
git branch -d patch/1.1.1 
#刪除Remote Repository中的branch 
git push origin --delete patch/1.1.1 
#合併branch 

#查看所有branch 
git branch -a 
```

## Git 查看命令

```bash
#查看目錄的狀態
git status 
#查看Repository名稱
git remote -v 
#查看所有branch
git branch -a 
```

## Reference ##

