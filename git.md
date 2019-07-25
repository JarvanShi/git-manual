# git教程
## git工作流程
1. 克隆资源到本地工作目录
2. file增删改查操作，或者更新资源
3. 检查修改情况
4. 提交修改
5. 推送修改，或者撤回提交，并再次修改和提交

## git基本操作
1. 配置
git config --global user.name <username>  # 设置用户名
git cogfig --global user.email <useremail>  # 设置用户邮箱
2. 初始化仓库 
git init  # 在目录中创建新的git仓库，仓库名就是该目录
git init newrepo  # 指定目录作为git仓库
3. 克隆仓库
ssh-keygen -t rsa -C 'email'  # 生成密匙，将~/.ssh/id_rsa.pub里的密匙添加到github
ssh -T git@github.com  # 验证本地仓库和远程仓库是否验证成功
git clone git@github.com:JarvanShi/web-crawler ~/workspace/git/  #使用ssh协议将远程仓库克隆到本地,【这种方法最快】
git clone git://github.com/JarvanShi/web-crawler  # 使用git协议将远程仓库克隆到本地
git clone http://github.com/JarvanShi/web-crawler  # 使用http协议将远程仓库克隆到本地
4. 查看仓库修改状态
git status -s  # 以简要方式显示git缓存状态
git status  # 以详细方式显示git缓存状态
5. 添加修改到缓存
git add <file>  # 将file添加到缓存
6. 查看未缓存的文件的详细信息
git diff  # 未添加缓存的file的改动详细信息
7. 查看已缓存的文件的详细信息
git diff --cached  # 添加缓存的file的改动详细信息
8. 取消文件的缓存
git reset HEAD <file>  # 取消该file的缓存
9. 提交缓存到仓库
git commit -m '提交缓存'
10. 直接提交，跳过添加缓存
git commit -am '直接提交，而不经过添加缓存'
11. 删除git中的文件
git rm <file>  # 在git中删除文件
12. 删除git中该文件的缓存
git rm --cached <file>  # 在git中仅删除添加的暂存区缓存
13. 删除git中该文件和缓存
git rm -f <file>  # 在git中删除该文件的暂存区缓存和该文件
git rm -rf <file>  # 该目录下面的文件和文件夹全部删除
14. 移动文件
git mv <file1> <file2>  # 在git中移动文件

## git分支操作
1. 列出分支
git branch -a
2. 创建分支
git branch <branch name>
git checkout -b <branch name>
3. 切换分支
git checkout <branch name>
4. 删除分支
git branch -d <branch name>
5. 合并分支
git merge <branch name>
6. 合并冲突
手动修改冲突
使用git add告诉git文件冲突已解决
使用git commit提交结果

## git日志
1. 日志详细信息
git log
2. 日志简要信息
git log --oneline
3. 日志逆向显示
git log --oneline --reverse
4. 日志图像显示
git log --graph
5. 日志按作者显示
git log --author=Linus --oneline
6. 日志按时间显示
git log --oneline --since={2019-06-17} --before={3.weeks.ago} --no-merges

## git标签
1. 显示所有标签
git tag 
2. 给提交打标签
git tag -a <如：v1.0> <提交号>
3. 查看提交的标签
git log --oneline --decorate --graph
4. 指定标签信息
git tag -a <tagname> -m '标签信息'

## git github
1. 添加远程仓库
git remote add origin git@github.com:JarvanShi/runoob-git-test
2. 推送本地仓库
git push -u origin master
3. 查看当前仓库
git remote
4. 查看所有仓库
git remote -v
5. 添加另一个仓库
git remote add origin2 git@github.com:JarvanShi/runoob-git-test.git
6. 删除仓库
git remote rm origin2
7. 获取远程仓库的新数据
git fetch origin
8. 合并远程仓库和本地仓库的数据
git merge origin/master
