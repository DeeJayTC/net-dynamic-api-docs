# Configuration Options

### The "APIAttribute"

```
[Api("/url")]
```

Here's the currently implemented parameters, note that the library shows more but currently only these two have a proper effect as of 0.0.4

```
<param name="route">The full base route for the class ie /myclass/ </param>
<param name="methods">The methods to generate for this endpoint</param>
```

#### "Route" just defines the base route for the class ie /people

#### "Methods" defines which methods to generate, this is an enum flag ie you can combine options or just choose all.&#x20;

Example for only get and post:

```
   [Api("/people", ApiMethodsToGenerate.Get | ApiMethodsToGenerate.Update )]
```

#### Coming soon, not yet implemented:

```
  /// <param name="requiredReadClaims"></param>
  /// <param name="requiredWriteClaims"></param>
  /// <param name="requiredRolesRead"></param>
  /// <param name="requiredRolesWrite"></param>
  /// <param name="fireEvents"></param>
  /// <param name="authorize"></param>
  /// <param name="cache"></param>
  /// <param name="cacheDuration"></param>
```

#### &#x20;
