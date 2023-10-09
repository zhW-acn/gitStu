# 基础
1. commit：提交记录
    使用`git commit`会使main分支和HEAD指针指向新的分支
2. branch：新建分支
    使用`git branch bugFix`创建一个名为bugFix的分支，<br>
    commit提交之后，**Attention**这会使main分支和HEAD指针前进，而新建的分支留在上一个提交记录。
3. checkout：跳转分支（HEAD）
    使用`git checkout bugFix`后HEAD指针会跳转到bugFix分支上，<br>
    如果想创建一个新的分支同时切换到新创建的分支的话，可以通过`git checkout -b <branch-name>`来实现。
4. merge：合并两个分支
    使用`git merge <branch-name>`把目标分支归并到当前分支上，并提交
5. rebase：合并两个分支，创造更线性的提交历史
    使用`git rebase <branch-name>`把把目标分支归并到当前分支上，并提交

# 进阶
1. 分离HEAD
    HEAD 是一个对当前所在分支的符号引用 ： 也就是指向你正在其基础上进行工作的提交记录。

    HEAD 总是指向当前分支上最近一次提交记录。使用`git checkout <batch-name>`使HEAD指向分支。把HEAD从main分离出
2. 相对引用
    其实分离HEAD用checkout+batch-name在git中移动不太方便，因为指定提交记录的hash值基于SHA-1，40位。<br>
    虽然git只需你能提供能够唯一标识提交记录的前几个字符即可，而不是整个hash值。使用`git log`查看提交记录的hash值。
    这时候相对引用的概念出现了。<br>
    使用`^`向上移动一个提交记录，使用`~num`向上移动多个：eg:`~3`向上移动三个