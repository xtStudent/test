# 提交相关
- git add 文件路径
添加某个文件到暂存区
- git add .
添加所有文件到暂存区
- git checkout -- 文件名
撤销工作区改动
- git reset HEAD 文件名
清空暂存区
- git commit -m '提交描述信息'
提交

# 分支相关
- git branch 
创建分支
- git checkout 分支名
切换分支
- git checkout -b 分支名
创建分支后立即切换到当前分支
- git branch -d 分支名

# 合并相关
- git merge 分支名/节点哈希值
将某个分支或者某个节点的代码合并至当前分支
- git rebase 分支名/节点哈希值
与merge不同的是rebase合并看起来不会产生新的节点（实际上是会产生的，只是做了一次复制）

