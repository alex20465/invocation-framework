# Invocation framework (PROJECT IS NOT IMPLEMENTED YET)

The invocation framework invokes exposed web-based service-methods based on SaaS/FaaS paradigm, it generates the service exposed interface to describe the functionality of the service.


## Features

- Abstract simplified invocations using service unit.
- Serverless provider integration (AWS-Lambda, Google-Functions etc.)
- Support graphQL
- Generate interface descriptions using the provider API/SDK or GraphQL documentation
- Service invocation schema validation
- Middleware support before/after invocations

## Example Usage

```javascript
const {AWSService} = require('invocation-framework');

const carService = new AWSService({
    service: 'my-car-service',
    stage: 'dev'
});
```

This code generates the service description files, the process is quite slow. Execute this process as project build task.

```javascript
carService.generate()
    .then(() => carService.getMyCar()) // invokes a service method
    .then(({car}) => {
        console.log(car);
    });
```
