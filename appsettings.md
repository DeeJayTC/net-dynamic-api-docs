---
description: Creating your first API using the generator is quick and easy
---

# 3⃣ Create your first API

The first and most important thing to note is, you need to implement the "**IObjectBase\<T>**" interface for your primary key. This is made to allow you to select the type of primary key (int, string or guid) you want to use but is also used to generate the API Endpoints later on. This is the minimum requirement you have to do.&#x20;

Lets write a class as a sample:

```csharp
public class Person : IObjectBase<int> {

    public int Id {get;set;}
    public string Name {get;set;}
    public DateTime DateOfBirth {get;set;}
}


```

Now, this is enough for our underlying systems to generate the database tables for this specific class and you can theoretically query and store data for it. Yet this is not an API Endpoint yet.&#x20;

To have a class appear in swagger and have all the needed CRUD endpoints generated you have to actually mark it as an API, this is quite easy thanks to our API Attribute.&#x20;

Lets further extend the class to work as an API

```csharp
[Api("/people")
public class Person : IObjectBase<int> {

    public int Id {get;set;}
    public string Name {get;set;}
    public DateTime DateOfBirth {get;set;}
}
```

See how we only added that attribute? Yes, this is enough to turn the class into a full API!

If you start your app now, you'll see Swagger UI showing you the OpenAPI Specs for your Person class. If you want to further define the behaviour of that API see here -> [api-behaviour.md](reference/api-behaviour.md "mention")

In case you want to add some custom behaviour to your API you can further extend the class with our so called hooks. These come for all CRUD events such as beforeCreate, afterUpdate, afterDelete etc. Read more about that here -> [hooks.md](reference/documentation/hooks.md "mention")
