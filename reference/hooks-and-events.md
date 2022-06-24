---
description: Custom before / after hooks make even more advanced APIs possible
---

# ⭐ Hooks & Events



{% hint style="info" %}
**Note: This is an early feature, use it with caution but it should work:**
{% endhint %}

### Add a hook to customize behaviour

The library comes with 4 interfaces

```
// Before Update
IBeforeUpdate<TEntity>
IAfterUpdate<TEntity>

IBeforeDelete<TEntity>
IAfterDelete<TEntity>

IBeforeCreate<TEntity>
IAfterCreate<Tentity>
```

Each before event comes with the new and old version, take this as an example taken from the sample app:

```
public Task<Person> BeforeUpdate(Person newPerson, Person oldPerson)
{
   newPerson.Age = 333;

   return Task.FromResult(newPerson);
}
```
