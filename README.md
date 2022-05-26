---
description: Build your first API in 5 minutes :)
cover: >-
  https://user-images.githubusercontent.com/4077759/162592498-d420906e-5eee-4d95-b0b2-c5c3c2b0c8d1.png
coverY: 79.04278462654098
layout: landing
---

# 😎 Welcome!

The API Generator automatically generates a fully working CRUD Microservice from just your Model (C# Classes) or a JSON Definition. Everything from routes, database handling, migrations, openapi spec, OData etc is working magically out of the box! You just write your model and get a fully working CRUD api with filtering, sorting, selectable fields and everything else OData and classic REST offers.\
\
By using the API Gen, this little snipet is already a full API

```csharp
 [Api("/people", ApiMethodsToGenerate.All )]
 public class Person : Trackable, 
    IObjectBase<Guid>,
    IBeforeUpdate<Person>, // Before Update Hook
    IBeforeDelete<Person>, // BeforeDelete Hook
 {
    public string Name { get; set; }
    public DateTime Date { get; set; }
    public string Description { get; set; }
    public int Age { get; set; }
    public Guid Id { get; set; }
 }
```

{% hint style="info" %}
Currently released version 0.1.5 on Nuget
{% endhint %}
