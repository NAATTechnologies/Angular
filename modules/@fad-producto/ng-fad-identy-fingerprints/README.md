# Getting started

## Installation

``` bash
npm install @fad-producto/ng-fad-identy-fingerprints
```

## Server
Request to the technical team:
1.- Base64 of the license
2.- Server url
3.- Add to the server the domains in which the application will be used (including development ip's)

## Configuration project

In angular.json file add identy assets and styles

``` json
.
.
"assets": [
    "src/favicon.ico",
    "src/assets",
    {
      "glob": "**/*",
      "input": "node_modules/@fad-producto/ng-fad-identy-fingerprints/assets",
      "output": "./assets/"
    }
],
"styles": [
  "node_modules/@fad-producto/ng-fad-identy-fingerprints/assets/third-party/identy-fingerprints/style/identy-finger-style.css"
],
.
.
```

## Import

In the file necessary *example.module.ts* import the module.

In this case  *app.module.ts*

``` ts
import { NgFadIdentyFingerprintsModule } from '@fad-producto/ng-fad-identy-fingerprints';
.
.
.
... imports: [
       ...,
       NgFadIdentyFingerprintsModule
    ]...
```


# Usage

## HTML

Add the selector inside some component

``` html
<ng-fad-identy-fingerprints
  [configuration]="configuration"
  [credentials]="credentials"
  [detectionModes]="detectionModes"
  [captureTimeout]="captureTimeout"
  (oncomplete)="oncomplete($event)"
  (onnoflashdetected)="onnoflashdetected($event)"
  (onerror)="onerror($event)"
  (onclose)="onclose()">
</ng-fad-identy-fingerprints>
```

## Typescript

```ts
import { Credentials, FINGERS_DETECTION_MODE, IIdentyFingerprintsConfiguration, ResponseError, ResponseSuccess } from '@fad-producto/ng-fad-identy-fingerprints';
.
.
.

configuration: IIdentyFingerprintsConfiguration;
credentials: Credentials = {
    licence: 'base64 license',
    modelUrl: 'url-server'
};
captureTimeout = 60000;
detectionModes: FINGERS_DETECTION_MODE[] = [FINGERS_DETECTION_MODE.L4F];

onerror(error: ResponseError) {
  // manage error
}

oncomplete(event: ResponseSuccess) {
   // capture result
}

onclose() {
  // manage close capture
}

onnoflashdetected(data: string) {
  // manage when dispositive doesn't support camera flash
}
```

# Inputs

| Name                  | Type                             |  Required  | Default               | Description                                                |
| --------------------- | -------------------------------- | ---------- |---------------------- | ---------------------------------------------------------- |
| configuration         | IIdentyFingerprintsConfiguration |  false     | CONFIGURATION_DEFAULT | Configuration module                                       |
| credentials           | Credentials                      |  true      | undefined             | License and server url                                     |
| detectionModes        | FINGERS_DETECTION_MODE[]         |  true      | undefined             | Hand (right or left) and fingers (4F or thumb) to capture  |
| captureTimeout        | number                           |  false     | 60000                 | Set capture timeout                                        |

## IFingerprintsConfiguration

The following properties are for a more specific configuration of the module

| Name          | Type                       |  Required  | Default                   | Description                                                |
| ------------- | -------------------------- | ---------- |-------------------------- | ---------------------------------------------------------- |
| allowClose    | boolean                    |  false     | undefined                 | Button that allows close the process before finish         |
| livenesCheck  | boolean                    |  false     | undefined                 | Run liveness check on the captured images                  |


# Outputs

| Name              | Return          | Description                                             |
| ----------------- | --------------- | ------------------------------------------------------- |
| oncomplete        | ResponseSuccess | Is called when capture completes successfully           |
| onerror           | ResponseError   | Is called when an error happens                         |
| onclose           | void            | Is called when user close component                     |
| onnoflashdetected | string          | Is called when dispositive doesn't support camera flash |
