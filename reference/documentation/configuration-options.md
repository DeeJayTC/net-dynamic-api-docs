---
description: Unfinished yet...
---

# 🔧 Configuration Options

This section is unfinished, see here for all available options -> [https://github.com/DeeJayTC/net-dynamic-api/blob/main/src/TCDev.APIGenerator.Schema/ApiGeneratorConfig.cs](https://github.com/DeeJayTC/net-dynamic-api/blob/main/src/TCDev.APIGenerator.Schema/ApiGeneratorConfig.cs)

```json
 //Sample Config for API Generator
  "Api": {
    "Swagger": {
      "Enabled": "false", // Enable/Disable for production builds
      "Description": "Smoower API Sample",
      "Version": "v1",
      "Title": "Smoower sample config",
      "ContactMail": "Me@me.de",
      "ContactUri": "https://www.myuri.com"
    },
    "Database": {
      "DatabaseType": "SQL",
      "Connection": "Server=localhost;database=123123123;user=<user>;password=<password>"
    },
    "Odata": {
      "Enabled": true,
      "EnableSelect": true,
      "EnableFilter": false,
      "EnableSort": false
    }
  }
```
