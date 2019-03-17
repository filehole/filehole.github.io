---
layout: post
title: 生成 Git SSH Key
categories: Git
description: 生成 Git SSH Key 的教程
keywords: Git, 教程
---

SSH Key 用来认证我们信任的设备，避免每次都需要重复输入密码。这个教程用来教大家生成自己的 SSH Key，同时将公钥添加到自己的 GitHub 账号。

* TOC
{:toc}

## Step1：检查已有的 SSH Keys

打开自己的 Git Bash，并输入以下命令：

'''sh
ls -al ~/.ssh
'''

查看是否已经存在 `public SSH Key`。

* id_dsa.pub
* id_ecdsa.pub
* id_ed25519.pub
* id_rsa.pub

## Step2: 生成新的 SSH Key

复制下面的命令，并替换其中的 `email` 为自己的账户，其他的可以用默认设置，不断点击 `Enter` 即可。

```sh
ssh-keygen -t rsa -C "your_email@example.com"
```

生成好后你将可以看到如下返回。

```sh
Your identification has been saved in /c/Users/your_account/.ssh/id_rsa.# Your public key has been saved in /c/Users/your_account/.ssh/id_rsa.pub.# The key fingerprint is:# 01:0f:f4:3b:ca:85:d6:17:a1:7d:f0:68:9d:f0:a2:db your_email@example.com
```

然后将生成好的 `key` 添加到 `ssh-agent`：

```sh
eval $(ssh-agent -s)
> Agent pid 59566
ssh-add ~/.ssh/id_rsa
```

## Step3：添加 SSH Key 到自己账户

执行下面命令，当然你可以打开文件手动复制里面的内容。

```sh
clip < ~/.ssh/id_rsa.pub
```

进入 GitHub 中的 Settings，点击 SSH Keys，进行添加，Add SSH Key。

![SSH Key](https://filehole.github.io/images/posts/git/git-ssh-key.png)

到这里自己的 SSH Key 就应该设置好了，当然也可以用以下命令来验证设置。

```sh
ssh -T git@github.com
```
