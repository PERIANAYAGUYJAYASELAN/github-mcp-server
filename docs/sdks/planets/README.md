# Planets
(*planets*)

## Overview

Everything about planets

### Available Operations

* [get_all_data](#get_all_data) - Get all planets
* [create_planet_json](#create_planet_json) - Create a planet
* [create_planet_raw](#create_planet_raw) - Create a planet
* [get_planet](#get_planet) - Get a planet
* [update_planet_json](#update_planet_json) - Update a planet
* [update_planet_raw](#update_planet_raw) - Update a planet
* [delete_planet](#delete_planet) - Delete a planet
* [upload_image](#upload_image) - Upload an image to a planet

## get_all_data

It's easy to say you know them all, but do you really? Retrieve all the planets and check whether you missed one.

### Example Usage

```python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.planets.get_all_data(limit=10, offset=0)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                             | Type                                                                  | Required                                                              | Description                                                           |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `limit`                                                               | *Optional[int]*                                                       | :heavy_minus_sign:                                                    | The number of items to return                                         |
| `offset`                                                              | *Optional[int]*                                                       | :heavy_minus_sign:                                                    | The number of items to skip before starting to collect the result set |
| `retries`                                                             | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)      | :heavy_minus_sign:                                                    | Configuration to override the default retry behavior of the client.   |

### Response

**[models.GetAllDataResponse](../../models/getalldataresponse.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |

## create_planet_json

Time to play god and create a new planet. What do you think? Ah, don't think too much. What could go wrong anyway?

### Example Usage

```python
import perianayaguyjayaselan_demo_api_scalar_galaxy_python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy
from perianayaguyjayaselan_demo_api_scalar_galaxy_python.utils import parse_datetime


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.planets.create_planet_json(request=perianayaguyjayaselan_demo_api_scalar_galaxy_python.PlanetInput(
        name="Mars",
        description="The red planet",
        type=perianayaguyjayaselan_demo_api_scalar_galaxy_python.Type.TERRESTRIAL,
        habitability_index=0.68,
        physical_properties=perianayaguyjayaselan_demo_api_scalar_galaxy_python.PhysicalProperties(
            mass=0.107,
            radius=0.532,
            gravity=0.378,
            temperature=perianayaguyjayaselan_demo_api_scalar_galaxy_python.Temperature(
                min=130,
                max=308,
                average=210,
            ),
        ),
        atmosphere=[
            perianayaguyjayaselan_demo_api_scalar_galaxy_python.Atmosphere(
                compound="CO2",
                percentage=95.3,
            ),
        ],
        discovered_at=parse_datetime("1610-01-07T00:00:00Z"),
        image="https://cdn.scalar.com/photos/mars.jpg",
        satellites=[
            perianayaguyjayaselan_demo_api_scalar_galaxy_python.SatelliteInput(
                name="Phobos",
                description="Phobos is the larger and innermost of the two moons of Mars.",
                diameter=22.2,
                type=perianayaguyjayaselan_demo_api_scalar_galaxy_python.SatelliteType.MOON,
                orbit=perianayaguyjayaselan_demo_api_scalar_galaxy_python.Orbit(
                    planet_id=1,
                    orbital_period=0.319,
                    distance=9376,
                ),
            ),
        ],
        creator=perianayaguyjayaselan_demo_api_scalar_galaxy_python.UserInput(
            name="Marc",
        ),
        tags=[
            "solar-system",
            "rocky",
            "explored",
        ],
        success_callback_url="https://example.com/webhook",
        failure_callback_url="https://example.com/webhook",
    ))

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [models.PlanetInput](../../models/planetinput.md)                   | :heavy_check_mark:                                                  | The request object to use for the request.                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.CreatePlanetJSONResponse](../../models/createplanetjsonresponse.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |

## create_planet_raw

Time to play god and create a new planet. What do you think? Ah, don't think too much. What could go wrong anyway?

### Example Usage

```python
import io
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.planets.create_planet_raw(request=io.BytesIO("{\"name\":\"Mars\",\"description\":\"The red planet\",\"type\":\"terrestrial\",\"habitabilityIndex\":0.68,\"physicalProperties\":{\"mass\":0.107,\"radius\":0.532,\"gravity\":0.378,\"temperature\":{\"min\":130,\"max\":308,\"average\":210}},\"atmosphere\":[{\"compound\":\"CO2\",\"percentage\":95.3}],\"discoveredAt\":\"1610-01-07T00:00:00Z\",\"image\":\"https://cdn.scalar.com/photos/mars.jpg\",\"satellites\":[{\"name\":\"Phobos\",\"description\":\"Phobos is the larger and innermost of the two moons of Mars.\",\"diameter\":22.2,\"type\":\"moon\",\"orbit\":{\"planetId\":1,\"orbitalPeriod\":0.319,\"distance\":9376}}],\"creator\":{\"name\":\"Marc\"},\"tags\":[\"solar-system\",\"rocky\",\"explored\"],\"successCallbackUrl\":\"https://example.com/webhook\",\"failureCallbackUrl\":\"https://example.com/webhook\"}".encode()))

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                            | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `request`                                                            | [Union[bytes, IO[bytes], io.BufferedReader]](../../models/planet.md) | :heavy_check_mark:                                                   | The request object to use for the request.                           |
| `retries`                                                            | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)     | :heavy_minus_sign:                                                   | Configuration to override the default retry behavior of the client.  |

### Response

**[models.CreatePlanetRawResponse](../../models/createplanetrawresponse.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |

## get_planet

You'll better learn a little bit more about the planets. It might come in handy once space travel is available for everyone.

### Example Usage

```python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.planets.get_planet(planet_id=1)

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `planet_id`                                                         | *int*                                                               | :heavy_check_mark:                                                  | The ID of the planet to get                                         | 1                                                                   |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.GetPlanetResponse](../../models/getplanetresponse.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |

## update_planet_json

Sometimes you make mistakes, that's fine. No worries, you can update all planets.

### Example Usage

```python
import perianayaguyjayaselan_demo_api_scalar_galaxy_python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy
from perianayaguyjayaselan_demo_api_scalar_galaxy_python.utils import parse_datetime


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.planets.update_planet_json(planet_id=1, name="Mars", type_=perianayaguyjayaselan_demo_api_scalar_galaxy_python.Type.TERRESTRIAL, description="The red planet", habitability_index=0.68, physical_properties=perianayaguyjayaselan_demo_api_scalar_galaxy_python.PhysicalProperties(
        mass=0.107,
        radius=0.532,
        gravity=0.378,
        temperature=perianayaguyjayaselan_demo_api_scalar_galaxy_python.Temperature(
            min=130,
            max=308,
            average=210,
        ),
    ), atmosphere=[
        perianayaguyjayaselan_demo_api_scalar_galaxy_python.Atmosphere(
            compound="CO2",
            percentage=95.3,
        ),
    ], discovered_at=parse_datetime("1610-01-07T00:00:00Z"), image="https://cdn.scalar.com/photos/mars.jpg", satellites=[
        {
            "name": "Phobos",
            "description": "Phobos is the larger and innermost of the two moons of Mars.",
            "diameter": 22.2,
            "type": perianayaguyjayaselan_demo_api_scalar_galaxy_python.SatelliteType.MOON,
            "orbit": {
                "planet_id": 1,
                "orbital_period": 0.319,
                "distance": 9376,
            },
        },
    ], creator={
        "name": "Marc",
    }, tags=[
        "solar-system",
        "rocky",
        "explored",
    ], success_callback_url="https://example.com/webhook", failure_callback_url="https://example.com/webhook")

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               | Example                                                                   |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `planet_id`                                                               | *int*                                                                     | :heavy_check_mark:                                                        | The ID of the planet to get                                               | 1                                                                         |
| `name`                                                                    | *str*                                                                     | :heavy_check_mark:                                                        | N/A                                                                       | Mars                                                                      |
| `type`                                                                    | [models.Type](../../models/type.md)                                       | :heavy_check_mark:                                                        | N/A                                                                       | terrestrial                                                               |
| `description`                                                             | *OptionalNullable[str]*                                                   | :heavy_minus_sign:                                                        | N/A                                                                       | The red planet                                                            |
| `habitability_index`                                                      | *Optional[float]*                                                         | :heavy_minus_sign:                                                        | A score from 0 to 1 indicating potential habitability                     | 0.68                                                                      |
| `physical_properties`                                                     | [Optional[models.PhysicalProperties]](../../models/physicalproperties.md) | :heavy_minus_sign:                                                        | N/A                                                                       |                                                                           |
| `atmosphere`                                                              | List[[models.Atmosphere](../../models/atmosphere.md)]                     | :heavy_minus_sign:                                                        | Atmospheric composition                                                   |                                                                           |
| `discovered_at`                                                           | [date](https://docs.python.org/3/library/datetime.html#date-objects)      | :heavy_minus_sign:                                                        | N/A                                                                       | 1610-01-07T00:00:00Z                                                      |
| `image`                                                                   | *OptionalNullable[str]*                                                   | :heavy_minus_sign:                                                        | N/A                                                                       | https://cdn.scalar.com/photos/mars.jpg                                    |
| `satellites`                                                              | List[[models.SatelliteInput](../../models/satelliteinput.md)]             | :heavy_minus_sign:                                                        | N/A                                                                       |                                                                           |
| `creator`                                                                 | [Optional[models.UserInput]](../../models/userinput.md)                   | :heavy_minus_sign:                                                        | A user                                                                    |                                                                           |
| `tags`                                                                    | List[*str*]                                                               | :heavy_minus_sign:                                                        | N/A                                                                       | [<br/>"solar-system",<br/>"rocky",<br/>"explored"<br/>]                   |
| `success_callback_url`                                                    | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | URL which gets invoked upon a successful operation                        | https://example.com/webhook                                               |
| `failure_callback_url`                                                    | *Optional[str]*                                                           | :heavy_minus_sign:                                                        | URL which gets invoked upon a failed operation                            | https://example.com/webhook                                               |
| `retries`                                                                 | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)          | :heavy_minus_sign:                                                        | Configuration to override the default retry behavior of the client.       |                                                                           |

### Response

**[models.UpdatePlanetJSONResponse](../../models/updateplanetjsonresponse.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |

## update_planet_raw

Sometimes you make mistakes, that's fine. No worries, you can update all planets.

### Example Usage

```python
import io
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.planets.update_planet_raw(planet_id=1, planet=io.BytesIO("{\"name\":\"Mars\",\"description\":\"The red planet\",\"type\":\"terrestrial\",\"habitabilityIndex\":0.68,\"physicalProperties\":{\"mass\":0.107,\"radius\":0.532,\"gravity\":0.378,\"temperature\":{\"min\":130,\"max\":308,\"average\":210}},\"atmosphere\":[{\"compound\":\"CO2\",\"percentage\":95.3}],\"discoveredAt\":\"1610-01-07T00:00:00Z\",\"image\":\"https://cdn.scalar.com/photos/mars.jpg\",\"satellites\":[{\"name\":\"Phobos\",\"description\":\"Phobos is the larger and innermost of the two moons of Mars.\",\"diameter\":22.2,\"type\":\"moon\",\"orbit\":{\"planetId\":1,\"orbitalPeriod\":0.319,\"distance\":9376}}],\"creator\":{\"name\":\"Marc\"},\"tags\":[\"solar-system\",\"rocky\",\"explored\"],\"successCallbackUrl\":\"https://example.com/webhook\",\"failureCallbackUrl\":\"https://example.com/webhook\"}".encode()))

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `planet_id`                                                         | *int*                                                               | :heavy_check_mark:                                                  | The ID of the planet to get                                         | 1                                                                   |
| `planet`                                                            | *Optional[Union[bytes, IO[bytes], io.BufferedReader]]*              | :heavy_minus_sign:                                                  | New information about the planet                                    |                                                                     |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.UpdatePlanetRawResponse](../../models/updateplanetrawresponse.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |

## delete_planet

This endpoint was used to delete planets. Unfortunately, that caused a lot of trouble for planets with life. So, this endpoint is now deprecated and should not be used anymore.

### Example Usage

```python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    demo_api_scalar_galaxy.planets.delete_planet(planet_id=1)

    # Use the SDK ...

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `planet_id`                                                         | *int*                                                               | :heavy_check_mark:                                                  | The ID of the planet to get                                         | 1                                                                   |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |

## upload_image

Got a crazy good photo of a planet? Share it with the world!

### Example Usage

```python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.planets.upload_image(planet_id=1, image={
        "file_name": "example.file",
        "content": open("example.file", "rb"),
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `planet_id`                                                         | *int*                                                               | :heavy_check_mark:                                                  | The ID of the planet to get                                         | 1                                                                   |
| `image`                                                             | [Optional[models.Image]](../../models/image.md)                     | :heavy_minus_sign:                                                  | The image file to upload                                            | @mars.jpg                                                           |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |                                                                     |

### Response

**[models.UploadImageResponse](../../models/uploadimageresponse.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |