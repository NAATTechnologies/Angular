# Getting started

## Installation

```
npm install @fad-producto/ng-fad-signed-document
```

## Assets
Add into the assets array (*angular.json*) the next lines:
``` json
{
  "glob": "**/*",
  "input": "node_modules/@fad-producto/ng-fad-signed-document/assets",
  "output": "./assets/"
}
``` 

## Import

In the file necessary *example.module.ts* import the module.

In this case  *app.module.ts*

``` ts
import { NgFadSignedDocumentModule, NgFadSignedDocumentComponent, ResponseError, Process, ISignedDocumentConfiguration, CONFIGURATION_DEFAULT } from '@fad-producto/ng-fad-signed-document';
.
.
.
... imports: [
       ...,
       BrowserAnimationsModule 
       NgFadSignedDocumentModule
    ]...
```

Note: BrowserAnimationsModule is required.

# Usage

## HTML


Add the selector inside some component and configure the input parameters:

``` html
  <ng-fad-signed-document
    [configuration]="configuration"
    [email]="email"
    [emailLimit]="emailLimit"
    [showAddMail]="showAddMail"
    [template]="template"
    [showAd]="showAd"
    (onsend)="onsend($event)"
    (onerror)="onerror($event)"
    (oncomplete)="oncomplete()"
    (oneventprocess)="oneventprocess($event)"
    (onclicktemplate)="onclicktemplate()">
  </ng-fad-signed-document>
```

## Typescript 

Listen to the events and execute methods:

``` ts
  public configuration = {};
  public email = 'email@example.com';
  public emailLimit = 4;
  public showAddMail = true;
  template = null;
  showAd = false;
  @ViewChild(NgFadSignedDocumentComponent) signedDocument: NgFadSignedDocumentComponent;

  onerror(error: ResponseError) {
    alert(JSON.stringify(error));
  }

  onsend(emails: string[]) {
    // Do something
    // if process is correct
    this.signedDocument.showSuccess();
  }

  oncomplete() {
    // Do something after onsend event
  }

  oneventprocess('SUCCESS_SEND_MAIL' | 'CLOSE_MAILS' | 'OPEN_MAILS') {
    // Do something after oneventprocess event
  }

  onclicktemplate() {
    // Do something after onclicktemplate event
  }
```


# Inputs

| Name             | Type                         |  Required  | Default                                        | Description                                             |
| ---------------- | ---------------------------- | -----------| ---------------------------------------------- | ------------------------------------------------------- |
| configuration    | ISignedDocumentConfiguration |  false     |  CONFIGURATION_DEFAULT                         |  module data to be configured                           |
| email            | string                       |  true      |  undefined                                     |  signer's email displayed on screen                     |
| emailLimit       | number                       |  false     |  6                                             |  limit of emails to resend document                     |
| showAddMail      | boolean                      |  false     |  true                                          |  option to resend document                              |
| template         | boolean                      |  false     |  undefined                                     |  custom template to display at the end of the component |
| showAd           | boolean                      |  false     |  undefined or false (if template has content)  |  show notice                                            |


# Outputs

| Name              | Return          | Description                                                    |
| ----------------- | --------------- | -------------------------------------------------------------- |
| onerror           | ResponseError   | Is called when an error happens                                |
| onsend            | string[]        | Is called when the user continues the process                  |
| oncomplete        | void            | Is called when the user ends the process                       |
| oneventprocess    | Process         | Is called when the user has interaction with some elements *   |
| onclicktemplate   | void            | Is called when the user has interaction the ad                 |

## oneventprocess

SUCCESS_SEND_MAIL: is sent after the method this.signedDocument.showSuccess();
CLOSE_MAILS: is sent when the screen to enter emails is closed
OPEN_MAILS: is sent whe the user open the screen to send emails
