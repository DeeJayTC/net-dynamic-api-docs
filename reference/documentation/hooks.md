---
description: Custom before / after hooks make even more advanced APIs possible
---

# ⭐ Hooks & Events

{% hint style="info" %}
**Note: This is an early feature, use it with caution but it should work:**
{% endhint %}

In case you want to add some custom behaviour to your API you can further extend the class with our so called hooks. These come for all CRUD events such as beforeCreate, afterUpdate, afterDelete etc. But have a look at this:

```csharp
    [Api("/people")] 
    public class Person : IObjectBase<int>, IBeforeCreate<Person>, IAfterUpdate<Person>
    {

        public int Id { get; set; }
        public string Name { get; set; }
        public DateTime DateOfBirth { get; set; }

        public async Task<Person> AfterUpdate(Person newItem, Person oldItem, IApplicationDataService<GenericDbContext, AuthDbContext> data)
        {
            using(var client = new HttpClient())
            {
                await client.PostAsync("someUrl", newItem);
            }
        }

        public Task<Person> BeforeCreate(Person newItem, IApplicationDataService<GenericDbContext, AuthDbContext> data)
        {
            // lets make sure the date of birth is correct!
            if (newItem.DateOfBirth < new DateTime(1900, 01, 01))
            {
                newItem.DateOfBirth = DateTime.MinValue;
            }
            return Task.FromResult(newItem);
        }
    }
```

This can be done for all these events:

* IBeforeUpdate, IBeforeCreate, IBeforeDelete
* IAfterUpdate, IAfterCreate, IAfterDelete

We might add more event hooks later but these are the ones currently existing.&#x20;

In each event you can access the database using the provided ApplicationDataService instance.&#x20;
