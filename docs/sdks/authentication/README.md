# Authentication
(*authentication*)

## Overview

Some endpoints are public, but some require authentication. We provide all the required endpoints to create an account and authorize yourself.

### Available Operations

* [create_user_json](#create_user_json) - Create a user
* [create_user_raw](#create_user_raw) - Create a user
* [get_token_json](#get_token_json) - Get a token
* [get_token_raw](#get_token_raw) - Get a token
* [get_me](#get_me) - Get authenticated user

## create_user_json

Time to create a user account, eh?

### Example Usage

```python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.authentication.create_user_json(request={
        "name": "Marc",
        "email": "marc@scalar.com",
        "password": "i-love-scalar",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                     | Type                                                                          | Required                                                                      | Description                                                                   |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| `request`                                                                     | [models.CreateUserJSONRequestBody](../../models/createuserjsonrequestbody.md) | :heavy_check_mark:                                                            | The request object to use for the request.                                    |
| `retries`                                                                     | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)              | :heavy_minus_sign:                                                            | Configuration to override the default retry behavior of the client.           |

### Response

**[models.CreateUserJSONResponse](../../models/createuserjsonresponse.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |

## create_user_raw

Time to create a user account, eh?

### Example Usage

```python
import io
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.authentication.create_user_raw(request=io.BytesIO("{\"name\":\"Marc\",\"email\":\"marc@scalar.com\",\"password\":\"i-love-scalar\"}".encode()))

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `request`                                                                 | [Union[bytes, IO[bytes], io.BufferedReader]](../../models/requestbody.md) | :heavy_check_mark:                                                        | The request object to use for the request.                                |
| `retries`                                                                 | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)          | :heavy_minus_sign:                                                        | Configuration to override the default retry behavior of the client.       |

### Response

**[models.CreateUserRawResponse](../../models/createuserrawresponse.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |

## get_token_json

Yeah, this is the boring security stuff. Just get your super secret token and move on.

### Example Usage

```python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.authentication.get_token_json(request={
        "email": "marc@scalar.com",
        "password": "i-love-scalar",
    })

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [models.Credentials](../../models/credentials.md)                   | :heavy_check_mark:                                                  | The request object to use for the request.                          |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetTokenJSONResponse](../../models/gettokenjsonresponse.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |

## get_token_raw

Yeah, this is the boring security stuff. Just get your super secret token and move on.

### Example Usage

```python
import io
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.authentication.get_token_raw(request=io.BytesIO("{\"email\":\"marc@scalar.com\",\"password\":\"i-love-scalar\"}".encode()))

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `request`                                                                 | [Union[bytes, IO[bytes], io.BufferedReader]](../../models/credentials.md) | :heavy_check_mark:                                                        | The request object to use for the request.                                |
| `retries`                                                                 | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)          | :heavy_minus_sign:                                                        | Configuration to override the default retry behavior of the client.       |

### Response

**[models.GetTokenRawResponse](../../models/gettokenrawresponse.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |

## get_me

Find yourself they say. That's what you can do here.

### Example Usage

```python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.authentication.get_me()

    # Handle response
    print(res)

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `retries`                                                           | [Optional[utils.RetryConfig]](../../models/utils/retryconfig.md)    | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |

### Response

**[models.GetMeResponse](../../models/getmeresponse.md)**

### Errors

| Error Type      | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.APIError | 4XX, 5XX        | \*/\*           |