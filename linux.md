* 原生启动后台服务
    * 启动：nohup yarn run start &
    * 查看：jobs
    * 停止：fg [jobs的编号]

* 常用命令
    * git clone https://felixpmg:1q2w3e4r@git.coding.net/newband-dev/lms_web_2.0.git
    * ssh-copy-id -i ~/.ssh/id_rsa.pub root@xxx.xx.xx.xxx
    * which node : 用来查找一个命令的绝对路径
    * rm -rf dir : 强制删除dir目录
    * cp file1 file2 : cp [ 来源文件 ] [目的文件]
    * cp -r dir1 dir2 : cp [选项] [ 来源目录 ] [目的目录]
    * mv source dist : 移动或者重命名文件/目录(mv /usr/bin/node{,.bak}  =  mv /usr/bin/node /usr/bin/node.bak)
    * chgrp [组名] [文件名] : 更改文件的所属组
    * chown [ -R ] 账户名:组名 文件名 : 更改文件的所属主
    * whereis node : 通过预先生成的一个文件列表库去查找跟给出的文件名相关的文件
    * find /root -name filename : 在/root目录下查找文件名为filename的文件
    * [vim 快捷键](http://wiki.jikexueyuan.com/project/linux/vim.html)
    * [文档的压缩与打包](http://wiki.jikexueyuan.com/project/linux/compression-and-packaged.html)
    * tar -zcvf test.tar.gz test : 将test目录压缩至test.tar.gz压缩包
    * tar -zxvf test01.tar.gz : 解压test01.tar.gz文件
    * 进入docker容器 : docker exec -it containerId /bin/bash
    * 切换账号操作命令： su - deploy -c "bash /home/deploy/restart_pm2.sh prod"
