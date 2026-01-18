<!-- Start SDK Example Usage [usage] -->
```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;

var sdk = new DemoApiScalarGalaxy();

var res = await sdk.Planets.GetAllDataAsync(
    limit: 10,
    offset: 0
);

// handle response
```
<!-- End SDK Example Usage [usage] -->