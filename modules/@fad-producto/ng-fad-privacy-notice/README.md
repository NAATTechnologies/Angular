# Getting started

## Installation

```
npm install @fad-portal/ng-fad-privacy-notice
```

## Assets
Add into the assets array (*angular.json*) the next lines:
``` json
{
  "glob": "**/*",
  "input": "node_modules/@fad-producto/ng-fad-privacy-notice/assets",
  "output": "./assets/"
}
```


## Import

In the file necessary *example.module.ts* import the module.

In this case  *app.module.ts*

``` ts
import { NgFadPrivacyNoticeModule, IPrivacyNoticeConfiguration, CONFIGURATION_DEFAULT, ResponseError } from '@fad-portal/ng-fad-privacy-notice';
.
.
.
... imports: [
       ...,
       BrowserAnimationsModule 
       NgFadPrivacyNoticeModule
    ]...
```

Note: BrowserAnimationsModule is required.

# Usage 1

## HTML


Add the selector inside some component and configure the input parameters:


``` html
  <ng-fad-privacy-notice-v1
    [configuration]="configuration"
    [privacyNoticeHtml]="privacyNoticeHtml"
    [delay]="delay"
    (oncomplete)="oncomplete()"
    (onerror)="onerror($event)">
  </ng-fad-privacy-notice-v1>
```

## Typescript 

Listen to the events and execute methods:

``` ts
  privacyNoticeHtml: string;
  configuration: IPrivacyNoticeConfiguration;
  delay: number;

  onerror(error: ResponseError) {
    alert(JSON.stringify(error));
  }

  oncomplete() {
    alert('next step');
  }
```


# Inputs

| Name              | Type                        |  Required  | Default                | Description                                |
| ----------------- | --------------------------- | ---------- | ---------------------- | ------------------------------------------ |
| configuration     | IPrivacyNoticeConfiguration |  false     |  CONFIGURATION_DEFAULT |  module data to be configured              |
| privacyNoticeHtml | string                      |  false     |  undefined             |  privacy notice template                   |
| legend            | string                      |  false     |  undefined             |  legend confirmation of the privacy notice |
| delay             | number                      |  false     |  2000                  |  loader duration                           |


# Outputs

| Name              | Return        | Description                                                    |
| ----------------- | ------------- | -------------------------------------------------------------- |
| onerror           | ResponseError | Is called when an error happens                                |
| oncomplete        | void          | Is called when the user finishes the process                   |



# Usage 2

## HTML


Add the selector inside some component and configure the input parameters:


``` html
  <ng-fad-privacy-notice-v2
    [configuration]="configuration"
    [privacyNoticeHtml]="privacyNoticeHtml"
    [delay]="delay"
    (oncomplete)="oncomplete()"
    (onerror)="onerror($event)">
  </ng-fad-privacy-notice-v2>
```

## Typescript 

Listen to the events and execute methods:

``` ts
  privacyNoticeHtml: string;
  configuration: IPrivacyNoticeConfiguration;
  delay: number;

  onerror(error: ResponseError) {
    alert(JSON.stringify(error));
  }

  onclose() {
    alert('next step');
  }
```


# Inputs

| Name              | Type                        |  Required  | Default                | Description                                |
| ----------------- | --------------------------- | ---------- | ---------------------- | ------------------------------------------ |
| configuration     | IPrivacyNoticeConfiguration |  false     |  CONFIGURATION_DEFAULT |  module data to be configured              |
| privacyNoticeHtml | string                      |  false     |  undefined             |  privacy notice template                   |
| delay             | number                      |  false     |  2000                  |  loader duration                           |


# Outputs

| Name              | Return        | Description                                                    |
| ----------------- | ------------- | -------------------------------------------------------------- |
| onerror           | ResponseError | Is called when an error happens                                |
| oncomplete        | void          | Is called when the user finishes the process                   |
