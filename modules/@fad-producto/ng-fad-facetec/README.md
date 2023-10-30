# Getting started

## Installation

**Angular 9**

``` bash
npm install @fad-producto/ng-fad-facetec
```

**Angular 16**

``` bash
npm install @fad-producto/ng-fad-facetec --tag ng16
```

## Assets
Add into the assets array (*angular.json*) the next lines:
``` json
{
  "glob": "**/*",
  "input": "node_modules/@fad-producto/ng-fad-facetec/assets",
  "output": "./assets/"
}
``` 
### Example:
```json
"architect": {
  "build": {
    "options": {
      "assets": [
        "src/favicon.ico",
        "src/assets",
        {
          "glob": "**/*",
          "input": "node_modules/@fad-producto/ng-fad-facetec/assets",
          "output": "./assets/"
        }
      ],
    }
  }
}
```


## Import

In the file **necessary** *example.module.ts* import the module.

In this case  *app.module.ts*

``` ts
import { NgFadFacetecModule } from '@fad-producto/ng-fad-facetec';
.
.
.
... imports: [
       ...,
       BrowserAnimationsModule 
       NgFadFacetecModule
    ]...
```

# Usage

## HTML


Add the selector inside some component and configure the output events:


``` html
<ng-fad-facetec
  [credentials]="credentials"
  [configuration]="configuration"
  (onerror)="onerror($event)"
  (oncomplete)="oncomplete($event)">
</ng-fad-facetec>
```

## Typescript 

Listen to the events:

``` ts
import { IFacetecConfiguration, ResponseError, ResponseSuccess, ErrorCode, CONFIGURATION_DEFAULT, Credentials} from '@fad-producto/ng-fad-facetec';
const CREDENTIALS: Credentials = {
  deviceKeyIdentifier: 'XXXXXXXXXXXXXXXXXX',
  baseURL: 'https://someurl.com',
  publicFaceScanEncryptionKey: '-----BEGIN PUBLIC KEY-----\n' +
    'XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX' +
    'XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX' +
    'XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX' +
    'XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX' +
    '-----END PUBLIC KEY-----',
  productionKeyText: {
    domains: 'XXXXXXXXXXXXXXXXXX',
    expiryDate: 'XXXX-XX-XX',
    key: 'XXXXXXXXXXXXXXXXXX'
  }
};

oncomplete(respose: ResponseSuccess ) {
  console.log(result); // all result from facetec
  alert(result.auditTrail[0]); // face image
}

onerror(error: ResponseError) {
   console.error(error);
    // if (error.code === ErrorCode.USER_CANCELLED) // do something
}
```

# Inputs


| Name           | Type             | Required   | Default             |   Description                                                                                              |
| -----------    | ---------- | ------------------- | ---------------- | --------------------------------------------------------------------------------------------------------  |
| credentials    |  Credentials       | true     |   null              |  Credentials required for facetec to work                                                                  |
| useMiddleware  |  boolean           | false    |   false             |  Flag to activate the parameters needed to use the FAD middleware                                          |
| configuration  | IFacetecConfiguration |false  |  FAD_CUSTOMIZATION, MODULE_CUSTOMIZATION, CONFIGURATION_DEFAULT      |   Customizable properties like colors and legends         |



# Outputs


| Name        | **Return**           | Description                                |
| ----------- | ---------------- | ------------------------------------------ |
| oncomplete  | ResponseSuccess  | Fires when the liveness ends successfully  |
| onerror     | ResponseError     | Is called when an error happens            |

