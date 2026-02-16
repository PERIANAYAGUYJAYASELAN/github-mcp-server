# Planets
(*Planets*)

## Overview

Everything about planets

### Available Operations

* [GetAllData](#getalldata) - Get all planets
* [CreatePlanetJson](#createplanetjson) - Create a planet
* [CreatePlanetRaw](#createplanetraw) - Create a planet
* [GetPlanet](#getplanet) - Get a planet
* [UpdatePlanetJson](#updateplanetjson) - Update a planet
* [UpdatePlanetRaw](#updateplanetraw) - Update a planet
* [DeletePlanet](#deleteplanet) - Delete a planet
* [UploadImage](#uploadimage) - Upload an image to a planet

## GetAllData

It's easy to say you know them all, but do you really? Retrieve all the planets and check whether you missed one.

### Example Usage

```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;

var sdk = new DemoApiScalarGalaxy();

var res = await sdk.Planets.GetAllDataAsync(
    limit: 10,
    offset: 0
);

// handle response
```

### Parameters

| Parameter                                                             | Type                                                                  | Required                                                              | Description                                                           |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `Limit`                                                               | *long*                                                                | :heavy_minus_sign:                                                    | The number of items to return                                         |
| `Offset`                                                              | *long*                                                                | :heavy_minus_sign:                                                    | The number of items to skip before starting to collect the result set |

### Response

**[GetAllDataResponse](../../Models/Requests/GetAllDataResponse.md)**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException | 4XX, 5XX                                                                   | \*/\*                                                                      |

## CreatePlanetJson

Time to play god and create a new planet. What do you think? Ah, don't think too much. What could go wrong anyway?

### Example Usage

```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Components;
using System;
using System.Collections.Generic;

var sdk = new DemoApiScalarGalaxy();

PlanetInput req = new PlanetInput() {
    Name = "Mars",
    Description = "The red planet",
    Type = Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Components.Type.Terrestrial,
    HabitabilityIndex = 0.68F,
    PhysicalProperties = new PhysicalProperties() {
        Mass = 0.107F,
        Radius = 0.532F,
        Gravity = 0.378F,
        Temperature = new Temperature() {
            Min = 130F,
            Max = 308F,
            Average = 210F,
        },
    },
    Atmosphere = new List<Atmosphere>() {
        new Atmosphere() {
            Compound = "CO2",
            Percentage = 95.3F,
        },
    },
    DiscoveredAt = System.DateTime.Parse("1610-01-07T00:00:00Z"),
    Image = "https://cdn.scalar.com/photos/mars.jpg",
    Satellites = new List<SatelliteInput>() {
        new SatelliteInput() {
            Name = "Phobos",
            Description = "Phobos is the larger and innermost of the two moons of Mars.",
            Diameter = 22.2F,
            Type = SatelliteType.Moon,
            Orbit = new Orbit() {
                PlanetId = 1,
                OrbitalPeriod = 0.319F,
                Distance = 9376F,
            },
        },
    },
    Creator = new UserInput() {
        Name = "Marc",
    },
    Tags = new List<string>() {
        "solar-system",
        "rocky",
        "explored",
    },
    SuccessCallbackUrl = "https://example.com/webhook",
    FailureCallbackUrl = "https://example.com/webhook",
};

var res = await sdk.Planets.CreatePlanetJsonAsync(req);

// handle response
```

### Parameters

| Parameter                                             | Type                                                  | Required                                              | Description                                           |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `request`                                             | [PlanetInput](../../Models/Components/PlanetInput.md) | :heavy_check_mark:                                    | The request object to use for the request.            |

### Response

**[CreatePlanetJsonResponse](../../Models/Requests/CreatePlanetJsonResponse.md)**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException | 4XX, 5XX                                                                   | \*/\*                                                                      |

## CreatePlanetRaw

Time to play god and create a new planet. What do you think? Ah, don't think too much. What could go wrong anyway?

### Example Usage

```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;
using System;

var sdk = new DemoApiScalarGalaxy();

byte[] req = System.Text.Encoding.UTF8.GetBytes("{\"type\":\"terrestrial\",\"physicalProperties\":{\"radius\":0.532,\"gravity\":0.378,\"temperature\":{\"min\":130,\"max\":308,\"average\":210},\"mass\":0.107},\"satellites\":[{\"orbit\":{\"planetId\":1,\"orbitalPeriod\":0.319,\"distance\":9376},\"name\":\"Phobos\",\"description\":\"Phobos is the larger and innermost of the two moons of Mars.\",\"diameter\":22.2,\"type\":\"moon\"}],\"creator\":{\"name\":\"Marc\"},\"successCallbackUrl\":\"https://example.com/webhook\",\"name\":\"Mars\",\"description\":\"The red planet\",\"habitabilityIndex\":0.68,\"atmosphere\":[{\"percentage\":95.3,\"compound\":\"CO2\"}],\"discoveredAt\":\"1610-01-07T00:00:00Z\",\"image\":\"https://cdn.scalar.com/photos/mars.jpg\",\"tags\":[\"solar-system\",\"rocky\",\"explored\"],\"failureCallbackUrl\":\"https://example.com/webhook\"}");

var res = await sdk.Planets.CreatePlanetRawAsync(req);

// handle response
```

### Parameters

| Parameter                                  | Type                                       | Required                                   | Description                                |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| `request`                                  | *byte[]*                                   | :heavy_check_mark:                         | The request object to use for the request. |

### Response

**[CreatePlanetRawResponse](../../Models/Requests/CreatePlanetRawResponse.md)**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException | 4XX, 5XX                                                                   | \*/\*                                                                      |

## GetPlanet

You'll better learn a little bit more about the planets. It might come in handy once space travel is available for everyone.

### Example Usage

```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;

var sdk = new DemoApiScalarGalaxy();

var res = await sdk.Planets.GetPlanetAsync(planetId: 1);

// handle response
```

### Parameters

| Parameter                   | Type                        | Required                    | Description                 | Example                     |
| --------------------------- | --------------------------- | --------------------------- | --------------------------- | --------------------------- |
| `PlanetId`                  | *long*                      | :heavy_check_mark:          | The ID of the planet to get | 1                           |

### Response

**[GetPlanetResponse](../../Models/Requests/GetPlanetResponse.md)**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException | 4XX, 5XX                                                                   | \*/\*                                                                      |

## UpdatePlanetJson

Sometimes you make mistakes, that's fine. No worries, you can update all planets.

### Example Usage

```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Components;
using System;
using System.Collections.Generic;

var sdk = new DemoApiScalarGalaxy();

var res = await sdk.Planets.UpdatePlanetJsonAsync(
    planetId: 1,
    planet: new PlanetInput() {
        Name = "Mars",
        Description = "The red planet",
        Type = Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Components.Type.Terrestrial,
        HabitabilityIndex = 0.68F,
        PhysicalProperties = new PhysicalProperties() {
            Mass = 0.107F,
            Radius = 0.532F,
            Gravity = 0.378F,
            Temperature = new Temperature() {
                Min = 130F,
                Max = 308F,
                Average = 210F,
            },
        },
        Atmosphere = new List<Atmosphere>() {
            new Atmosphere() {
                Compound = "CO2",
                Percentage = 95.3F,
            },
        },
        DiscoveredAt = System.DateTime.Parse("1610-01-07T00:00:00Z"),
        Image = "https://cdn.scalar.com/photos/mars.jpg",
        Satellites = new List<SatelliteInput>() {
            new SatelliteInput() {
                Name = "Phobos",
                Description = "Phobos is the larger and innermost of the two moons of Mars.",
                Diameter = 22.2F,
                Type = SatelliteType.Moon,
                Orbit = new Orbit() {
                    PlanetId = 1,
                    OrbitalPeriod = 0.319F,
                    Distance = 9376F,
                },
            },
        },
        Creator = new UserInput() {
            Name = "Marc",
        },
        Tags = new List<string>() {
            "solar-system",
            "rocky",
            "explored",
        },
        SuccessCallbackUrl = "https://example.com/webhook",
        FailureCallbackUrl = "https://example.com/webhook",
    }
);

// handle response
```

### Parameters

| Parameter                                             | Type                                                  | Required                                              | Description                                           | Example                                               |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `PlanetId`                                            | *long*                                                | :heavy_check_mark:                                    | The ID of the planet to get                           | 1                                                     |
| `Planet`                                              | [PlanetInput](../../Models/Components/PlanetInput.md) | :heavy_minus_sign:                                    | New information about the planet                      |                                                       |

### Response

**[UpdatePlanetJsonResponse](../../Models/Requests/UpdatePlanetJsonResponse.md)**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException | 4XX, 5XX                                                                   | \*/\*                                                                      |

## UpdatePlanetRaw

Sometimes you make mistakes, that's fine. No worries, you can update all planets.

### Example Usage

```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;
using System;

var sdk = new DemoApiScalarGalaxy();

var res = await sdk.Planets.UpdatePlanetRawAsync(
    planetId: 1,
    planet: System.Text.Encoding.UTF8.GetBytes("{\"name\":\"Mars\",\"description\":\"The red planet\",\"type\":\"terrestrial\",\"habitabilityIndex\":0.68,\"physicalProperties\":{\"mass\":0.107,\"radius\":0.532,\"gravity\":0.378,\"temperature\":{\"min\":130,\"max\":308,\"average\":210}},\"atmosphere\":[{\"compound\":\"CO2\",\"percentage\":95.3}],\"discoveredAt\":\"1610-01-07T00:00:00Z\",\"image\":\"https://cdn.scalar.com/photos/mars.jpg\",\"satellites\":[{\"name\":\"Phobos\",\"description\":\"Phobos is the larger and innermost of the two moons of Mars.\",\"diameter\":22.2,\"type\":\"moon\",\"orbit\":{\"planetId\":1,\"orbitalPeriod\":0.319,\"distance\":9376}}],\"creator\":{\"name\":\"Marc\"},\"tags\":[\"solar-system\",\"rocky\",\"explored\"],\"successCallbackUrl\":\"https://example.com/webhook\",\"failureCallbackUrl\":\"https://example.com/webhook\"}")
);

// handle response
```

### Parameters

| Parameter                        | Type                             | Required                         | Description                      | Example                          |
| -------------------------------- | -------------------------------- | -------------------------------- | -------------------------------- | -------------------------------- |
| `PlanetId`                       | *long*                           | :heavy_check_mark:               | The ID of the planet to get      | 1                                |
| `Planet`                         | *byte[]*                         | :heavy_minus_sign:               | New information about the planet |                                  |

### Response

**[UpdatePlanetRawResponse](../../Models/Requests/UpdatePlanetRawResponse.md)**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException | 4XX, 5XX                                                                   | \*/\*                                                                      |

## DeletePlanet

This endpoint was used to delete planets. Unfortunately, that caused a lot of trouble for planets with life. So, this endpoint is now deprecated and should not be used anymore.

### Example Usage

```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;

var sdk = new DemoApiScalarGalaxy();

var res = await sdk.Planets.DeletePlanetAsync(planetId: 1);

// handle response
```

### Parameters

| Parameter                   | Type                        | Required                    | Description                 | Example                     |
| --------------------------- | --------------------------- | --------------------------- | --------------------------- | --------------------------- |
| `PlanetId`                  | *long*                      | :heavy_check_mark:          | The ID of the planet to get | 1                           |

### Response

**[DeletePlanetResponse](../../Models/Requests/DeletePlanetResponse.md)**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException | 4XX, 5XX                                                                   | \*/\*                                                                      |

## UploadImage

Got a crazy good photo of a planet? Share it with the world!

### Example Usage

```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Requests;
using System.IO;

var sdk = new DemoApiScalarGalaxy();

var res = await sdk.Planets.UploadImageAsync(
    planetId: 1,
    requestBody: new UploadImageRequestBody() {
        Image = new Image() {
            FileName = "example.file",
            Content = File.ReadAllBytes("example.file"),
        },
    }
);

// handle response
```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               | Example                                                                   |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `PlanetId`                                                                | *long*                                                                    | :heavy_check_mark:                                                        | The ID of the planet to get                                               | 1                                                                         |
| `RequestBody`                                                             | [UploadImageRequestBody](../../Models/Requests/UploadImageRequestBody.md) | :heavy_minus_sign:                                                        | Image to upload                                                           |                                                                           |

### Response

**[UploadImageResponse](../../Models/Requests/UploadImageResponse.md)**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException | 4XX, 5XX                                                                   | \*/\*                                                                      |