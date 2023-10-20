# Getting started

## Installation

``` bash
npm install @fad-producto/ng-fad-regula-id
```

## Update
``` bash
npm install @fad-producto/ng-fad-regula-id@latest
```

## Angular >= 13

``` bash
npm install npm i --save-dev @types/pako
```

Change noImplicitOverride and noImplicitReturns to false on tsonfig.json file

``` ts
"compilerOptions" : {
  .
  .
  .
  "noImplicitOverride": false,
  "noImplicitReturns": false,
  .
  .
  .
}
```

## License
Add the license file provided by the technical team

## Configuration project

In angular.json file add assets

``` ts
.
.
"assets": [
    .
    .
    {
      "glob": "**/*",
      "input": "node_modules/@fad-producto/ng-fad-regula-id/assets",
      "output": "./assets/"
    }
  ]
  .
  .
```

## Import

In the file necessary *example.module.ts* import the module.

In this case  *app.module.ts*

``` ts
import { NgFadRegulaIdModule } from '@fad-producto/ng-fad-regula-id';
.
.
.
... imports: [
       ...,
       BrowserAnimationsModule 
       NgFadRegulaIdModule
    ]...
```

# Usage

## HTML


Add the selector inside some component and configure the output events:


``` html
<ng-fad-regula-id
  [configuration]="configuration"
  [credentials]="credentials"
  [idData]="idData"
  [idPhoto]="idPhoto"
  [captureType]="captureType"
  (oncomplete)="oncomplete($event)"
  (onerror)="onerror($event)"
  (onclose)="onclose()">
</ng-fad-regula-id>
```

## Typescript 

Listen to the events:

``` ts
import { CAPTURE_TYPE, Credentials, IRegulaIdConfiguration, ResponseError, ResponseSuccess } from '@fad-producto/ng-fad-regula-id';
.
.
.
public configuration: IRegulaIdConfiguration;
public credentials: Credentials = {
    license: 'license_base64',
};
public idData = true;
public idPhoto = false;
captureType = CAPTURE_TYPE.CAMERA_SNAPSHOT;

oncomplete(result: ResponseSuccess) {
  console.log(result)
}

onerror(error: ResponseError) {
   alert(JSON.stringify(error));
}

onclose() {
  // remove module component from your component
}

```

# Inputs


| Name           | Required                        | Default                                 |  Type                  | Description                                            |
| -----------    | ------------------------------- | --------------------------------------- | ---------------------- | ------------------------------------------------------ |
| configuration  |   false                         |  CONFIGURATION_DEFAULT                  | IRegulaIdConfiguration | Configuration module                                   |
| credentials    |   true                          |  undefined                              | Credentials            | License base64 and path to request api                  |
| idData         |   false                         |  false                                  | boolean                | Add OCR to the final response                          |
| idPhoto        |   false                         |  false                                  | boolean                | Image of the face cutout, only works if idData is true |
| captureType    |   true (only in mobile devices) |  undefined                              | CAPTURE_TYPE           | Capture type, DOCUMENT_READER for automatic capture and CAMERA_SNAPSHOT for manual capture. This captureType only works on mobile devices |


## IRegulaIdConfiguration

The following properties are for a more specific configuration of the module

| Name                              | Type                       |  Required  | Default                   | Description                                                                       |
| --------------------------------- | -------------------------- | ---------- |-------------------------- | --------------------------------------------------------------------------------- |
| idValidations.cardMatch           | boolean                    |  false     | true                      | Allows you to validate if the captured credentials are being correctly classified |
| For CAPTURE_TYPE.CAMERA_SNAPSHOT                                                                                                                                                            |
| cameraSnapshot.changeCameraButton | boolean                    |  false     | true                      | Allows you to switch cameras to improve focus                                     |
| cameraSnapshot.closeButton        | boolean                    |  false     | false                     | Add a button that closes the module                                               |
| For CAPTURE_TYPE.DOCUMENT_READER                                                                                                                                                            |
| documentReader.captureButton      | boolean                    |  false     | false                     | Add a button to capture manually. Only processes one side of the ID               |
| documentReader.closeButton        | boolean                    |  false     | false                     | Add a button that closes the module                                               |
| documentReader.changeCameraButton | boolean                    |  false     | false                     | Allows you to switch cameras to improve focus                                     |
| documentReader.timeout            | number                     |  false     | 30000                     | Maximum capture time per id side in milliseconds                                  |



# Outputs

| Name        | Return          | Description                                  |
| ----------- | --------------- | -------------------------------------------- |
| oncomplete  | ResponseSuccess | Fires when the id capture ends successfully  |
| onerror     | ResponseError   | Is called when an error happens              |
| onclose     | void            | Fires when user closes the camera            |
