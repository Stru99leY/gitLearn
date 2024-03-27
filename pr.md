# 在vscode中

1. 首先得有两个分支,比如master和dev,首先在clone仓库后，在本地使用命令"`git checkout -b localBranch origin/dev` 使用新的分支。解释指令:
创建新分支 (-b localBranch): 使用 -b 选项告诉 git checkout 命令创建一个名为 localBranch 的新本地分支。这将在您的本地 Git 仓库中生成一个新的分支指针，它开始时指向与执行该命令时相同的提交（即当前所在分支的 HEAD 指向的提交）。

切换到新分支 (localBranch): 执行完创建操作后，git checkout 自动将您所在的分支切换到新创建的 localBranch。这意味着您的工作目录和暂存区将反映 localBranch 所指向的提交状态，您可以在此分支上开始新的开发工作。

关联远程跟踪分支 (origin/dev): 后面的 origin/dev 参数指定了一个远程分支作为新创建的 localBranch 的上游或追踪关系。这一步并非直接在命令中实现，但执行此命令后，如果您运行 git branch -vv，会发现 localBranch 已经被配置为追踪 origin/dev。这意味着：

当您首次执行此命令时，如果本地还没有 origin/dev 的副本，Git 会自动尝试从远程仓库 origin 中拉取（fetch）dev 分支的最新提交，确保您的新本地分支 localBranch 起始于与远程 dev 分支相同的状态。
未来执行 git pull 时，Git 会默认将远程 origin/dev 分支的更新合并到您的 localBranch 上。
执行 git push 时，如果没有显式指定远程分支，Git 会默认将 localBranch 推送到与之关联的远程跟踪分支 origin/dev。
综上所述，git checkout -b localBranch origin/dev 命令的作用是：

在本地创建一个名为 localBranch 的新分支。
将当前工作目录切换到新创建的 localBranch，以便开始在该分支上进行开发。
设置 localBranch 与远程仓库 origin 中的 dev 分支建立追踪关系，确保本地分支能够轻松地与远程分支保持同步，进行拉取和推送操作。

2.
