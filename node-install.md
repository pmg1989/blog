### Linux 安装 NodeJS
* 基本步骤
    * cd /usr/local/node-v10/
    * 下载二进制文件：wget https://nodejs.org/download/release/v10.17.0/node-v10.17.0-linux-x64.tar.gz
    * 解压文件：tar -xvf node-v10.17.0-linux-x64.tar.gz
    * 重命名文件名：mv node-v10.17.0-linux-x64.tar.gz  nodejs
    * 删除二进制文件：rm -rf node-v10.17.0-linux-x64.tar.gz
* 方法一：修改~/.bash_profile文件 增加以下内容(只对当前用户有效)
    * export NODE_HOME=/usr/local/node-v10/nodejs
    * export PATH=$NODE_HOME/bin:$PATH
* 方法二：建立软链接，配置全局环境变量(只对当前用户有效)
    * ln -s /usr/local/node-v10/nodejs/bin/npm /usr/local/bin
    * ln -s /usr/local/node-v10/nodejs/bin/node /usr/local/bin
* 方法三：修改/etc/profile文件 增加以下内容（全局作用，对所有用户都有效）
    * export NODE_HOME=/usr/local/node-v10/nodejs
    * export PATH=$NODE_HOME/bin:$PATH
* 方法四（xhj）：新增/etc/profile.d/bashsh.sh文件 增加以下内容（全局作用，对所有用户都有效，不需要source）
    * export PATH=/usr/local/node-v10/node-v10.17.0-linux-x64/bin:$PATH
    * 若对摸个用户无效，则需修改对应用户的.bashrc文件，替换$PATH的顺序为： export PATH=$PATH:/usr/local/bin
    
```
   cd /usr/local/node-v10/
   wget https://nodejs.org/download/release/v10.17.0/node-v10.17.0-linux-x64.tar.gz
   tar -xvf node-v10.17.0-linux-x64.tar.gz
   mv node-v10.17.0-linux-x64  nodejs
   rm -rf node-v10.17.0-linux-x64.tar.gz
   
   # /etc/profile.d/bashsh.sh
   export NODE_HOME=/usr/local/node-v10/nodejs
   export PATH=$NODE_HOME/bin:$PATH
```
