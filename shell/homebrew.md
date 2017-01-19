# Homebrew 配置

## 替换为中科大源
```shell
// 替换 brew.git:
cd "$(brew --repo)"
git remote set-url origin https:://mirrors.ustc.edu.cn/brew.git

// 替换 homebrew-core.git:
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://mirrors.ustc.edu.cn/homebrew-core.git

// 替换 homebrew-bottles 镜像
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.ustc.edu.cn/homebrew-bottles' >> ~/.zshrc
source ~/.zshrc
```

## 替换为清华源
```shell
// 替换 brew.git:
cd "$(brew --repo)"
git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git

// 替换 homebrew-core.git:
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git


// 替换 homebrew-bottles 镜像
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles' >> ~/.zshrc
source ~/.zshrc
```

## 重置
```shell
// 重置 brew.git:
cd "$(brew --repo)"
git remote set-url origin https://github.com/Homebrew/brew.git

// 重置 homebrew-core.git:
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://github.com/Homebrew/homebrew-core.git

// 注释 .zshrc 里 homebrew-bottles 镜像
source ~/.zshrc
```
