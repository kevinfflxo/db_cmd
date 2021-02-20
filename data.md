## 資料基本操作(Data Manipulation)

1. 資料的操作**建議先切換到 database**，請參閱：[database](./database.md)
2. 資料的操作**需要知道有哪些資料表及欄位**，請參閱：[table](./table.md)
3. 本文以**資料表：newtable**作為範例

假設有一張**資料表：newtable**結構如下：

|Field     |Type           |Key |
|----------|---------------|----|
|id        |bigint unsigned|PRI |
|name      |varchar(255)   |    |
|email     |varchar(255)   |UNI |
|password  |varchar(255)   |    |
|saved     |json           |    |
|created_at|timestamp      |    |
|updated_at|timestamp      |    |

---

### 查看資料

**SELECT Syntax (常用的)**

```
SELECT [COLUMN]
        [DISTINCT | DISTINCTROW | ALL]
    [FROM table_references]
      [INNER JOIN | LEFT JOIN | RIGHT JOIN]
      [WHERE where_definition]
      [GROUP BY {unsigned_integer | col_name | formula} [ASC | DESC], ...]
      [HAVING where_definition]
      [ORDER BY {unsigned_integer | col_name | formula} [ASC | DESC] ,...]
      [LIMIT [offset,] rows]
      [PROCEDURE procedure_name]
      [FOR UPDATE | LOCK IN SHARE MODE]]
```

* 查看**全部**的欄位資料

```
SELECT * FROM `newtable`;
```

* 查看**id, name**的欄位資料

```
SELECT `id`, `name` FROM `newtable`;
```

---

### 新增資料

**INSERT Syntax (常用的)**

```
INSERT [INTO] tbl_name [(col_name,...)]
    VALUES (expression,...),(...),...
```

* 新增資料 **(指定欄位，建議)**

```
INSERT INTO `newtable`(`name`, `email`, `password`, `saved`) VALUES ('newuser', 'newemail@example.com', 'newpassword', '[]');
```

* 新增資料 **(不指定欄位)**

    > 需要注意**欄位的順序不能錯**，且即使欄位允許 NULL，在新增資料的時候仍需指定初始值

```
INSERT INTO `newtable` VALUES (1, 'newuser', 'newemail@example.com', 'newpassword', '[]', NULL, NULL);
```

---

### 更新資料

**UPDATE Syntax (常用的)**

```
UPDATE tbl_name
    SET col_name1=expr1 [, col_name2=expr2, ...]
    [WHERE where_definition]
```

* 更新 **id = 1** 的資料，設定 **name = user**

```
UPDATE `newtable` SET `name` = 'user' WHERE `id` = 1;
```

---

### 刪除資料

**DELETE Syntax (常用的)**

```
DELETE FROM table_name
    [WHERE where_definition]
```

如果沒有 **[WHERE where_definition]** 則相當於 **TRUNCATE TABLE**

```
TRUNCATE TABLE newtable;
```

* 刪除 **id = 1** 的資料

```
DELETE FROM `newtable` WHERE `id` = 1;
```