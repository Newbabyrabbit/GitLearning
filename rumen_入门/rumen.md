# 简单入门  

**基础操作**
1. 创建版本库  -> `git init`
2. 明确哪些文件将要被纳入到下次提交 -> `git add xxx`
3. 提交，将 `git add` 后的文件纳入版本库 -> `git commit`
4. 检查状态 -> `git status`
5. 从版本库中删除被跟踪文件(*也会从本地删除*) -> `git rm xxx`
6. 显示提交历史 -> `git log --oneline`

**Git的协作功能**  
1. 克隆版本库 -> `git clone 源A 目标B`
2. 在B(克隆版本)中获取A的修改提交 -> `git pull`
3. 从任意版本库中取回修改 -> `git pull 其他版本库 master`
4. 创建共享版本库 -> `git clone --bare 源 目标`  

共享版本库可被用来充当开发者传递提交的汇聚点，方便别人拉取(相当于中间站)