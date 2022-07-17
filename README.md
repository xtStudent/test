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
1. 优点：每个节点都是严格按照时间排列。当合并发生冲突时，只需要解决两个分支所指向的节点的冲突即可
2. 缺点：合并两个分支时大概率会生成新的节点并分叉，久而久之提交历史会变成一团乱麻
- git rebase 分支名/节点哈希值
与merge不同的是rebase合并看起来不会产生新的节点（实际上是会产生的，只是做了一次复制）
1. 优点：会使提交历史看起来更加线性、干净
2. 缺点：虽然提交看起来像是线性的，但并不是真正的按时间排序, 并且当合并发生冲突时，理论上来讲有几个节点rebase到目标分支就可能处理几次冲突
- git cherry-pick 分支名1/节点哈希值, 分支名2节点哈希值
选择某几个节点进行合并

# 回退相关
- git checkout 节点哈希值
- git checkout --detach
直接脱离分支指向当前节点
- git checkout 分支名/HEAD^
HEAD分离并指向前一个节点
- git checkout 分支名~N
HEAD分离并指向前N个节点
- git commit --amend -m '更改后的commit信息'
修改提交信息
- git reset HEAD~N
回退N个提交
