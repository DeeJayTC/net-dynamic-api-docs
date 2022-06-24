# 1⃣ Configuration & Setup

To get started and use the API Generator you have to initialize it first and add it to your .NET Web API Project. Depending on wether you use the "new" or "old" mode go to either the program.cs or the old startup file and add the required services:\


```csharp
builder.Services.AddApiGeneratorServices()
                .AddConfiguration(NameOfRootNodeInAppSettings)
                .AddAssembly(Assembly.GetExecutingAssembly())
```

Depending on the libraries you installed and the functions you'd love to use there's further things you have to configure:\
\
