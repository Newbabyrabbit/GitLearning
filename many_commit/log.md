# 关于暂存区的二三事 

提交分为两个步骤：
1. add  将相关修改纳入到暂存区
2. commit 将暂存区的内容提交到版本库

**status命令**  

该命令可以查看工作区和暂存区中各文件的状态：
1. `changes to be commited` 已被add，即将被commit
2. `changes not staged for commit` 修改了，但是没有被add（之前被add过）
3. `untracked files` 从来没有被add过的文件，即未被跟踪

**快照**  

暂存区不仅要存储修改所发生的位置，还要存储修改的内容，add命令就是给相关文件拍了一张快照   
例如：`git diff --staged` 比较当前的HEAD提交和此时暂存区的差异   
单纯的 `git diff` 是查看暂存区与工作区（未被add的本地修改）的不同之处   

**从暂存区中撤回修改**  

`git reset 重置到哪个版本 被重置的文件或目录(可选)`  
例如：`git reset HEAD foo.txt`  
在重置过程中，暂存区会被重写，但如果add后又被修改了，就不能使用reset重置了。   

**stash储藏**  
当项目进行到一定的程度时，如果我们发现自己要快速修复某个问题，可以先不提交正在做的事，转而去处理相关修复，此时我们可以执行 stash  命令，将工作区和暂存区中的修改保存在储藏栈中，日后处理。
1. `git stash`   
2. `git stash pop` 恢复储藏栈顶的操作
3. `git stash list` 查看储藏栈
4. `git stash pop stash@(0)` 指定要恢复的储存栈操作