---
description: This is as simple as it can get
---

# ⁉ Samples

This code snippet is a fully working API that comes with GET,PUT,DELETE,POST endpoints, database tables etc all configured fully automatically.&#x20;

{% tabs %}
{% tab title="C#" %}
```csharp
   [Api("/students")]
    public class Student: IObjectBase<int>
    {
        public int Id { get; set; }
        public string FirstName { get; set; }
        public string LastName { get; set; }
        public DateTime DateOfBirth { get; set; }
    
        public void BeforeDelete(Student student)
        {
            // Before Delete hook to make custom validations
        }
    
    }

    [Api("/teachers")]
    public class Teacher : IObjectBase<int>
    {
        public int Id { get; set; }
        public string FirstName { get; set; }
        public string LastName { get; set; }
        public DateTime DateOfBirth { get; set; }

        public void BeforeCreate(Teacher newTeacher)
        {
            // Before Create hook to make custom validations
        }
    }

    [Api("/courses")]
    public class Course : IObjectBase<int>
    {
        public int Id { get; set; }
        public List<Student> Students { get; set; }
        public Teacher Teacher { get; set; }
        public List<DateTime> Schedule { get; set; }
    }
           
```
{% endtab %}

{% tab title="JSON" %}
```json

[
  {
    "name": "Student",
    "route": "/students",
    "idType": "int",
    "Fields": [
      {
        "name": "FirstName",
        "type": "String",
		"maxLength": 200
      },
      {
        "name": "LastName",
        "type": "String"
      },
      {
        "name": "DateOfBirth",
        "type": "DateTime"
      }
    ]
  },
  {
    "name": "Teacher",
    "route": "/teachersILove",
    "idType": "int",
    "events": "POST,DELETE",
    "cacheTime": "24h",
    "Fields": [
      {
        "name": "FirstName",
        "type": "String",
		    "maxLength": 200
      },
      {
        "name": "LastName",
        "type": "String"
      },
      {
        "name": "DateOfBirth",
        "type": "DateTime"
      }
    ]
  }  {
    "name": "Course",
    "route": "/coursess",
    "idType": "int",
    "Fields": [
      {
        "name": "FirstName",
        "type": "List<Student>"
        "maxCount": 20
      },
      {
        "name": "Teacher",
        "type": "Teacher"
      },
      {
        "name": "Schedule",
        "type": "List<DateTime>"
      }
    ]
  },
]
```
{% endtab %}

{% tab title="Setup Code" %}
```csharp
var builder = WebApplication.CreateBuilder(args);

builder.Services.AddApiGeneratorServices()
                //.AddAssemblyWithOData(Assembly.GetExecutingAssembly())
                .AddAssemblyWithODataFromUri("https://xxx","")
                //.AddAssembly(Assembly.GetExecutingAssembly())
                .AddDataContextSQL()
                .AddOData()
                .AddSwagger(true);
                
var app = builder.Build();                
app.UseApiGenerator();
app.UseAutomaticApiMigrations(true);

app.UseHttpsRedirection();
app.UseStaticFiles();
app.UseRouting();

app.UseApiGeneratorAuthentication();

app.UseEndpoints(endpoints =>
{
    endpoints.UseApiGeneratorEndpoints();
    endpoints.MapControllers();
});

app.Run();
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
You can find a lot more samples here -> [https://github.com/DeeJayTC/api-generator-samples](https://github.com/DeeJayTC/api-generator-samples)
{% endhint %}

