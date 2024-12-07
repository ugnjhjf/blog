---
title: MySQL部署
published: 2024-11-02
description: 在Debian 11上安装mysql
image: ./cover.jpg
tags: [MySQL, Debian, Database, Linux]
category: Back-end
draft: false
---
https://acytoo.com/ladder/install-mysql-on-debian11/
[[Debian 11 mysql安装 没有GPG公钥]]

https://blog.csdn.net/lggirls/article/details/121375433
https://dev.mysql.com/get/mysql-apt-config_0.8.33-1_all.deb

mysql -u root -p


```undefined
sudo apt install openjdk-17-jdk
```

```undefined
sudo apt install openjdk-17-jre
```

https://blog.csdn.net/qq_52050769/article/details/118095034

# 数据库问题
# 错误1: Nginx无法访问服务器

## 问题描述
开放端口之后，Nginx反向代理之后依旧无法访问内网服务器

## 解决方案

### 步骤1：MySQL允许外网链接
将监听改为0.0.0.0，即所有主机
位置为
```shell
/etc/mysql/my.cnf
```
加入以下内容：

```ini
[mysqld]
port = 3306
bind-address = 0.0.0.0
```

可以顺便开启utf-8编码

### 步骤2：MySQL开放权限
```mysql
mysql> GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'mypwd' WITH GRANT OPTION;  
mysql> flush privileges;
```


```shell
systemctl restart mysql
```
### 步骤2：防火墙开放
```shell
sudo ufw allow 3306
```

### 步骤3：Nginx使用stream而不是upstream
mysql有自己的传输协议，因此不是使用HTTPS

```nginx
stream{
	server{
	listen 3306;
	 proxy_connect_timeout 5s;
	 proxy_timeout 3s;
	 proxy_pass 192.168.31.100:3306;
	}
}
```

Java连接代码
```java
public class DatabaseConnector {  
    private Connection connection;  
  
    public DatabaseConnector() throws ClassNotFoundException {  
        connectDB();  
    }  
  
    public Connection getConnection() {  
        return connection;  
    }  
  
    public boolean connectDB() throws ClassNotFoundException {  
        Class.forName("com.mysql.cj.jdbc.Driver");  
  
        String url = "jdbc:mysql://www.EXAMPLE.com/DATA_BASE_NAME?useUnicode=true&characterEncoding=utf-8&autoReconnect=true&connectTimeout=3000&socketTimeout=3000";  
        String username = "root";  
        String password = "XXXXXX";  
        try {  
            connection = DriverManager.getConnection(url, username, password);  
            System.out.println("Database connection successful");  
            return true;        } catch (SQLException error) {  
            System.err.println("Database connection failure：" + error.getMessage());  
            return false;        }  
    }  
  
    public void disconnectDB() throws SQLException {  
        if (connection != null && !connection.isClosed()) {  
            connection.close();  
            System.out.println("Database connection closed");  
        }  
    }  
}
```


---
代码问题
# 错误2：查询的时候提示connection closed
## 问题描述
查询的时候概率出现结果，一般都是无法查询，显示下列错误：

```java
ConnectionIsClosedException: No operations allowed after connection closed
```

## 解决方案：
留意在每个方法之后有没有关闭连接，检查下列三个：
```java
resultSet.close();  //查询结果关闭
statement.close();  //SQL关闭
connection.close(); //数据库连接关闭

```

# 错误3：NullPointerException
## 问题描述：
在使用JSON前定义了变量，但是没有创建Object
## 解决方案：
补上新建Object，new xxxx(); 不仅仅是JSON，其他Object也适用
```java
private JSONObject resultJSON = new JSONObject();
```

## 错误4：CJCommunicationsException: Communications link failure
## 问题描述
无法与数据库交互，但是数据库之间的连接是没有问题的

## 解决方案：

检查 Connection connection 是否有被定义

```java
public DatabaseOperator() throws ClassNotFoundException {  
    this.databaseConnector = new DatabaseConnector();  
    this.connection = databaseConnector.getConnection();  

}
```