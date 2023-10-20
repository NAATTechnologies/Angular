# Getting started

## Installation

``` bash
npm install @fad-producto/ng-fad-signature-express
```

## Update

``` bash
npm install @fad-producto/ng-fad-signature-express@latest
```

## Assets
Add into the assets array (*angular.json*) the next lines:
``` json
{
  "glob": "**/*",
  "input": "node_modules/@fad-producto/ng-fad-signature-express/assets",
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
          "input": "node_modules/@fad-producto/ng-fad-signature-express/assets",
          "output": "./assets/"
        }
      ],
    }
  }
}
```


## Import

In the file necessary *example.module.ts* import the module.

In this case  *app.module.ts*

``` ts
import { NgFadSignatureExpressModule } from '@fad-producto/ng-fad-signature-express';
.
.
.
... imports: [
       ...,
       BrowserAnimationsModule 
       NgFadSignatureModule
    ]...
```

Note: BrowserAnimationsModule is required.

# Usage

## HTML


Add the selector inside some component and configure the output events:


``` html
<ng-fad-signature-express
  [configuration]="configuration"
  (onerror)="onerror($event)"
  (oncomplete)="oncomplete($event)"
  (acceptCamera)="acceptCamera()">
</ng-fad-signature-express>
```

## Typescript 

Listen to the events:

``` ts

import { ISignatureExpressConfiguration, ResponseSuccess, ResponseError, ErrorCode, CONFIGURATION_DEFAULT } from '@fad-producto/ng-fad-signature-express';

.
.
.

configuration: ISignatureExpressConfiguration = {
  selfie: {
    captureSelfie: true,
    imageType: 'image/png',
    imageQuality: 1
  }
};

.
.
.
oncomplete(response: ResponseSuccess) {
  console.log(response);
}

onerror(error: ResponseError) {
  console.log(error);
  // if (error.code === ErrorCode.BROWSER_NOT_SUPPORTED) // do something
}

acceptCamera() {
  console.log('cammera accepted');
}
```

# Inputs

| Name             | Type           |  Required  | Default               | Description                   |
| ---------------- | ------------   | ---------- | --------------------- | ----------------------------- |
| configuration    | ISignatureExpressConfiguration  |  false     | MEDIA_CONFIGURATION_MOBILE, CONFIGURATION_DEFAULT | Module data to be configured  |


# Outputs

| Name         | Return          | Description                                        |
| ------------ | --------------- | -------------------------------------------------- |
| oncomplete   | ResponseSuccess | Fires when the process completes successfully      |
| acceptCamera | void            | Fires when the user accepts the camera permissions |
| onerror      | ResponseError   | Is called when an error happens                    |

