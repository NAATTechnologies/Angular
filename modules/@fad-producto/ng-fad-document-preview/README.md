# Getting started

## Installation

``` bash
npm install @fad-producto/ng-fad-document-preview
```

## Assets
Add into the assets array (*angular.json*) the next lines:
``` json
{
  "glob": "**/*",
  "input": "node_modules/@fad-producto/ng-fad-pdf-reader/assets",
  "output": "./assets/"
}
``` 

## Dependencies

Add the folder provided by the technical team within the project assets (images and js)


## Import

In the file necessary *example.module.ts* import the module.

In this case  *app.module.ts*

``` ts
import { NgFadDocumentPreviewModule, IDocumentPreviewConfiguration, ResponseError, CONFIGURATION_DEFAULT, STATUS_COMPONENT } from '@fad-producto/ng-fad-document-preview';
.
.
.
... imports: [
       ...,
       BrowserAnimationsModule 
       NgFadDocumentPreviewModule
    ]...
```

# Usage

## HTML


Add the selector inside some component and configure the output events:


``` html
<ng-fad-document-preview
  [configuration]="configuration"
  [pdfSrc]="pdf"
  [status]="status"
  [showDocumentRejection]="showDocumentRejection"
  [pdfResources]="pdfResources"
  (onerror)="onerror($event)"
  (oncomplete)="oncomplete()"
  (onrejectdocument)="onrejectdocument()">
</ng-fad-document-preview>
```

## Typescript 

Listen to the events:

``` ts

configuration = null;
pdf = 'src of your pdf';
status = STATUS_COMPONENT.PENDING;
showDocumentRejection = true;
pdfResources = null;

onerror(event) {
  alert(JSON.stringify(event));
}

oncomplete() {
  // do something after accept document
}

onrejectdocument() {
  this.status = STATUS_COMPONENT.REJECTED;
  // do something after reject document
}
```



# Inputs


| Name                  | Required   | Default                 |  Type                         | Description                                            |
| ------------------    | ---------- | ------------------------| ----------------------------- | ------------------------------------------------------ |
| configuration         |   false    |   CONFIGURATION_DEFAULT | IDocumentPreviewConfiguration | configuration of legends and styles                    |
| pdf                   |   true     |   undefined             | string                        | source of your pdf                                     |
| status                |   true     |   undefined             | STATUS_COMPONENT              | status ofyour document                                 |
| showDocumentRejection |   false    |   undefined             | boolean                       | shows the button to reject a document                  |
| pdfResources          |   false    |   undefined             | PdfResource[]                 | modify the paths and files for the pdfjs library files |


# Outputs


| Name             | Return        | Description                             |
| ---------------- | ------------- | --------------------------------------- |
| oncomplete       | void          | Is called when user ends the process    |
| onerror          | ResponseError | Is called when an error happens         |
| onrejectdocument | void          | Is called when user reject the document |
