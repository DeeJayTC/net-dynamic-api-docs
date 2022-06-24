# 1⃣ Configuration & Setup

To get started and use the API Generator you have to initialize it first and add it to your .NET Web API Project. Depending on wether you use the "new" or "old" mode go to either the program.cs or the old startup file and add the required services:\


```csharp
builder.Services.AddApiGeneratorServices()
                .AddConfig(NameOfRootNodeInAppSettings)
                or
                .AddConfig(new ApiGeneratorConfig() { ... })
                or
                .AddConfig()
```

For a full info about all the available configuration options see here -> [configuration-options.md](../reference/configuration-options.md "mention")\




Make sure to also add these to tell the .NET Core middleware to properly use the API Generator:

```csharp
var app = builder.Build();

// Configure the HTTP request pipeline.

app.UseApiGenerator();
app.UseAutomaticApiMigrations(true);
```

\
