## CentOS上安装Tomcat

### 1.JDK环境

1.检查是否已有java环境

`java -version`

若无明确java 版本则未安装。

2.上传jdk.tar.gz,并解压

`tar -zxvf jdk.tar.gz`

3.配置/etc/profile文件

在文件末尾加入

```
export JAVA_HOME=/usr/local/java/jdk1.7.0_75
export JRE_HOME=/usr/local/java/jdk1.7.0_75/jre
export PATH=$PATH:/usr/local/java/jdk1.7.0_75/bin
export CLASSPATH=./:/usr/local/java/jdk1.7.0_75/lib:/usr/local/java/jdk1.7.0_75/jre/lib
```

### 2.安装tomcat

1.上传tomcat.tar.gz,并解压。

### 3. 发布web项目到tomcat

1.从开发环境中将项目导出为X.war。

2.将X.war放到tomcat/webapp下。

3.启动tomcat

```cd /bin
cd tomcat/bin
./startup.sh
```

### 4.开放端口8080

1.修改/etc/sysconfig/iptables

2.在文件末尾加入

`-A INPUT -m state --state NEW -m tcp -p tcp --dport 8080 -j ACCEPT （开放8080端口） `

3.关闭防火墙

chkconfig iptables off

service iptables restart







