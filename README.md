# demo-api-scalar-galaxy-python

Developer-friendly, idiomatic Python SDK for the *demo-api-scalar-galaxy-python* API.

<div align="left">
    <a href="https://www.scalar.com/?utm_source=demo-api-scalar-galaxy-python&utm_campaign=python"><img src="https://custom-icon-badges.demolab.com/badge/-Built%20By%20scalar+speakeasy-212015?style=for-the-badge&logo=scalar&labelColor=252525" /></a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" style="width: 100px; height: 28px;" />
    </a>
</div>

<br />

## Summary

Demo API (Scalar Galaxy): The Scalar Galaxy is an example OpenAPI document to test OpenAPI tools and libraries. It's a fictional universe with fictional planets and fictional data. Get all the data for [all planets](#tag/planets/get/planets).

## Resources

* https://github.com/scalar/scalar
* https://github.com/OAI/OpenAPI-Specification
* https://scalar.com

## Markdown Support

All descriptions *can* contain ~~tons of text~~ **Markdown**. [If GitHub supports the syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax), chances are we're supporting it, too. You can even create [internal links to reference endpoints](#tag/authentication/post/user/signup).

<details>
  <summary>Examples</summary>

  **Blockquotes**

  > I love OpenAPI. <3

  **Tables**

  | Feature          | Availability |
  | ---------------- | ------------ |
  | Markdown Support | ✓            |

  **Accordion**

  ```html
  <details>
    <summary>Using Details Tags</summary>
    <p>HTML Example</p>
  </details>
  ```

  **Images**

  Yes, there's support for images, too!

  ![Empty placeholder image showing the width/height](https://images.placeholders.dev/?width=1280&height=720)

  **Alerts**

  > [!tip]
  > You can now use markdown alerts in your descriptions.

</details>


For more information about the API: [Documentation](https://github.com/scalar/scalar)
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [perianayaguyjayaselan-demo-api-scalar-galaxy-python](#perianayaguyjayaselan-demo-api-scalar-galaxy-python)
  * [Resources](#resources)
  * [Markdown Support](#markdown-support)
* [/// script](#script)
* [requires-python = ">=3.9"](#requires-python-39)
* [dependencies = [](#dependencies)
* ["perianayaguyjayaselan-demo-api-scalar-galaxy-python",](#perianayaguyjayaselan-demo-api-scalar-galaxy-python-1)
* []](#)
* [///](#-1)
* [Rest of script here...](#rest-of-script-here)
* [Synchronous Example](#synchronous-example)
* [Asynchronous Example](#asynchronous-example)
* [Or when using async:](#or-when-using-async)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

> [!NOTE]
> **Python version upgrade policy**
>
> Once a Python version reaches its [official end of life date](https://devguide.python.org/versions/), a 3-month grace period is provided for users to upgrade. Following this grace period, the minimum python version supported in the SDK will be updated.

The SDK can be installed with either *pip* or *poetry* package managers.

### PIP

*PIP* is the default package installer for Python, enabling easy installation and management of packages from PyPI via the command line.

```bash
pip install perianayaguyjayaselan-demo-api-scalar-galaxy-python
```

### Poetry

*Poetry* is a modern tool that simplifies dependency management and package publishing by using a single `pyproject.toml` file to handle project metadata and dependencies.

```bash
poetry add perianayaguyjayaselan-demo-api-scalar-galaxy-python
```

### Shell and script usage with `uv`

You can use this SDK in a Python shell with [uv](https://docs.astral.sh/uv/) and the `uvx` command that comes with it like so:

```shell
uvx --from perianayaguyjayaselan-demo-api-scalar-galaxy-python python
```

It's also possible to write a standalone Python script without needing to set up a whole project like so:

```python
#!/usr/bin/env -S uv run --script
# /// script
# requires-python = ">=3.9"
# dependencies = [
#     "perianayaguyjayaselan-demo-api-scalar-galaxy-python",
# ]
# ///

from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy

sdk = DemoAPIScalarGalaxy(
  # SDK arguments
)

# Rest of script here...
```

Once that is saved to a file, you can run it with `uv run script.py` where
`script.py` can be replaced with the actual file name.
<!-- End SDK Installation [installation] -->

<!-- Start IDE Support [idesupport] -->
## IDE Support

### PyCharm

Generally, the SDK will work well with most IDEs out of the box. However, when using PyCharm, you can enjoy much better integration with Pydantic by installing an additional plugin.

- [PyCharm Pydantic Plugin](https://docs.pydantic.dev/latest/integrations/pycharm/)
<!-- End IDE Support [idesupport] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

```python
# Synchronous Example
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.planets.get_all_data(limit=10, offset=0)

    # Handle response
    print(res)
```

</br>

The same SDK client can also be used to make asychronous requests by importing asyncio.
```python
# Asynchronous Example
import asyncio
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy

async def main():

    async with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

        res = await demo_api_scalar_galaxy.planets.get_all_data_async(limit=10, offset=0)

        # Handle response
        print(res)

asyncio.run(main())
```
<!-- End SDK Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security schemes globally:

| Name              | Type          | Scheme                   |
| ----------------- | ------------- | ------------------------ |
| `bearer_auth`     | http          | HTTP Bearer              |
| `basic_auth`      | http          | HTTP Basic               |
| `api_key_query`   | apiKey        | API key                  |
| `api_key_header`  | apiKey        | API key                  |
| `api_key_cookie`  | apiKey        | API key                  |
| `o_auth2`         | oauth2        | OAuth2 token             |
| `open_id_connect` | openIdConnect | OpenID Connect Discovery |

You can set the security parameters through the `security` optional parameter when initializing the SDK client instance. The selected scheme will be used by default to authenticate with the API for all operations that support it. For example:
```python
import perianayaguyjayaselan_demo_api_scalar_galaxy_python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy(
    security=perianayaguyjayaselan_demo_api_scalar_galaxy_python.Security(
        bearer_auth="<YOUR_BEARER_TOKEN_HERE>",
    ),
) as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.planets.get_all_data(limit=10, offset=0)

    # Handle response
    print(res)

```
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>

### [authentication](docs/sdks/authentication/README.md)

* [create_user_json](docs/sdks/authentication/README.md#create_user_json) - Create a user
* [create_user_raw](docs/sdks/authentication/README.md#create_user_raw) - Create a user
* [get_token_json](docs/sdks/authentication/README.md#get_token_json) - Get a token
* [get_token_raw](docs/sdks/authentication/README.md#get_token_raw) - Get a token
* [get_me](docs/sdks/authentication/README.md#get_me) - Get authenticated user

### [celestial_bodies](docs/sdks/celestialbodies/README.md)

* [create_celestial_body](docs/sdks/celestialbodies/README.md#create_celestial_body) - Create a celestial body


### [planets](docs/sdks/planets/README.md)

* [get_all_data](docs/sdks/planets/README.md#get_all_data) - Get all planets
* [create_planet_json](docs/sdks/planets/README.md#create_planet_json) - Create a planet
* [create_planet_raw](docs/sdks/planets/README.md#create_planet_raw) - Create a planet
* [get_planet](docs/sdks/planets/README.md#get_planet) - Get a planet
* [update_planet_json](docs/sdks/planets/README.md#update_planet_json) - Update a planet
* [update_planet_raw](docs/sdks/planets/README.md#update_planet_raw) - Update a planet
* [delete_planet](docs/sdks/planets/README.md#delete_planet) - Delete a planet
* [upload_image](docs/sdks/planets/README.md#upload_image) - Upload an image to a planet

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start File uploads [file-upload] -->
## File uploads

Certain SDK methods accept file objects as part of a request body or multi-part request. It is possible and typically recommended to upload files as a stream rather than reading the entire contents into memory. This avoids excessive memory consumption and potentially crashing with out-of-memory errors when working with very large files. The following example demonstrates how to attach a file stream to a request.

> [!TIP]
>
> For endpoints that handle file uploads bytes arrays can also be used. However, using streams is recommended for large files.
>

```python
import io
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.planets.create_planet_raw(request=io.BytesIO("{\"name\":\"Mars\",\"description\":\"The red planet\",\"type\":\"terrestrial\",\"habitabilityIndex\":0.68,\"physicalProperties\":{\"mass\":0.107,\"radius\":0.532,\"gravity\":0.378,\"temperature\":{\"min\":130,\"max\":308,\"average\":210}},\"atmosphere\":[{\"compound\":\"CO2\",\"percentage\":95.3}],\"discoveredAt\":\"1610-01-07T00:00:00Z\",\"image\":\"https://cdn.scalar.com/photos/mars.jpg\",\"satellites\":[{\"name\":\"Phobos\",\"description\":\"Phobos is the larger and innermost of the two moons of Mars.\",\"diameter\":22.2,\"type\":\"moon\",\"orbit\":{\"planetId\":1,\"orbitalPeriod\":0.319,\"distance\":9376}}],\"creator\":{\"name\":\"Marc\"},\"tags\":[\"solar-system\",\"rocky\",\"explored\"],\"successCallbackUrl\":\"https://example.com/webhook\",\"failureCallbackUrl\":\"https://example.com/webhook\"}".encode()))

    # Handle response
    print(res)

```
<!-- End File uploads [file-upload] -->

<!-- Start Retries [retries] -->
## Retries

Some of the endpoints in this SDK support retries. If you use the SDK without any configuration, it will fall back to the default retry strategy provided by the API. However, the default retry strategy can be overridden on a per-operation basis, or across the entire SDK.

To change the default retry strategy for a single API call, simply provide a `RetryConfig` object to the call:
```python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy
from perianayaguyjayaselan_demo_api_scalar_galaxy_python.utils import BackoffStrategy, RetryConfig


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.planets.get_all_data(limit=10, offset=0,
        RetryConfig("backoff", BackoffStrategy(1, 50, 1.1, 100), False))

    # Handle response
    print(res)

```

If you'd like to override the default retry strategy for all operations that support retries, you can use the `retry_config` optional parameter when initializing the SDK:
```python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy
from perianayaguyjayaselan_demo_api_scalar_galaxy_python.utils import BackoffStrategy, RetryConfig


with DemoAPIScalarGalaxy(
    retry_config=RetryConfig("backoff", BackoffStrategy(1, 50, 1.1, 100), False),
) as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.planets.get_all_data(limit=10, offset=0)

    # Handle response
    print(res)

```
<!-- End Retries [retries] -->

<!-- Start Error Handling [errors] -->
## Error Handling

Handling errors in this SDK should largely match your expectations. All operations return a response object or raise an exception.

By default, an API error will raise a models.APIError exception, which has the following properties:

| Property        | Type             | Description           |
|-----------------|------------------|-----------------------|
| `.status_code`  | *int*            | The HTTP status code  |
| `.message`      | *str*            | The error message     |
| `.raw_response` | *httpx.Response* | The raw HTTP response |
| `.body`         | *str*            | The response content  |

When custom error responses are specified for an operation, the SDK may also raise their associated exceptions. You can refer to respective *Errors* tables in SDK docs for more details on possible exception types for each operation. For example, the `get_all_data_async` method may raise the following exceptions:

| Error Type      | Status Code | Content Type |
| --------------- | ----------- | ------------ |
| models.APIError | 4XX, 5XX    | \*/\*        |

### Example

```python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy, models


with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:
    res = None
    try:

        res = demo_api_scalar_galaxy.planets.get_all_data(limit=10, offset=0)

        # Handle response
        print(res)

    except models.APIError as e:
        # handle exception
        raise(e)
```
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Select Server by Index

You can override the default server globally by passing a server index to the `server_idx: int` optional parameter when initializing the SDK client instance. The selected server will then be used as the default on the operations that use it. This table lists the indexes associated with the available servers:

| #   | Server                                | Variables             | Description                     |
| --- | ------------------------------------- | --------------------- | ------------------------------- |
| 0   | `https://galaxy.scalar.com`           |                       |                                 |
| 1   | `{protocol}://void.scalar.com/{path}` | `protocol`<br/>`path` | Responds with your request data |

If the selected server has variables, you may override its default values through the additional parameters made available in the SDK constructor:

| Variable   | Parameter                         | Supported Values | Default   | Description |
| ---------- | --------------------------------- | ---------------- | --------- | ----------- |
| `protocol` | `protocol: models.ServerProtocol` | - `"https"`      | `"https"` |             |
| `path`     | `path: str`                       | str              | `""`      |             |

#### Example

```python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy(
    server_idx=1,
    protocol="https"
    path="18258"
) as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.planets.get_all_data(limit=10, offset=0)

    # Handle response
    print(res)

```

### Override Server URL Per-Client

The default server can also be overridden globally by passing a URL to the `server_url: str` optional parameter when initializing the SDK client instance. For example:
```python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy


with DemoAPIScalarGalaxy(
    server_url="https://void.scalar.com/",
) as demo_api_scalar_galaxy:

    res = demo_api_scalar_galaxy.planets.get_all_data(limit=10, offset=0)

    # Handle response
    print(res)

```
<!-- End Server Selection [server] -->

<!-- Start Custom HTTP Client [http-client] -->
## Custom HTTP Client

The Python SDK makes API calls using the [httpx](https://www.python-httpx.org/) HTTP library.  In order to provide a convenient way to configure timeouts, cookies, proxies, custom headers, and other low-level configuration, you can initialize the SDK client with your own HTTP client instance.
Depending on whether you are using the sync or async version of the SDK, you can pass an instance of `HttpClient` or `AsyncHttpClient` respectively, which are Protocol's ensuring that the client has the necessary methods to make API calls.
This allows you to wrap the client with your own custom logic, such as adding custom headers, logging, or error handling, or you can just pass an instance of `httpx.Client` or `httpx.AsyncClient` directly.

For example, you could specify a header for every request that this sdk makes as follows:
```python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy
import httpx

http_client = httpx.Client(headers={"x-custom-header": "someValue"})
s = DemoAPIScalarGalaxy(client=http_client)
```

or you could wrap the client with your own custom logic:
```python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy
from perianayaguyjayaselan_demo_api_scalar_galaxy_python.httpclient import AsyncHttpClient
import httpx

class CustomClient(AsyncHttpClient):
    client: AsyncHttpClient

    def __init__(self, client: AsyncHttpClient):
        self.client = client

    async def send(
        self,
        request: httpx.Request,
        *,
        stream: bool = False,
        auth: Union[
            httpx._types.AuthTypes, httpx._client.UseClientDefault, None
        ] = httpx.USE_CLIENT_DEFAULT,
        follow_redirects: Union[
            bool, httpx._client.UseClientDefault
        ] = httpx.USE_CLIENT_DEFAULT,
    ) -> httpx.Response:
        request.headers["Client-Level-Header"] = "added by client"

        return await self.client.send(
            request, stream=stream, auth=auth, follow_redirects=follow_redirects
        )

    def build_request(
        self,
        method: str,
        url: httpx._types.URLTypes,
        *,
        content: Optional[httpx._types.RequestContent] = None,
        data: Optional[httpx._types.RequestData] = None,
        files: Optional[httpx._types.RequestFiles] = None,
        json: Optional[Any] = None,
        params: Optional[httpx._types.QueryParamTypes] = None,
        headers: Optional[httpx._types.HeaderTypes] = None,
        cookies: Optional[httpx._types.CookieTypes] = None,
        timeout: Union[
            httpx._types.TimeoutTypes, httpx._client.UseClientDefault
        ] = httpx.USE_CLIENT_DEFAULT,
        extensions: Optional[httpx._types.RequestExtensions] = None,
    ) -> httpx.Request:
        return self.client.build_request(
            method,
            url,
            content=content,
            data=data,
            files=files,
            json=json,
            params=params,
            headers=headers,
            cookies=cookies,
            timeout=timeout,
            extensions=extensions,
        )

s = DemoAPIScalarGalaxy(async_client=CustomClient(httpx.AsyncClient()))
```
<!-- End Custom HTTP Client [http-client] -->

<!-- Start Resource Management [resource-management] -->
## Resource Management

The `DemoAPIScalarGalaxy` class implements the context manager protocol and registers a finalizer function to close the underlying sync and async HTTPX clients it uses under the hood. This will close HTTP connections, release memory and free up other resources held by the SDK. In short-lived Python programs and notebooks that make a few SDK method calls, resource management may not be a concern. However, in longer-lived programs, it is beneficial to create a single SDK instance via a [context manager][context-manager] and reuse it across the application.

[context-manager]: https://docs.python.org/3/reference/datamodel.html#context-managers

```python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy
def main():

    with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:
        # Rest of application here...


# Or when using async:
async def amain():

    async with DemoAPIScalarGalaxy() as demo_api_scalar_galaxy:
        # Rest of application here...
```
<!-- End Resource Management [resource-management] -->

<!-- Start Debugging [debug] -->
## Debugging

You can setup your SDK to emit debug logs for SDK requests and responses.

You can pass your own logger class directly into your SDK.
```python
from perianayaguyjayaselan_demo_api_scalar_galaxy_python import DemoAPIScalarGalaxy
import logging

logging.basicConfig(level=logging.DEBUG)
s = DemoAPIScalarGalaxy(debug_logger=logging.getLogger("perianayaguyjayaselan_demo_api_scalar_galaxy_python"))
```
<!-- End Debugging [debug] -->

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release.

### SDK Created by [Scalar](https://www.scalar.com/?utm_source=demo-api-scalar-galaxy-python&utm_campaign=python)