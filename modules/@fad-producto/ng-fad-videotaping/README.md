# Getting started

## Installation
``` bash
npm install @fad-producto/ng-fad-videotaping
```

## Update
``` bash
npm install @fad-producto/ng-fad-videotaping@latest
```

## Assets
Add into the assets array (*angular.json*) the next lines:
``` json
{
  "glob": "**/*",
  "input": "node_modules/@fad-producto/ng-fad-videotaping/assets",
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
          "input": "node_modules/@fad-producto/ng-fad-videotaping/assets",
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
import { NgFadVideotapingModule } from '@fad-producto/ng-fad-videotaping';
.
.
.
... imports: [
       ...,
       BrowserAnimationsModule 
       NgFadVideotapingModule
    ]...
```

Note: BrowserAnimationsModule is required.

# Usage

## HTML


Add the selector inside some component and configure the input parameters:


``` html
<ng-fad-videotaping
  [legend]="legend"
  [identifications]="identifications"
  [configuration]="configuration"
  (onerror)="onerror($event)"
  (onclose)="onclose()"
  (oncomplete)="oncomplete($event)">
</ng-fad-videotaping>
```

## Typescript 

Listen to the events:

``` ts
import { IVideotapingConfiguration, CONFIGURATION_DEFAULT, ErrorCode, Identification, IDS_ALLOWED, ResponseError, ResponseSuccess } from '@fad-producto/ng-fad-videotaping';
  public legend = 'Lorem Ipsum es simplemente el texto de relleno de las imprentas y archivos de texto. Lorem Ipsum ha sido el texto  de relleno estándar de las industrias desde el año 1500';

  public identifications: Identification[] = [{ name: IDS_ALLOWED.ID_MEX_FRONT, title: 'Front' }, { name: IDS_ALLOWED.ID_MEX_BACK, title: 'Back' }];

  // optional
  public configuration: IVideotapingConfiguration = {
    idDetection: {
      captureId: true,
      probability: 0.85
    },
    recorder: {
      recordEverything: false
    },
    selfie: {
      captureSelfie: true,
      imageType: 'image/png',
      imageQuality: 1
    },
    selfieId: {
      captureSelfieId: false,
      imageType: 'image/png',
      imageQuality: 1,
      captureTimeout: 100
    },
  };

  oncomplete(response: ResponseSuccess) {
    console.log(response);
  }

  onerror(error: ResponseError) {
    console.log(error);
    // if (error.code === ErrorCode.BROWSER_NOT_SUPPORTED) // do something
  }
  
  acceptCamera() {
    console.log('camera accepted');
  }

  onclose(){
    console.log('module closed');
  }

```


# Inputs

| Name              | Type             |  Required  | Default                                             | Description                                        |
| ----------------- | ---------------- | ---------- | --------------------------------------------------- | -------------------------------------------------- |
| legend            | string           |  true      |  null                                               |  Legend to repeat in the recording                 |
| identifications   | Identification[] |  false     | [{name: IDS_ALLOWED.ID_MEX_FRONT, title: 'Anverso'} |  Identifications to detect (only from IDS_ALLOWED) |
| configuration     | IVideotapingConfiguration    |  false     | MEDIA_CONFIGURATION_MOBILE, CONFIGURATION_DEFAULT                               |  Module data to be configured                      |



# Outputs

| Name         | Return          | Description                                        |
| ------------ | --------------- | -------------------------------------------------- |
| oncomplete   | ResponseSuccess | Fires when the process completes successfully      |
| acceptCamera | void            | Fires when the user accepts the camera permissions |
| onerror      | ResponseError   | Is called when an error happens                    |
| onclose      | void   | Fires when the user intentionally closes the module     |



