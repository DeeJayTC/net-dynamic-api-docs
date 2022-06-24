---
description: See which Databases you can use and the configuration options needed
---

# 2⃣ Database Options

Currently the API Generator works with all Databases supported by EntityFramework itself. \
We have ready made libraries supporting MSSQL, SQLite and Postgres but the generator should work fine with MySQL and more with a litle bit of extra work.&#x20;

To use our implementation just add the package you want

```
dotnet add package TCDev.APIGenerator.Data.SQL 
dotnet add package TCDev.APIGenerator.Data.Postgres
dotnet add package TCDev.APIGenerator.Data.SQLite
```

Then you can add the Database to your startup file:

```
.AddDataContextSQL()
or
.AddDataContextSQLite
etc..
```

To tell the generator a few further things such as connection string just set the config option in appsettings:

```json
    "Database": {
      "DatabaseType": "SQL",
      "Connection": "Server=localhost;database=123123123;user=sa;password=Password!23;"
    }
```

If you want to use automatic migrations add this to your startup:

```
app.UseAutomaticApiMigrations(true);
while true or false defines wether destructive migrations
are allowed that could lead to data loss!
```

