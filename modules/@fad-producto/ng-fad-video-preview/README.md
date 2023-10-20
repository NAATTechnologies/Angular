# Getting started

## Installation

``` bash
npm install @fad-producto/ng-fad-video-preview
```

## Update
``` bash
npm install @fad-producto/ng-fad-video-preview@latest
```


## Assets
Add into the assets array (*angular.json*) the next lines:
``` json
{
  "glob": "**/*",
  "input": "node_modules/@fad-producto/ng-fad-video-preview/assets",
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
          "input": "node_modules/@fad-producto/ng-fad-video-preview/assets",
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
import { NgFadVideoPreviewModule } from '@fad-producto/ng-fad-video-preview';

.
.
.
... imports: [
       ...,
       BrowserAnimationsModule 
       NgFadVideoPreviewModule
    ]...
```

Note: BrowserAnimationsModule is required.

# Usage

## HTML


Add the selector inside some component and configure the output events:


``` html
<ng-fad-video-preview
[blobFace]="blobFace"
[blobSignature]="blobSignature"
[configuration]="configuration"
(oncancel)="oncancel()"
(onconfirm)="onconfirm()"
(onplay)="onplay()"
(onerror)="onerror($event)">
</ng-fad-video-preview>

```

## Typescript 

Listen to the events:

``` ts
import { IVideoPreviewConfiguration, ResponseError, ErrorCode, CONFIGURATION_DEFAULT } from '@fad-producto/ng-fad-video-preview';
.
.
.
onplay() {
  console.log('Playing')
}

oncancel() {
  alert('retry');
}

onerror(error: ResponseError) {
  console.log(error);
  // if (error.code === ErrorCode.NO_VIDEO) // do something
}

onconfirm() {
  alert('confirm');
}

```

# Inputs

| Name             | Type           |  Required  | Default               | Description                   |
| ---------------- | ------------   | ---------- | --------------------- | ----------------------------- |
| blobFace    | Blob  |  true     | null | Face video as a  Blob  |
| blobSignature    | Blob  |  false     | null | Signature video as a  Blob |
|configuration | IVideoPreviewConfiguration  | false  | FAD_CUSTOMIZATION, MODULE_CUSTOMIZATION, CONFIGURATION_DEFAULT | Module data to be configured |

# Outputs

| Name         | Return          | Description                                        |
| ------------ | --------------- | -------------------------------------------------- |
| oncancel   | void | Fires when user decides to retry the video(s)    |
| onconfirm | void            | Fires when the user confirms the video(s) |
| onplay | void | Fires when the user starts playing the video(s) |
| onerror      | ResponseError   | Is called when an error happens                    |

