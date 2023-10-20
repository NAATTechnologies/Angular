# Getting started

## Installation

```
npm install @fad-producto/ng-fad-security-code
```

## Assets
Add into the assets array (*angular.json*) the next lines:
``` json
{
  "glob": "**/*",
  "input": "node_modules/@fad-producto/ng-fad-security-code/assets",
  "output": "./assets/"
}
```

## Import

In the file necessary *example.module.ts* import the module.

In this case  *app.module.ts*

``` ts
import { NgFadSecurityCodeModule, ResponseError, CONFIGURATION_DEFAULT, SecurityType } from '@fad-producto/ng-fad-security-code';
.
.
.
... imports: [
       ...,
       BrowserAnimationsModule 
       NgFadSecurityCodeModule
    ]...
```

Note: BrowserAnimationsModule is required.

# Usage

## HTML


Add the selector inside some component and configure the input parameters:


``` html
  <ng-fad-security-code
    #securityCodeModule
    [securityType]="securityType"
    [currentPhone]="currentPhone"
    [securityLength]="securityLength"
    (oncomplete)="oncomplete($event)"
    (onerror)="onerror($event)">
  </ng-fad-security-code>
```

## Typescript 

Listen to the events and execute methods:

``` ts
  import { NgFadSecurityCodeComponent } from 'ng-fad-security-code/public-api';
  .
  .
  .

  @ViewChild('securityCodeModule') securityCodeModule: NgFadSecurityCodeComponent;
  public securityType = 'SMS' | 'PHONE_NUMBER' | 'SECRET_WORD';
  public currentPhone = '5555555555';
  public securityLength = 4;

  oncomplete(code: string) {
   // captured code
  }

  onerror($event: ResponseError) {
    // some error
    alert(JSON.stringify(error));
  }

  setError() {
    // set error to true when the validation of the security code is wrong
    this.securityCodeModule.setError(true);
  }
```



# Inputs

| Name           | Type                       |  Required                        | Default               | Description                                                       |
| -------------- | -------------------------- | -------------------------------- | --------------------- | ----------------------------------------------------------------- |
| securityType   | SecurityType               | true                             |  'SMS'                |  type of code to be entered                                       |
| currentPhone   | string                     | true (if securityType === 'SMS') |  null                 |  user's phone to paint on screen                                  |
| securityLength | number                     | true                             |  4                    |  security code length                                             |
| oneInputLength | number                     | false                            |  255                  |  Max length of input (only use in securityType === 'SECRET_WORD') |
| configuration  | ISecurityCodeConfiguration | false                            | CONFIGURATION_DEFAULT |  Module data to be configured                                     |



# Outputs


| Name         | Return  | Description                                         |
| ------------ | ------- | --------------------------------------------------- |
| onsendcode   | string  | Is called after the user captured the security code |
| onerror      | object  | Is called when an error happens                     |

