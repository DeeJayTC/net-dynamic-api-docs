---
description: Quick and easy first steps with the library
---

# 🧙 Lets get started

## Install the library

The best way to use the API Generator is to just use the Nuget package:

{% tabs %}
{% tab title=".NET 6" %}
```
# Install via nuget
dotnet add package TCDev.APIGenerator
dotnet add package TCDev.APIGenerator.Data
dotnet add package TCDev.APIGenerator.Schema // Auto installed as dependency

```
{% endtab %}
{% endtabs %}

{% hint style="success" %}
**Step1 - Setup**\
Before being able to do anything you need to include and configure the library
{% endhint %}

#### Add the library:

```
 builder.Services.AddApiGeneratorServices(builder.Configuration, Assembly.GetExecutingAssembly());
```

Note: Assembly needs to point to the assembly which has your classes. In our example we just use the currently executed assembly.&#x20;

Additionally we need to actually use the service and include in middleware etc:

```
 app.UseApiGenerator(); 
 app.UseAutomaticAPIMigrations(true); 
```

UseAutomaticAPIMigrations should only be used during development and for test scenarios. Never have that active in production as it can possibly break things.&#x20;

Want to get more detailed.... continue  reading :)
