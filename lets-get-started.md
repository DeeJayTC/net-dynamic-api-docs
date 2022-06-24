---
description: Quick and easy first steps with the library
---

# 🧙 Lets get started

## Install the library

The best way to use the API Generator is to just use the Nuget package:

{% hint style="success" %}
Install required dependencies

dotnet add package TCDev.APIGenerator \
dotnet add package TCDev.APIGenerator.Data \
dotnet add package TCDev.APIGenerator.Schema
{% endhint %}

{% hint style="warning" %}
**Install further dependencies on demand**\
The APIGenerator comes with a few optional dependencies out of which you need to pick at least the database ones to use the API properly. \
\
Install either of these for the matching database:\
\
TCDev.APIGenerator.Data.SQL\
TCDev.APIGenerator.Data.SQLite\
TCDev.APIGenerator.Data.Postgres\
TCDev.APIGenerator.Data.InMemory\
\
Further available packages for additional features:\
\
TCDev.APIGenerator.OData _// If you want to use any OData features_\

{% endhint %}

{% hint style="info" %}
Another option is to just use the packages for the Database you want to use directly, it will auto-install the needed dependencies, you can start like this:\
\
dotnet add package TCDev.APIGenerator.Data.SQL

dotnet add package TCDev.APIGenerator.OData\

{% endhint %}
