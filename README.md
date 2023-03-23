# Usage
```typescript
import {RatingApi, Configuration} from '@babbiorsetto/dhl-typescript-fetch-client'

const config: Configuration = {
    username: 'MyApiKey',
    password: 'MyApiSecret'
}
const rating = new RatingApi(config, 'https://express.api.dhl.com/mydhlapi/test')

try {
    const resp = await rating.expApiRates('accountNumber', /*All required info*/)
    console.log(JSON.stringify(resp.products))
} catch(err) {
    console.log(err)
    // The body of the error message
    // Has a detailed description in the 'detail' field
    const errBody: SupermodelIoLogisticsExpressErrorResponse = await err.json()
    console.log(errBody.detail)
}
```

Full description of the API in the [official documentation](https://developer.dhl.com/api-reference/dhl-express-mydhl-api#reference-docs-section)
