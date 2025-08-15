Note: check commits for details

See also README_sqlserver

1. Change some create table sql(s) based on Sql Server sql syntax
2. Use `IDENTITY(1,1)` instead of `AUTO_INCREMENT`. Then we need to manually set `SET IDENTITY_INSERT bmsql_history ON` before inserting any given value for `identity` column (see src/LoadData/LoadData.java)
3. Change `FOR UPDATE` to `WITH (UPDLOCK)` and put it rightly after tablename (see src/client/jTPCCConnection.java)
4. Change `where (col1, col2) in ((?,?),(?,?))`-like sentences to `WHERE (col1 = ? AND col2 = ?) OR (col1 = ? AND col2 = ?) OR ...` format
5. ...
