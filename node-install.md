### Linux 安装 NodeJS
* 基本步骤
    * cd /opt
    * 下载二进制文件：wget https://nodejs.org/dist/v8.10.0/node-v8.10.0-linux-x64.tar.xz
    * 解压文件：tar -xvf node-v8.10.0-linux-x64.tar.xz
    * 重命名文件名：mv node-v8.10.0-linux-x6  nodejs
    * 删除二进制文件：rm -rf node-v8.10.0-linux-x64.tar.xz
* 方法一：修改~/.bash_profile文件 增加以下内容(只对当前用户有效)
    * export NODE_HOME=/opt/nodejs
    * export PATH=$NODE_HOME/bin:$PATH
* 方法二：建立软链接，配置全局环境变量(只对当前用户有效)
    * ln -s /opt/nodejs/bin/npm /usr/local/bin
    * ln -s /opt/nodejs/bin/node /usr/local/bin
* 方法三：修改/etc/profile文件 增加以下内容（全局作用，对所有用户都有效）
    * export NODE_HOME=/opt/nodejs
    * export PATH=$NODE_HOME/bin:$PATH
    
```
   cd /opt
   wget https://nodejs.org/dist/v8.10.0/node-v8.10.0-linux-x64.tar.xz
   tar -xvf node-v8.10.0-linux-x64.tar.xz
   mv node-v8.10.0-linux-x6  nodejs
   rm -rf node-v8.10.0-linux-x64.tar.xz
   
   export NODE_HOME=/opt/nodejs
   export PATH=$NODE_HOME/bin:$PATH
```
