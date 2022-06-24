---
description: The API Attribute comes with various customization options
---

# 🤏 API Behaviour

To further define the behaviour of an API Endpoint such as which HTTP methods should be available, cache liftime, authorization and more see here:

```csharp
        /// <summary>
        ///    Attribute defining auto generated controller for the class
        /// </summary>
        /// <param name="route">The full base route for the class ie /myclass/ </param>
        /// <param name="requiredReadScopes"></param>
        /// <param name="requiredWriteScopes"></param>
        /// <param name="fireEvents"></param>
        /// <param name="authorize"></param>
        /// <param name="cache"></param>
        /// <param name="cacheDuration"></param>
        /// <param name="methods">The methods to generate for this endpoint</param>
        public ApiAttribute(
            string route,
            ApiMethodsToGenerate methods = ApiMethodsToGenerate.All,
            string[] requiredReadScopes = null,
            string[] requiredWriteScopes = null,
            bool fireEvents = false,
            bool authorize = false,
            bool cache = false,
            int cacheDuration = 50000)
        {
            this.Route = route;
            this.Options = new ApiAttributeAttributeOptions
            {
                RequiredReadScopes = requiredReadScopes,
                RequiredWriteScopes = requiredWriteScopes,
                Authorize = authorize,
                Cache = cache,
                CacheDuration = cacheDuration,
                FireEvents = fireEvents,
                Methods = methods
            };
        }c
```

