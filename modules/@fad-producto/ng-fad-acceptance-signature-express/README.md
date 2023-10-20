# Getting started

## Installation

```
npm install @fad-producto/ng-fad-acceptance-signature-express
```

## Update
``` bash
npm install @fad-producto/ng-fad-acceptance-signature-express@latest
```

## Assets
Add into the assets array (*angular.json*) the next lines:
``` json
{
  "glob": "**/*",
  "input": "node_modules/@fad-producto/ng-fad-pdf-reader/assets",
  "output": "./assets/"
},
{
  "glob": "**/*",
  "input": "node_modules/@fad-producto/ng-fad-acceptance-signature-express/assets",
  "output": "./assets/"
}
``` 

## Import

In the file necessary *example.module.ts* import the module.

In this case  *app.module.ts*

``` ts
import { NgFadAcceptanceSignatureExpressModule, IAcceptanceSignatureConfiguration, CONFIGURATION_DEFAULT, ResponseError, PdfPagesSignature } from '@fad-producto/ng-fad-acceptance-signature-express';
.
.
.
... imports: [
       ...,
       BrowserAnimationsModule 
       NgFadAcceptanceSignatureExpressModule
    ]...
```

Note: BrowserAnimationsModule is required.

# Usage

## HTML


Add the selector inside some component and configure the input parameters:


``` html
  <ng-fad-acceptance-signature-express
    [configuration]="configuration"
    [pdfSrc]="pdfSrc"
    [positionSignatures]="positionSignatures"
    (onerror)="onerror($event)"
    (oncomplete)="oncomplete()">
  </ng-fad-acceptance-signature-express>
```

## Typescript 

Listen to the events and execute methods:

``` ts
  public configuration = {};
  public pdfSrc = 'pdf resource';

  onerror(error: ResponseError) {
    alert(JSON.stringify(error));
  }

  oncomplete() {
    alert('next step');
  }

```


# Inputs

| Name                | Type                              |  Required  | Default                | Description                         |
| ------------------- | --------------------------------- | -----------| ---------------------- | ----------------------------------- |
| configuration       | IAcceptanceSignatureConfiguration |  false     |  CONFIGURATION_DEFAULT |  module data to be configured       |
| pdfSrc              | string                            |  true      |  undefined             |  pdf resource                       |
| positionSignatures  | PdfPagesSignature[]               |  true      |  undefined             |  signature coordinates              |


# Outputs

| Name              | Return        | Description                                                    |
| ----------------- | ------------- | -------------------------------------------------------------- |
| onerror           | ResponseError | Is called when an error happens                                |
| oncomplete        | void          | Is called when the user finishes the process                   |

