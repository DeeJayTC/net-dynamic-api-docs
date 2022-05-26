# Database Options

Per default the library is using EF Core In Memory provider as per 0.0.6. \
To use SQL or SQL Lite you need to configure by just changing app settings

```
 "Api": {
    "Database": {
      "DatabaseType": "SQL or InMemory"
    },
  }
```

Connection string is taken from AppSettings "connection strings" area

```
  "ConnectionStrings": {
    "ApiGeneratorDatabase": "Server=localhost;database=tcdev_dev_222;user=sa;password=Password!23;"
  },
```

{% hint style="info" %}
NOTE: ConnectinString MUST be named "APIGeneratorDatabase" this requirement will change in a later version
{% endhint %}
