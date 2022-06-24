---
description: Things you can do to customize the database
---

# 🗃 Customizing Database

Per default the generator automatically creates all the tables, columns and tries to find the relationships between automatically. This is all handled by EntityFramework. \
However, there are times when this is not enough or not working, here's how you can customize this behaviour:

### Using a custom table name

```csharp
    [Api("/people", ApiMethodsToGenerate.All)]
    [Table("MyFancyNewTableName")]
    public class Person : IObjectBase<Guid> {
    
    }
```

As we're within .NET Core we can use all of the EntityFramework attributes as usually, just add a \[Table("")] attribute to map your class to a different table, everything else works out of the box



### Full customization

Based on EntityFramework model builder you can also fully customize your class behaviour, relationship and a lot more, here's how to do this:

```csharp
    [Api("/people", ApiMethodsToGenerate.All)]
    public class Person : IObjectBase<Guid>, IEntityTypeConfiguration<Person>
    {
        public Guid Id { get; set; } = new Guid();

        public string Name { get; set; }

        // Set custom stuff as desired similar to DBContext model builder
        // All model building options are available
        public void Configure(EntityTypeBuilder<Person> builder)
        {
            builder.ToTable("TableName");
            builder.HasMany("relatedObject");
            ...
        }
    }
```

