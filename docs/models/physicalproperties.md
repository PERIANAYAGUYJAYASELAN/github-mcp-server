# PhysicalProperties


## Fields

| Field                                                    | Type                                                     | Required                                                 | Description                                              | Example                                                  |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `mass`                                                   | *Optional[float]*                                        | :heavy_minus_sign:                                       | Mass in Earth masses (must be greater than 0)            | 0.107                                                    |
| `radius`                                                 | *Optional[float]*                                        | :heavy_minus_sign:                                       | Radius in Earth radii (must be greater than 0)           | 0.532                                                    |
| `gravity`                                                | *Optional[float]*                                        | :heavy_minus_sign:                                       | Surface gravity in Earth g                               | 0.378                                                    |
| `temperature`                                            | [Optional[models.Temperature]](../models/temperature.md) | :heavy_minus_sign:                                       | N/A                                                      |                                                          |
| `__pydantic_extra__`                                     | Dict[str, *float*]                                       | :heavy_minus_sign:                                       | N/A                                                      |                                                          |