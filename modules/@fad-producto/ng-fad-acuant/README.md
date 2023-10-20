# Getting started

## Installation

``` bash
npm install @fad-producto/ng-fad-acuant
```
## Update
``` bash
npm install @fad-producto/ng-fad-acuant@latest
```
## Assets
Add into the assets array (*angular.json*) the next lines:
``` json
{
  "glob": "**/*",
  "input": "node_modules/@fad-producto/ng-fad-acuant/assets",
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
          "input": "node_modules/@fad-producto/ng-fad-acuant/assets",
          "output": "./assets/"
        }
      ],
    }
  }
}
```


## Import

In the file necessary *example.module.ts* import the module.

In this case  *app.module.ts*

``` ts
import { IAcuantConfiguration, AcuantCredentials, ResponseError, AcuantResult, ErrorCode, CONFIGURATION_DEFAULT, NgFadAcuantModule } from '@fad-producto/ng-fad-acuant';
.
.
.
... imports: [
       ...,
       BrowserAnimationsModule 
       NgFadAcuantModule
    ]...
```
Note: BrowserAnimationsModule is required.
# Usage

## HTML


Add the selector inside some component and configure the output events:


``` html
<ng-fad-acuant
  [credentials]="credentials"
  [configuration]= "configuration"
  [side]=0
  [idData]=false
  [idPhoto]=false
  [forcePhoto]= false
  [imageQuality]= 1
  [manualCapture]=false
  [documentInstance]="documentInstance"
  (onerror)="onerror($event)"
  (oncomplete)="oncomplete($event)">
</ng-fad-acuant>
```

## Typescript 

Listen to the events:

``` ts


const CREDENTIALS : AcuantCredentials  = {
  passiveUsername: 'XXXXXXXXXXXXXXXXXXXXXXXXX',
  passivePassword: 'XXXXXXXXXXXXXXXXXXXXXXXXX',
  passiveSubscriptionId: 'XXXXXXXXXXXXXXXXXXXXXXXXX',
  acasEndpoint: 'XXXXXXXXXXXXXXXXXXXXXXXXX',
  livenessEndpoint: 'XXXXXXXXXXXXXXXXXXXXXXXXX',
  assureidEndpoint: 'XXXXXXXXXXXXXXXXXXXXXXXXX'
};



public configuration: IAcuantConfiguration = {
  customization: {
    moduleCustomization: {
      legends: {
        scan: {
          none: 'ENFOCA TU ID SOBRE LA GUÍA',
          smallDocument: 'ACERCATE MÁS',
          goodDocument: null,
          capturing: 'CAPTURANDO',
          tapToCapture: 'TOCA LA PANTALLA PARA CAPTURAR'
        },
        manualCapture: {
          instruction: 'Captura el frente de tu identificación',
          buttonNext: 'Continuar'
        }
      },
    },
  },
}
  
.
.
.

oncomplete(result: AcuantResult) {
  console.log(result)
}

onerror(error: ResponseError) {
   console.error(error);
    // if (error.code === ErrorCode.REQUIRED_CREDENTIALS) // do something
}
```



# Inputs


| Name              |   Type               | Required   | Default             | Description                                                                        |
| -----------       |  -----------------   | ---------- | ------------------- | ------------------------------------------------------                             |
| credentials       |    AcuantCredentials | true       |   null              | Credentials required for acuant to work                                            |
| configuration     |    IAcuantConfiguration     | false      |   object            | configuration of legends                                                           |
| side              |    number  (0 or 1)  | false      |   0                 | Side of image to capture <ul> <li> 0 - Front </li><li> 1 - Back</li>    </ul>      |
| idData            |    boolean           | false      |   false             | add OCR and OCR validation to the final response                                   |
| idPhoto           |    boolean           | false      |   false             | Image of the face cutout, only works if idData is true                             |
| imageQuality      |    number (0.1 to 1) | false      |   1                 | Quality of the image result                                                        |
| forcePhoto        |    boolean           | false      |   false             | Returns the ID photo if the OCR is not required or if could not obtain the ID face crop                                                                                   |
| documentInstance  |    string            | false      |   null              |      Is used to relate the front and back of the ID                                                                              |
|manualCapture | boolean  | false | false | Enables the manual capture by default |


# Outputs


| Name        | Return  | Description                                |
| ----------- | ------- | ------------------------------------------ |
| oncomplete  | AcuantResult  | Fires when the liveness ends successfully  |
| onerror     | ResponseError  | Is called when an error happens            |

