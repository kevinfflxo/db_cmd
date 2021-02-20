## 新增使用者及建立資料庫權限

* **step 1：建立資料庫**

    > DATABASE：newdatabase

```
CREATE DATABASE newdatabase;
```

* **step 2：建立新帳號**

    > ID：newuser 
    > PASSWORD：newpassword

```
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'newpassword';
```

* **step 3：給予新帳號 newdatabase 所有權限**

```
GRANT ALL PRIVILEGES ON newdatabase.* TO 'newuser'@'localhost';
FLUSH PRIVILEGES;
```

## 移除使用者帳號

* **step 1：查看使用者**

```
SELECT `Host`, `User` FROM `mysql`.`user`;
```

* **step 2：查看 ‘newuser’@’localhost’ 所擁有的權限**

```
SHOW GRANTS FOR 'newuser'@'localhost';
```

* **step 3：移除權限**

```
REVOKE ALL PRIVILEGES, GRANT OPTION FROM 'newuser'@'localhost';
```

* **step 4：移除使用者**

```
DROP USER 'newuser'@'localhost';
```

* **step 5：移除資料庫 (建議先備份)**

```
DROP DATABASE newdatabase;
```