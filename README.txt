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

如果回退到了某个版本，或者回退多了，想恢复到最新版本或者之后的某个版本，就必须要知道commitid，怎么办呢？git提供了一个命令可以查看git执行的每一次命令；git reflog：
6df4f2d (HEAD -> master) HEAD@{0}: commit: git log git reset --hard HEADAD^ or git reset --hard HEAD~xxx and git reset commitid
67c2410 HEAD@{1}: reset: moving to HEAD^
994f1f6 HEAD@{2}: reset: moving to HEAD
994f1f6 HEAD@{3}: commit: git log 命令查看commit记录
67c2410 HEAD@{4}: commit: add tow lines text
b3748de HEAD@{5}: commit: add a line text
73174a6 HEAD@{6}: commit (initial): wrote a readme.txt file

就可以找到具体的某一次的commitid 然后想回到那个版本都是可以的  git reset --hard commitid；


git inti 的时候 git会为我们创建index(暂存区)和版本库，而且在版本库中创建一个master分支，和一个HEAD的指针指向master分支；
git add . 就是把对文件的更改添加到暂存区
git commit 就是把暂存区的内容添加到本地仓库中，就是把当前暂存区的内容做了一个快照保存了下来，以便将来回退；


如果对工作区中的文件的修改想撤销，有两种情况：
1.暂存区是干净的，工作区中的修改手动修改成和版本库中一致  也可通过git checkout -- filename 把版本库中的内容覆盖到工作区中  
2.暂存区中已经添加了该文件，手动的修改成和暂存区中的一致  也可以通过git checkout -- filename 把暂存区的内容覆盖到工作区中

总之：git checkout -- filename 之后工作区就会和最后一次git add git commit之后的内容一致；git checkout命令后面的--很重要，没有--就表示要切换到另一个分支
