# Satellite

Every satellite in the Scalar Galaxy


## Fields

| Field                                                        | Type                                                         | Required                                                     | Description                                                  | Example                                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `id`                                                         | *Optional[int]*                                              | :heavy_minus_sign:                                           | N/A                                                          | 1                                                            |
| `name`                                                       | *str*                                                        | :heavy_check_mark:                                           | N/A                                                          | Phobos                                                       |
| `description`                                                | *OptionalNullable[str]*                                      | :heavy_minus_sign:                                           | N/A                                                          | Phobos is the larger and innermost of the two moons of Mars. |
| `diameter`                                                   | *Optional[float]*                                            | :heavy_minus_sign:                                           | Diameter in kilometers                                       | 22.2                                                         |
| `type`                                                       | [models.SatelliteType](../models/satellitetype.md)           | :heavy_check_mark:                                           | N/A                                                          | moon                                                         |
| `orbit`                                                      | [Optional[models.Orbit]](../models/orbit.md)                 | :heavy_minus_sign:                                           | N/A                                                          |                                                              |