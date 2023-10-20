# Getting started

## Installation

``` bash
npm install @fad-producto/ng-fad-acceptance-signature-ZOOM
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
  "input": "node_modules/@fad-producto/ng-fad-acceptance-signature-zoom/assets",
  "output": "./assets/"
}
```

## Import

In the file necessary *example.module.ts* import the module.

In this case  *app.module.ts*

``` ts
iimport { NgFadAcceptanceSignatureZoomModule } from '@fad-producto/ng-fad-acceptance-signature-zoom';
.
.
.
... imports: [
       ...,
       BrowserAnimationsModule 
       NgFadAcceptanceSignatureZoomModule
    ]...
```

Note: BrowserAnimationsModule is required.

# Usage

## HTML


Add the selector inside some component and configure the output events:


``` html
<ng-fad-acceptance-signature-zoom
  [configuration]="configuration"
  [pdfSrc]="pdfSrc"
  [positionSignatures]="positionSignatures"
  [signer]="signer"
  (oncomplete)="oncomplete()"
  (onerror)="onerror($event)">
</ng-fad-acceptance-signature-zoom>
```

## Typescript 

Listen to the events:

``` ts
import { IAcceptanceSignatureZoomConfiguration, PdfPagesSignature, ResponseError } from '@fad-producto/ng-fad-acceptance-signature-zoom';
.
.
.

configuration: IAcceptanceSignatureZoomConfiguration;
pdfSrc = 'src of your pdf';
positionSignatures: PdfPagesSignature[];
signer = 'Name LastName';

onerror(event: ResponseError) {
  alert(JSON.stringify(event));
}

oncomplete() {
  // do somethig after accept all signatures
}
```



# Inputs


| Name                  | Required   | Default                 |  Type                                 | Description                                            |
| ------------------    | ---------- | ----------------------- | ------------------------------------- | ------------------------------------------------------ |
| configuration         |   false    |   CONFIGURATION_DEFAULT | IAcceptanceSignatureZoomConfiguration | configuration of legends, styles and behavior          |
| pdfSrc                |   true     |   undefined             | string                                | source of your pdf                                     |
| positionSignatures    |   true     |   undefined             | PdfPagesSignature[]                   | signature coordinates displayed in pdf                 |
| signer                |   true     |   undefined             | string                                | name of current signer                                 |




## IAcceptanceSignatureZoomConfiguration

The following properties are for a more specific configuration of the module

| Name                  | Type                       |  Required  | Default                   | Description                                                            |
| --------------------- | -------------------------- | ---------- |-------------------------- | ---------------------------------------------------------------------- |
| pdfResources          | PdfResource[]              |  false     | undefined                 | modify the paths and files for the pdfjs library files                 |
| aspectRatio           | number                     |  false     | 1                         | aspect ratio that will determine the separation in any of the axes     |
| offsetX               | number                     |  false     | 20                        | spacing on the x-axis                                                  |
| offsetY               | number                     |  false     | 20                        | spacing on the x-axis                                                  |
| xPosition             | number                     |  false     | 2                         | Center of the signature space on the x-axis                            |
| yPosition             | number                     |  false     | 2.5                       | Center of the signature space on the y-axis                            |
| viewAllPdf            | boolean                    |  false     | false                     | Allows the user to always see the entire pdf                           |
| canClickSpace         | boolean                    |  false     | false                     | Allows the user to click on the signature without zooming              |
| viewAlwaysInstruction | boolean                    |  false     | true                      | The user will always see the reference to click on the signature space |




# Outputs


| Name              | Return        | Description                                   |
| ----------------- | ------------- | --------------------------------------------- |
| onerror           | ResponseError | Is called when an error happens               |
| oncomplete        | void          | Is called when user finish the process        |

