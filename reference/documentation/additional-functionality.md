---
description: Easy to use helper classes for your APIs
---

# ❗ Additional functionality

The library comes with a few useful helper classes and interfaces you can use to further reduce boilerplate code.&#x20;

### Trackable

When inheriting from trackable your class is automatically extended by tracking "Created" and "Updated" and is automatically tracking last change date, this gets extended with LastUpdatedBy soon.&#x20;

Just inherit your class from Trackable like this:

```csharp
    [Api("/people")] 
    public class Person : Trackable
    {
        public int Id { get; set; }
        public string Name { get; set; }
        public DateTime DateOfBirth { get; set; }
    }
```

Your class will automatically have creation and last update dates tracked, this will also store the userId of the user when using Authentication

### SoftDeletable

Items are not deleted but just marked with "IsDeleted" in the database and are no longer returned via GET calls

....to be continued



