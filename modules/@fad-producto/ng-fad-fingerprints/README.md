# Getting started

## Installation

```
npm install @fad-producto/ng-fad-fingerprints
```

## License

Add the file provided by the technical team


## Configuration project

In angular.json file add identy assets and styles

```
.
.
"assets": [
    "src/favicon.ico",
    "src/assets",
    {
      "glob": "**/*",
      "input": "node_modules/@identy/identy-finger/dist/assets",
      "output": "./assets/"
    },
    {
      "glob": "**/*",
      "input": "node_modules/@identy/identy-common/dist/assets",
      "output": "./assets/"
    },
    {
      "glob": "**/*",
      "input": "node_modules/@fad-producto/ng-fad-fingerprints/assets",
      "output": "./assets/"
    }
],
"styles": [
    "node_modules/@identy/identy-finger/dist/identy-finger-style.css",
    "node_modules/@fad-producto/ng-fad-fingerprints/assets/style/fad-fingerprints.scss"
],
.
.
```

In tsconfig.json or tsconfig.app.json add

{
  ...
  compilerOptions: {
    ...
  "skipLibCheck": true,
    ...
  }
  ...
}

## Import

In the file necessary *example.module.ts* import the module.

In this case  *app.module.ts*

``` ts
import { NgFadFingerprintsModule } from '@fad-producto/ng-fad-fingerprints';
.
.
.
... imports: [
       ...,
       BrowserAnimationsModule 
       NgFadFingerprintsModule
    ]...
```

Note: BrowserAnimationsModule is required.

# Usage

## HTML

Add the selector inside some component

``` html
<ng-fad-fingerprints 
    [modelURL]="modelURL"
    [detectionModes]="detectionModes"
    [captureTimeout]="captureTimeout"
    [allowClose]="allowClose"
    (onerror)="onerror($event)" 
    (oncomplete)="oncomplete($event)"
    (onclose)="onclose()">
</ng-fad-fingerprints>
```

## Typescript

```ts
import { NgFadFingerprintsComponent, CONFIGURATION_DEFAULT, FingerDetectionMode, IFingerprintsConfiguration, ResponseError, ResponseSuccess } from '@fad-producto/ng-fad-fingerprints';
.
.
.

modelURL: string = 'yor_model_url';
captureTimeout = 30000;
detectionModes: FingerDetectionMode[] = [L4F];
delay = 5000;
allowClose = true;

onerror(error: ResponseError) {
  // manage error
}

oncomplete(event: ResponseSuccess) {
   // capture result
}

onclose() {
  // manage close capture
}
```

# Inputs

| Name                  | Type                       |  Required  | Default               | Description                                                |
| --------------------- | -------------------------- | ---------- |---------------------- | ---------------------------------------------------------- |
| configuration         | IFingerprintsConfiguration |  false     | CONFIGURATION_DEFAULT | Configuration module                                       |
| modelURL              | string                     |  true      | undefined             | Server url                                                 |
| detectionModes        | FingerDetectionMode[]      |  true      | undefined             | Hand (right or left) and fingers (4F or thumb) to capture  |
| captureTimeout        | number                     |  false     | 30000                 | Set capture timeout                                        |
| delay                 | number                     |  false     | 5000                  | Set init delay                                             |
| allowClose            | boolean                    |  false     | false                 | Button that allows you to close the capture                |


| FingerDetectionMode Type |
| ------------------------ |
| L4F                      |
| R4F                      |
| RIGHT_INDEX              |
| RIGHT_MIDDLE             |
| RIGHT_RING               |
| RIGHT_LITTLE             |
| LEFT_INDEX               |
| LEFT_MIDDLE              |
| LEFT_RING                |
| LEFT_LITTLE              |
| RIGHT_THUMB              |
| LEFT_THUMB               |


# Outputs

| Name           | Return          | Description                                    |
| -------------- | --------------- | ---------------------------------------------- |
| oncomplete     | ResponseSuccess | Is called when capture completes successfully  |
| onerror        | ResponseError   | Is called when an error happens                |
| onclose        | void            | Is called when user close component            |
