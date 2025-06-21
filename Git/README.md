# Git

> 以下說明如何在 WSL2 環境下操作 Git。

## 初始化 

```bash
# 安裝 git
sudo apt install -y git 
#配置 username 和 email（請將 <your name> 和 <your email> 替換為你的個人資訊）
git config --global user.name "<your name>"
git config --global user.email "<your email>"
#查看使否配置成功
git config --list 
```

## 