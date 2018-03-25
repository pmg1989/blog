* Linux 安装 NodeJS 步骤
    * cd /opt
    * 下载二进制文件：wget https://nodejs.org/dist/v8.10.0/node-v8.10.0-linux-x64.tar.xz
    * 解压文件：tar -xvf node-v8.10.0-linux-x64.tar.xz
    * 重命名文件名：mv node-v8.10.0-linux-x6  nodejs
    * 删除二进制文件：rm -rf node-v8.10.0-linux-x64.tar.xz
* 修改/etc/profile文件 增加以下内容
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
