# Getting started

## Installation

```bash
npm install @fad-producto/ng-fad-signature-fea
```

## Assets

Add into the assets array (_angular.json_) the next lines:

```json
{
  "glob": "**/*",
  "input": "node_modules/@fad-producto/ng-fad-signature-fea/assets",
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
          "input": "node_modules/@fad-producto/ng-fad-signature-fea/assets",
          "output": "./assets/"
        }
      ],
    }
  }
}
```

## Import

In the file necessary _example.module.ts_ import the module.

In this case _app.module.ts_

```ts
iimport { NgFadSignatureFeaModule } from '@fad-producto/ng-fad-signature-fea';
.
.
.
... imports: [
       ...,
       BrowserAnimationsModule
       NgFadSignatureFeaModule
    ]...
```

Note: BrowserAnimationsModule is required.

# Usage

## HTML

Add the selector inside some component and configure the output events:

```html
<ng-fad-signature-fea
  [configuration]="configuration"
  [requisitionId]="requisitionId"
  [signerId]="signerId"
  [baseUrl]="baseUrl"
  (oncomplete)="oncomplete()"
  (onerror)="onerror($event)"
>
</ng-fad-signature-fea>
```

## Typescript

Listen to the events:

```ts
import { ISignatureFeaConfiguration, ResponseError } from '@fad-producto/ng-fad-signature-fea';
.
.
.

configuration: ISignatureFeaConfiguration;
baseUrl = 'URL which services will target';
requisitionId = 'ID of the requisition created'
signerId = 'ID of the signer';

onerror(event: ResponseError) {
  alert(JSON.stringify(event));
}

oncomplete() {
  // do somethig after sign the selected requisitions
}
```

# Inputs

| Name          | Required | Default               | Type                       | Description                                   |
| ------------- | -------- | --------------------- | -------------------------- | --------------------------------------------- |
| configuration | false    | CONFIGURATION_DEFAULT | ISignatureFeaConfiguration | configuration of legends, styles and behavior |
| baseUrl       | true     | undefined             | string                     | URL which services will target                |
| requisitionId | true     | undefined             | string                     | ID of the requisition created                 |
| signerId      | true     | undefined             | string                     | ID of the signer                              |

# Outputs

| Name       | Return        | Description                            |
| ---------- | ------------- | -------------------------------------- |
| onerror    | ResponseError | Is called when an error happens        |
| oncomplete | void          | Is called when user finish the process |
