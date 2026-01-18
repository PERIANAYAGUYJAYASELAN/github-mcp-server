# CelestialBodies
(*CelestialBodies*)

## Overview

Celestial bodies are the planets and satellites in the Scalar Galaxy.

### Available Operations

* [CreateCelestialBody](#createcelestialbody) - Create a celestial body

## CreateCelestialBody

Create a celestial body

### Example Usage

```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Components;

var sdk = new DemoApiScalarGalaxy();

CelestialBodyInput req = CelestialBodyInput.CreateSatellite(
    new SatelliteInput() {
        Name = "Phobos",
        Type = SatelliteType.Satellite,
    }
);

var res = await sdk.CelestialBodies.CreateCelestialBodyAsync(req);

// handle response
```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [CelestialBodyInput](../../Models/Components/CelestialBodyInput.md) | :heavy_check_mark:                                                  | The request object to use for the request.                          |

### Response

**[CreateCelestialBodyResponse](../../Models/Requests/CreateCelestialBodyResponse.md)**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException | 4XX, 5XX                                                                   | \*/\*                                                                      |