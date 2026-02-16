# Authentication
(*Authentication*)

## Overview

Some endpoints are public, but some require authentication. We provide all the required endpoints to create an account and authorize yourself.

### Available Operations

* [CreateUserJson](#createuserjson) - Create a user
* [CreateUserRaw](#createuserraw) - Create a user
* [GetTokenJson](#gettokenjson) - Get a token
* [GetTokenRaw](#gettokenraw) - Get a token
* [GetMe](#getme) - Get authenticated user

## CreateUserJson

Time to create a user account, eh?

### Example Usage

```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Requests;

var sdk = new DemoApiScalarGalaxy();

CreateUserJsonRequestBody req = new CreateUserJsonRequestBody() {
    Name = "Marc",
    Email = "marc@scalar.com",
    Password = "i-love-scalar",
};

var res = await sdk.Authentication.CreateUserJsonAsync(req);

// handle response
```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `request`                                                                       | [CreateUserJsonRequestBody](../../Models/Requests/CreateUserJsonRequestBody.md) | :heavy_check_mark:                                                              | The request object to use for the request.                                      |

### Response

**[CreateUserJsonResponse](../../Models/Requests/CreateUserJsonResponse.md)**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException | 4XX, 5XX                                                                   | \*/\*                                                                      |

## CreateUserRaw

Time to create a user account, eh?

### Example Usage

```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;
using System;

var sdk = new DemoApiScalarGalaxy();

byte[] req = System.Text.Encoding.UTF8.GetBytes("{\"password\":\"i-love-scalar\",\"name\":\"Marc\",\"email\":\"marc@scalar.com\"}");

var res = await sdk.Authentication.CreateUserRawAsync(req);

// handle response
```

### Parameters

| Parameter                                  | Type                                       | Required                                   | Description                                |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| `request`                                  | *byte[]*                                   | :heavy_check_mark:                         | The request object to use for the request. |

### Response

**[CreateUserRawResponse](../../Models/Requests/CreateUserRawResponse.md)**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException | 4XX, 5XX                                                                   | \*/\*                                                                      |

## GetTokenJson

Yeah, this is the boring security stuff. Just get your super secret token and move on.

### Example Usage

```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Components;

var sdk = new DemoApiScalarGalaxy();

Credentials req = new Credentials() {
    Email = "marc@scalar.com",
    Password = "i-love-scalar",
};

var res = await sdk.Authentication.GetTokenJsonAsync(req);

// handle response
```

### Parameters

| Parameter                                             | Type                                                  | Required                                              | Description                                           |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `request`                                             | [Credentials](../../Models/Components/Credentials.md) | :heavy_check_mark:                                    | The request object to use for the request.            |

### Response

**[GetTokenJsonResponse](../../Models/Requests/GetTokenJsonResponse.md)**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException | 4XX, 5XX                                                                   | \*/\*                                                                      |

## GetTokenRaw

Yeah, this is the boring security stuff. Just get your super secret token and move on.

### Example Usage

```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;
using System;

var sdk = new DemoApiScalarGalaxy();

byte[] req = System.Text.Encoding.UTF8.GetBytes("{\"email\":\"marc@scalar.com\",\"password\":\"i-love-scalar\"}");

var res = await sdk.Authentication.GetTokenRawAsync(req);

// handle response
```

### Parameters

| Parameter                                  | Type                                       | Required                                   | Description                                |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| `request`                                  | *byte[]*                                   | :heavy_check_mark:                         | The request object to use for the request. |

### Response

**[GetTokenRawResponse](../../Models/Requests/GetTokenRawResponse.md)**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException | 4XX, 5XX                                                                   | \*/\*                                                                      |

## GetMe

Find yourself they say. That's what you can do here.

### Example Usage

```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;

var sdk = new DemoApiScalarGalaxy();

var res = await sdk.Authentication.GetMeAsync();

// handle response
```

### Response

**[GetMeResponse](../../Models/Requests/GetMeResponse.md)**

### Errors

| Error Type                                                                 | Status Code                                                                | Content Type                                                               |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException | 4XX, 5XX                                                                   | \*/\*                                                                      |