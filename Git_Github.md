# Git配置并关联GitHub以及使用简单教程

1. 安装Git：Linux: `sudo apt install git`
2. 本地Git配置
   * `git config --global user.name ”username”`
   * `git config--global user.email ”email”`
   * ` cat ~/.gitconfig`
3. 生成SSH Key：`ssh-keygen -t rsa -C"email"`
4. 用户主目录/.ssh/下，id_rsa是私钥，id_rsa.pub是公钥(cat id_rsa.pub并复制)
5. 登录GitHub，打开"SSH Keys"页面,使用公钥创建ssh keys 
6. 测试是否成功：`ssh -T git@github.com`
7. 远程库与本地库之间的操作
   * 远程	=> 本地
     * `git clone git@github.com:wangyb19/Python.git`
     * `cd reop`
     * `edit`
     * `git add .`
     * `git commit -m 'commit'`
   * 本地 => 远程
     * 本地库关联远程库：`git remote add origin git@github.com:username/repo.git`
     * 本地推送到远程（第一次）: `git push -u origin master` 第一次使用加上了-u参数，是推送内容并关联分支。
     * 之后：`git push origin master`
## 问题：每次从本地向github推送时总是需要输入用户名和密码
* 原因：在clone项目时使用了https方式而不是ssh方式
* 解决方法：将remote的https方式更改为ssh方式
  1. `git remote rm origin`
  2. `git remote add origin git地址`
