# CelestialBodies
(*celestial_bodies*)

## Overview

Celestial bodies are the planets and satellites in the Scalar Galaxy.

### Available Operations

* [create_celestial_body](#create_celestial_body) - Create a celestial body

## create_celestial_body

Create a celestial body

### Example Usage

```python
import perianayaguyjayaselan_demo_api_scalar_galaxy_python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.celestial_bodies.create_celestial_body(request={
        "name": "Phobos",
        "type": perianayaguyjayaselan_demo_api_scalar_galaxy_python.SatelliteType.SATELLITE,
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [models.CelestialBodyInput](../../models/celestialbodyinput.md)     | :heavy_check_mark:                                                  | The request object to use for the request.                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CelestialBody](../../models/celestialbody.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |