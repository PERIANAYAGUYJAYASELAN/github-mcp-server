<!-- Start SDK Example Usage [usage] -->
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