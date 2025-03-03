---
title: 一些常用的指令
publishDate: 2025-02-01
updatedDate: 2025-02-12
description: 因为一些指令比较常见，所以写一篇博客记录一下，以在将来方便同步。
heroImage: {src : "thumbnail.webp", color: '#E29CEE' }
category: 'Tech Talk'
pixivLink: '126490750'
tags:
    - 'Tech Talk'
---

## ZSH 配置

首先可以安装 zsh 和 oh-my-zsh

```bash
sudo apt update
sudo apt install zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

为了兼容主题，接下来安装字体

```bash
wget https://github.com/ryanoasis/nerd-fonts/releases/download/v3.3.0/JetBrainsMono.zip -O JetBrainsMono.zip
unzip JetBrainsMono.zip -d JetBrainsMono
mkdir -p ~/.local/share/fonts/JetBrainsMono
cp JetBrainsMono/*.ttf ~/.local/share/fonts/JetBrainsMono/
fc-cache -fv
```

安装完插件之后就可以修改命令行中的字体选项了，找到安装的字体并设定。


<div class="flex justify-center my-4">
    <img src="https://pic.axi404.top/image.45hryie6yz.webp" class="rounded-lg shadow-md max-w-xl w-full" />
</div>

接下来安装插件：

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

修改配置文件：

```bash title="~/.zshrc"
ZSH_THEME="powerlevel10k/powerlevel10k"
plugins=(z git zsh-autosuggestions zsh-syntax-highlighting)
```

结束。

## Docker 初始化

首先先安装 docker

```bash
curl -fsSL get.docker.com -o get-docker.sh
sudo sh get-docker.sh --mirror Aliyun
```

安装完成之后，可以初始化 docker 服务并且添加用户组：

```bash
sudo systemctl enable docker
sudo systemctl start docker
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
```

结束。

## Windows 安装 Torch

直接使用 pip 安装即可，需要指定 CUDA 版本：

```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
```

结束。

## Miniconda 安装

参考 [Miniconda 文档](https://www.anaconda.com/docs/getting-started/miniconda/install)：

```bash
mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm ~/miniconda3/miniconda.sh
```

结束。