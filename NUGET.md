# Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp


<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

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

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security schemes globally:

| Name            | Type          | Scheme                   |
| --------------- | ------------- | ------------------------ |
| `BearerAuth`    | http          | HTTP Bearer              |
| `BasicAuth`     | http          | HTTP Basic               |
| `ApiKeyQuery`   | apiKey        | API key                  |
| `ApiKeyHeader`  | apiKey        | API key                  |
| `ApiKeyCookie`  | apiKey        | API key                  |
| `OAuth2`        | oauth2        | OAuth2 token             |
| `OpenIdConnect` | openIdConnect | OpenID Connect Discovery |

You can set the security parameters through the `security` optional parameter when initializing the SDK client instance. The selected scheme will be used by default to authenticate with the API for all operations that support it. For example:
```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Components;

var sdk = new DemoApiScalarGalaxy(security: new Security() {
    BearerAuth = "<YOUR_BEARER_TOKEN_HERE>",
});

var res = await sdk.Planets.GetAllDataAsync(
    limit: 10,
    offset: 0
);

// handle response
```
<!-- End Authentication [security] -->

<!-- Start Error Handling [errors] -->
## Error Handling

Handling errors in this SDK should largely match your expectations. All operations return a response object or throw an exception.

By default, an API error will raise a `Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException` exception, which has the following properties:

| Property      | Type                  | Description           |
|---------------|-----------------------|-----------------------|
| `Message`     | *string*              | The error message     |
| `Request`     | *HttpRequestMessage*  | The HTTP request      |
| `Response`    | *HttpResponseMessage* | The HTTP response     |

When custom error responses are specified for an operation, the SDK may also throw their associated exceptions. You can refer to respective *Errors* tables in SDK docs for more details on possible exception types for each operation. For example, the `GetAllDataAsync` method throws the following exceptions:

| Error Type                                                                 | Status Code | Content Type |
| -------------------------------------------------------------------------- | ----------- | ------------ |
| Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException | 4XX, 5XX    | \*/\*        |

### Example

```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors;

var sdk = new DemoApiScalarGalaxy();

try
{
    var res = await sdk.Planets.GetAllDataAsync(
        limit: 10,
        offset: 0
    );

    // handle response
}
catch (Exception ex)
{
    if (ex is Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.Errors.APIException)
    {
        // Handle default exception
        throw;
    }
}
```
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Select Server by Index

You can override the default server globally by passing a server index to the `serverIndex: int` optional parameter when initializing the SDK client instance. The selected server will then be used as the default on the operations that use it. This table lists the indexes associated with the available servers:

| #   | Server                                | Variables             | Description                     |
| --- | ------------------------------------- | --------------------- | ------------------------------- |
| 0   | `https://galaxy.scalar.com`           |                       |                                 |
| 1   | `{protocol}://void.scalar.com/{path}` | `protocol`<br/>`path` | Responds with your request data |

If the selected server has variables, you may override its default values through the additional parameters made available in the SDK constructor:

| Variable   | Parameter                                                                         | Supported Values | Default   | Description |
| ---------- | --------------------------------------------------------------------------------- | ---------------- | --------- | ----------- |
| `protocol` | `protocol: Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp.Models.ServerProtocol` | - `"https"`      | `"https"` |             |
| `path`     | `path: string`                                                                    | string           | `""`      |             |

#### Example

```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;

var sdk = new DemoApiScalarGalaxy(
    serverIndex: 1,
    protocol: "https",
    path: "18258"
);

var res = await sdk.Planets.GetAllDataAsync(
    limit: 10,
    offset: 0
);

// handle response
```

### Override Server URL Per-Client

The default server can also be overridden globally by passing a URL to the `serverUrl: string` optional parameter when initializing the SDK client instance. For example:
```csharp
using Perianayaguyjayaselan.DemoApiScalarGalaxyCsharp;

var sdk = new DemoApiScalarGalaxy(serverUrl: "https://void.scalar.com/");

var res = await sdk.Planets.GetAllDataAsync(
    limit: 10,
    offset: 0
);

// handle response
```
<!-- End Server Selection [server] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->