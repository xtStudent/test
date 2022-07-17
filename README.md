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

# 远程相关
- git clone 仓库地址
- git fetch 远程仓库地址/分支名
将远程新增加的节点以及引用（分支/HEAD）的状态下载到本地
- git pull 远程分支名 / git pull --rebase 远程分支名
从远程仓库的某个引用拉取代码
- git push 远程分支名
将本地提交推送至远程

# 总结
- 不管是HEAD还是分支，它们都只是引用而已，引用+节点是 Git 构成分布式的关键
- merge相比于rebase有更明确的时间历史，而rebase会使提交更加线性应当优先使用
- 通过移动HEAD可以查看每个提交对应的代码
- clone或fetch都会将远程仓库的所有提交、引用保存在本地一份
- pull的本质其实就是fetch+merge，也可以加入--rebase通过rebase方式合并


参考：微信公众号-前端技术江湖《轻松搞懂git各指令的本质，提升git 内功》

链接：https://mp.weixin.qq.com/s/ns9agK5mn3bjFCfp4mvC7g



