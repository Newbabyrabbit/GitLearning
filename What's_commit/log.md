# 关于提交的理解  

**提交历史**  
1. 提交之间的差异比较
    1. `git diff 当前提交的散列值^!` 当前提交和上一次提交间的差异比较 
    2. `git diff --stat xxxA xxxB` --stat 显示两个文件中的修改数量
2. 显示提交历史
    1. `git log -n 3`  部分输出，显示最近三次提交
    2. `git log --oneline` 单行显示概述信息
    3. `git log --stat/--shortstat` 统计修改信息
        1. `--stat` 显示被修改的文件(文件名，有多少被修改文件，修改了几处)
        2. `--shortstat` 仅显示被修改了几处和被修改的文件的数量
    4. `git log --graph` 图显示