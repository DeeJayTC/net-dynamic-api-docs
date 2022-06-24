---
description: Work in Progress
---

# 🔓 Authentication

Currently the generator does not know about user's or permissions yet...working on this part. \
However you can more than secure your APIs and allow access based on bearer tokens and scopes.&#x20;

This sample would create an API endpoint that requires authorization and only allows JWTs with specific scopes for read/write:

```csharp
    [Api("/people", 
        authorize:true, 
        requiredReadScopes: new string[] { "people.read" },
        requiredWriteScopes: new string[] { "people.write"})] 
    public class Person : Trackable
    {

        public int Id { get; set; }
        public string Name { get; set; }
        public DateTime DateOfBirth { get; set; }
    }
```

All "reading" methods take the ReadScope such as Get and Query and all other methods use the write scope.&#x20;

To configure the generator for your JWT provider you have these options in the configuration:

```json
    "Identity": {
      "EnableIdentity": true,
      "Audience": "...",
      "Authority": "...",
      "Issuser": "....",
      "ValidateAuthority": true,
      "ValidateIssuer": true,
      "MetaDataUri": "",
      "ValidateLifetime": true,
      "ValidateIssuerSigningkey":  true
    }js
```

