* 點開'mariadb.bat'開啟資料庫

|--------------------------|
| 查看所有資料庫           |
|--------------------------|
show databases;

|--------------------------|
| 移到指定資料庫           |
|--------------------------|
use 'dbname';
e.g. 移到users資料庫
use users;

|--------------------------|
| 新建資料庫               |
|--------------------------|
create database 'dbname';
e.g. 新建pos資料庫
create database pos;

****************************
* 還原資料庫               *
****************************
必須在登出資料庫(另開一個新的cmd)的狀態下執行
mysql -usophia -psophia88 'dbname' < 'sql file path'
e.g. 還原 C:\Users\user\OneDrive\桌面\users.sql 到pos資料庫上
mysql -usophia -psophia88 pos < C:\Users\user\OneDrive\桌面\users.sql

|--------------------------|
| 查看所有資料表           |
|--------------------------|
* 必需先移到指定的資料庫
show tables;

|--------------------------|
| 查詢所有記錄             |
|--------------------------|
SELECT * FROM `table`;
e.g. 查詢users資料表所有記錄
SELECT * FROM `users`;
