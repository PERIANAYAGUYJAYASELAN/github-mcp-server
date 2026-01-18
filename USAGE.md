<!-- Start SDK Example Usage [usage] -->
```typescript
import { DemoApiScalarGalaxy } from "@perianayaguyjayaselan/demo-api-scalar-galaxy-typescript";

const demoApiScalarGalaxy = new DemoApiScalarGalaxy();

async function run() {
  const result = await demoApiScalarGalaxy.planets.getAllData({});

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->