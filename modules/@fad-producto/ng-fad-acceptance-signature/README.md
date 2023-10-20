# Getting started

## Installation

``` bash
npm install @fad-producto/ng-fad-acceptance-signature
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
  "input": "node_modules/@fad-producto/ng-fad-acceptance-signature/assets",
  "output": "./assets/"
}
```

## Import

In the file necessary *example.module.ts* import the module.

In this case  *app.module.ts*

``` ts
import { NgFadAcceptanceSignatureModule, IAcceptanceSignatureConfiguration, ResponseError, PdfPagesSignature, CONFIGURATION_DEFAULT } from '@fad-producto/ng-fad-acceptance-signature';
.
.
.
... imports: [
       ...,
       BrowserAnimationsModule 
       NgFadAcceptanceSignatureModule
    ]...
```

Note: BrowserAnimationsModule is required.

# Usage

## HTML


Add the selector inside some component and configure the output events:


``` html
<ng-fad-acceptance-signature
    [configuration]="configuration"
    [pdfSrc]="pdf"
    [positionSignatures]="positionSignatures"
    [pdfResources]="pdfResources"
    (onerror)="onerror($event)"
    (onmoreinformation)="onmoreinformation()"
    (oncomplete)="oncomplete()">
  </ng-fad-acceptance-signature>
```

## Typescript 

Listen to the events:

``` ts

configuration = null;
pdf = 'src of your pdf';
positionSignatures: PdfPagesSignature[];
pdfResources = null;

onerror(event: ResponseError) {
  alert(JSON.stringify(event));
}

onmoreinformation() {
  // do somethig after click in some information
}

oncomplete() {
  // do somethig after accept all signatures
}
```



# Inputs


| Name                  | Required   | Default                 |  Type                             | Description                                            |
| ------------------    | ---------- | ----------------------- | --------------------------------- | ------------------------------------------------------ |
| configuration         |   false    |   CONFIGURATION_DEFAULT | IAcceptanceSignatureConfiguration | configuration of legends                               |
| pdf                   |   true     |   undefined             | string                            | source of your pdf                                     |
| pdfResources          |   false    |   undefined             | PdfResource[]                     | modify the paths and files for the pdfjs library files |
| positionSignatures    |   true     |   undefined             | PdfPagesSignature[]               | signature coordinates displayed in pdf                 |


# Outputs


| Name              | Return        | Description                                   |
| ----------------- | ------------- | --------------------------------------------- |
| onmoreinformation | void          | Is called when user click to more information |
| onerror           | ResponseError | Is called when an error happens               |
| oncomplete        | void          | Is called when user finish the process        |
