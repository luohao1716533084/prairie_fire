### `MySQL` 安装

#### 方法一

在线安装最新版本

```bash
sudo yum install mysql-server
```

### `MySQL`配置

#### 启动

```bash
systemctl enable --now mysqld
```

#### 修改密码

```bash
ALTER USER 'root'@'localhost' IDENTIFIED BY '123456';基本操作
```

### 基本使用

查看命令

```sql
\?
```

#### 查看状态

```sql
status;
```

#### 输出副本

```bash
tee /tmp/query.sql  # 输出语句的结果到query.sql副本
```

#### 导入sql脚本

```sql
source /tmp/query.sql  # 输出语句的结果到query.sql副本
```

#### 执行系统命令

```sql
system ls /tmp/
```

#### 取消sql命令执行

```sql
\c
```

#### 编辑`sql`语句

```sql
\e
;
/* 默认用打开vim，使用:w /tmp/file.sql写入 */
```

MySQL数据库目录

```bash
# 存放位置
/var/lib/mysql

# 创建数据库目录
datadir=/var/lib/mysql
socket=/var/lib/mysql/mysql.sock
symbolic-links=0
log-error=/var/log/mysqld.log

# 蓝色的目录是一个数据库
# 数据库的数据则在该文件夹下
/var/lib/mysql/database/

"""
myisam
索引: `.sdi`, `.MYI`
数据: `.MYD`

innodb
索引: `.ibd`
"""
```

#### 修改密码

```sql
ALTER USER 'username'@'localhost' IDENTIFIED BY 'new_password';
```

#### 添加用户

```sql
CREATE USER 'new_user'@'localhost' IDENTIFIED BY 'user_password';
GRANT ALL PRIVILEGES ON *.* TO 'new_user'@'localhost' WITH GRANT OPTION;
FLUSH PRIVILEGES;
```

#### 开启日志

```sql
log-bin=mysqlbinlog
```





