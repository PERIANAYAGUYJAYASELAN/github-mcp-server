# UpdatePlanetRawRequest


## Fields

| Field                                                  | Type                                                   | Required                                               | Description                                            | Example                                                |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| `planet_id`                                            | *int*                                                  | :heavy_check_mark:                                     | The ID of the planet to get                            | 1                                                      |
| `planet`                                               | *Optional[Union[bytes, IO[bytes], io.BufferedReader]]* | :heavy_minus_sign:                                     | New information about the planet                       |                                                        |