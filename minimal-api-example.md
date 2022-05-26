---
description: This is as simple as it can get
---

# Minimal API Example

This code snippet is a fully working API that comes with GET,PUT,DELETE,POST endpoints, database tables etc all configured fully automatically.&#x20;

```
   /// <summary>
   /// This is the minimal sample, yes this is a working api ;)
   /// </summary>
   [Api("/minimal")]
   public class MinimalSample : IObjectBase<int>
   {
      public int Id { get; set; }
      public string Name { get; set; }
      public int Value { get; set; }
   }
```

There is however a lot more you can do and customize...continue  reading  the docs! :)
