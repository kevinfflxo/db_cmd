## 資料基本操作(Data Manipulation)

1. 資料的操作**建議先切換到 database**，請參閱：[database](./database.md)
2. 資料的操作**需要知道有哪些資料表及欄位**，請參閱：[table](./table.md)

假設有一張資料表結構如下：

|Field     |Type           |Key |
|----------|---------------|----|
|id        |bigint unsigned|PRI |
|name      |varchar(255)   |    |
|email     |varchar(255)   |UNI |
|password  |varchar(255)   |    |
|saved     |json           |    |
|created_at|timestamp      |    |
|updated_at|timestamp      |    |

* **查詢資料**

**SELECT Syntax**
```sql=
SELECT [COLUMN]
       [DISTINCT | DISTINCTROW | ALL]
    [FROM table_references
      [WHERE where_definition]
      [GROUP BY {unsigned_integer | col_name | formula} [ASC | DESC], ...]
      [HAVING where_definition]
      [ORDER BY {unsigned_integer | col_name | formula} [ASC | DESC] ,...]
      [LIMIT [offset,] rows]
      [PROCEDURE procedure_name]
      [FOR UPDATE | LOCK IN SHARE MODE]]
```