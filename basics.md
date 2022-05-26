---
description: Basic setup for your API
---

# Basics

{% hint style="warning" %}
**Note: A lot of this is still early alpha, while its working and already usable there's a lot more to come!**
{% endhint %}

## Writing your Model

Just write the class for your API as you usualy would, you can do anything like you want to, there's no limitations. Here's another sample:\


```
   [Api("/people", ApiMethodsToGenerate.All )]
   public class Person : Trackable, 
      IObjectBase<Guid>,
   {
      public string Name { get; set; }
      public DateTime Date { get; set; }
      public string Description { get; set; }
      public int Age { get; set; }
      public Guid Id { get; set; }
   }
```

The first and most important thing to note is, you need to implement the "**IObjectBase\<T>**" interface for your primary key. This is made to allow you to select the type of primary key (int, string or guid) you want to use but is also used to generate the API Endpoints later on. This is the minimum requirement you have to do.&#x20;

To configure the outcome you have to add the ApiAttribute to your class as seen in above example. The attribute is used to set the route and various options for your API
