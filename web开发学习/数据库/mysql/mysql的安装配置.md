
## 配置linux上的数据库（踩坑篇）
### 1.切记要注意自己数据库的版本，尤其是在设置密码这一块
**在mysq8.0以上的版本时，设置密码**
 MySQL的`SET PASSWORD`语句在MySQL 5.7之后的版本中已不再支持使用`PASSWORD`函数进行密码更改。要更改'root'用户的密码，你可以使用`ALTER USER`语句。以下是正确的语法：
		`ALTER USER 'root'@'localhost' IDENTIFIED BY 'wzy123456';`

### 2.在一开始无法登录上mysql时候，修改/etc/my.ini(my.cnf)等文件
这里需要跳过授权以进行修复或重置密码等操作，可以修改mysql的配置文件，来启用跳过授权表的选项。在mysql配置我呢见中，这个选项通常被称为
	skip-grant-tables
我们进行重置修改密码之后再将这一行代码进行删除就行

## 3.这里是为了修改root账户登录的地址筛选
 update user set host='%' where user ='root';

## 4.关于flush privileges的一些理解
`FLUSH PRIVILEGES;` 是一个MySQL数据库管理命令，它在特定情况下用来重新加载授权表，以确保最新的授权更改生效。当你在MySQL中进行了一些与用户权限或角色相关的更改时，如创建新用户、分配或撤销权限，你需要执行这个命令，以使这些更改立即生效。

通常，你在进行以下操作后需要运行 `FLUSH PRIVILEGES;`：

1. 创建、修改或删除用户账户。
2. 分配或撤销用户的权限。
3. 创建、修改或删除角色。
4. 将用户添加到或移除用户组。
5. 更新授权表文件（通常是 `mysql.user` 表）。

一旦你运行了 `FLUSH PRIVILEGES;`，MySQL 将重新加载授权表，以便数据库服务器能够立即应用新的权限设置。在大多数情况下，这不会中断数据库的正常运行。

需要注意的是，在MySQL 5.7以及之后的版本中，`FLUSH PRIVILEGES;` 不再是必需的，因为权限更改会自动生效，而无需手动刷新权限表。因此，只有在旧版本的MySQL或特殊情况下，才需要手动运行这个命令。

## 5.执行授权，给用户分配执行权力
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%'WITH GRANT OPTION;
