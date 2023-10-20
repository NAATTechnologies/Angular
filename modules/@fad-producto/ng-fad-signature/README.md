# Getting started

## Installation
``` bash
npm install @fad-producto/ng-fad-signature
```

## Update
``` bash
npm install @fad-producto/ng-fad-signature@latest
```

## Assets
Add into the assets array (*angular.json*) the next lines:
``` json
{
  "glob": "**/*",
  "input": "node_modules/@fad-producto/ng-fad-signature/assets",
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
          "input": "node_modules/@fad-producto/ng-fad-signature/assets",
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
import { ISignatureConfiguration, ResponseError, ResponseSuccess, ErrorCode, CONFIGURATION_DEFAULT, NgFadSignatureModule } from '@fad-producto/ng-fad-signature';
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
<ng-fad-signature
  [configuration]="configuration"
  (onerror)="onerror($event)"
  (acceptCamera)="acceptCamera()"
  (onclose)="onclose()"
  (oncomplete)="oncomplete($event)">
</ng-fad-signature>
```

## Typescript 

Listen to the events:

``` ts
  const configuration: ISignatureConfiguration = {
    faceDetection: {
      faceRequired: true
    },
    selfie: {
      captureSelfie: false,
      imageType: 'image/png',
      imageQuality: 1
    },
    timer: {
      recording: { min: 5 , max: 10 },
      faceUndected: 3
    },
  };

  oncomplete(response: ResponseSuccess) {
    console.log(response);
  }

  onerror(error: ResponseError) {
    console.log(error);
    // if (error.code === ErrorCode.BROWSER_NOT_SUPPORTED) // do something
  }

  onclose() {
    console.log('onclose');
  }

  acceptCamera() {
    console.log('camera accepted');
  }
```


# Inputs

| Name           | Type           |  Required  | Default               | Description                          |
| -------------- | -------------- | ---------- | --------------------- | ------------------------------------ |
| configuration  | ISignatureConfiguration  |  false     |  MEDIA_CONFIGURATION_MOBILE, CONFIGURATION_DEFAULT      |   Customizable properties like colors, legends and video/recorder configuration      |


# Outputs

| Name         | Return          | Description                                        |
| ------------ | --------------- | -------------------------------------------------- |
| oncomplete   | ResponseSuccess | Fires when the process completes successfully      |
| acceptCamera | void            | Fires when the user accepts the camera permissions |
| onclose | void            | Fires when the user close the module |
| onerror      | ResponseError   | Is called when an error happens                    |
