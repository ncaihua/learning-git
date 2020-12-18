git is a version control system.
git is free software.
I learning git.
learn git diff.
learn git status.

git reset --hard HEAD^
一次commit就相当于是一次快照，多次commit就会形成多个快照，通过git log 查看commit几次，有几个快照；一个快照的信息如下：
commit 67c2410c281b2a11e242287f67510aa15812a175 (HEAD -> master) ----每次提交的生成的一个唯一的版本号id，整个git仓库唯一；
Author: WhiteOrCloud.mall <ncaihua@163.com>   ----提交人
Date:   Thu Dec 17 17:09:37 2020 +0800  ------提交时间

    add tow lines text   ---每一次提交的-m后面的参数，就是提交说明

在git中HEAD表示当前版本，就是最后一次commit的版本
HEAD^表示上一个版本，HEAD^^表示上两个版本 哈哈哈哈，如果要回退到前100个版本，岂不是要是HEAD后面跟100个^，不现实，那么就有另一种方案，HEAD~xxx,就会退回到xxx版本；
其实还有一种方案，通过commit id的值，回退到具体的某一次快照，就是具体的某一次提交的版本，git reset --hard commitid，而且commitid没有必要写全，只要写前面的5-8位，git会自动到版本库中找；
