# FAD-ACUANT Migration Details (CHANGELOG)


## [10.0.3](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/v10.0.2...v10.0.3) (2023-07-27)


### Bug Fixes

* using minified js files for acuant v11.9.0 ([f1beb5d](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/f1beb5d7d41d6908ed58bed54a3e26b18c7fe038))

## [10.0.2](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/v10.0.1...v10.0.2) (2023-07-27)


### Bug Fixes

* focus for iframe version with Acuant 11.9.0
## [10.0.1](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/v10.0.0...v10.0.1) (2023-07-25)

### Changes
* Priority for the id verifications
## [10.0.0](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/v9.0.0...v10.0.0) (2023-07-24)


### ⚠ BREAKING CHANGES

* cardtype property inside AcuantResultImage changes to cardType

> The cardtype attribute of `AcuantResultImage` interface changes to cardType
> ``` ts
> AcuantResultImage {
>  image: {
>    data: string;
>    width: number;
>    height: number;
>  };
>  glare: string;
>  dpi: string;
>  cardType: AcuantCardType;
>  sharpness: number;
>  moire: string;
>  moireraw: string;
> };
> ``` 
> 
> For more details check the `AcuantResultImage` interface and the `AcuantCardType` enum

### Features

* Military and Consular classification types ([dfb663a](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/dfb663ae8096238f3b7b4edc7f8907dbecd12588))


### Bug Fixes

* cardtype changes to cardType ([8b149b9](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/8b149b95e1bd87083301bb4ff30d756a0af7e1a3))

## [9.0.0](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/v8.0.0...v9.0.0) (2023-07-21)


### ⚠ BREAKING CHANGES

* check that the zones of the IDs are equals now is available through the checkZone flag
* Thresholds must be configured through the new configuration object metricsThresholds
> The metrics thresholds must be configured trough the new metricsThresholds property
> ``` ts
> configuration: IAcuantConfiguration = {
>    metricsThresholds: {
>    sharpness: 60,
>    glare: 90,
>    dpi: 350
>  }
> }

### Features

* checkCardType ([82b7700](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/82b7700954f5d1092f15c893b718ab1c79500886))


* metric thresholds object ([3e2113e](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/3e2113e34dd32192445b87d77843119f934b393e))
* sameZone changes to checkZone ([0cb6e4f](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/0cb6e4f96acaf33d81962ff9702815f76115b0a7))

## [8.0.0](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/v7.0.0...v8.0.0) (2023-07-18)


### ⚠ BREAKING CHANGES

* glare and dpi properties changes from string to number

> The glare and dpi attributes of `AcuantResultImage` interface changes from string to number
> ``` ts
> AcuantResultImage {
>  image: {
>    data: string;
>    width: number;
>    height: number;
>  };
>  glare: number;
>  dpi: number;
>  cardtype: AcuantCardType;
>  sharpness: number;
>  moire: string;
>  moireraw: string;
> };
> ``` 
> 
> For more details check the `AcuantResultImage` interface and the `AcuantCardType` enum
### Features

* glare threashold and dpi threashold ([63dd0b3](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/63dd0b3742b436f53587241c7b4d5f5670086bd1))


* glare and dpi types ([c35dd1b](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/c35dd1b8ffb230934c2c1416ac71b712a1a54b0c))

## [7.0.0](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/v6.1.0...v7.0.0) (2023-07-12)


### ⚠ BREAKING CHANGES

* the quality of the output ID's images must be configured via the configuration object instead of an @Input
  
> The imageQuality @Input is replaced by the `imageResult.quality` property
> ``` ts
> configuration: IAcuantConfiguration = {
>    imageResult: {
>      quality: 1
>    },
> }
> ```

### Features

* idValidations property for check the sides and that the zones of the ID matches ([deee5ea](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/deee5ead118730ff7bea3ecdc089a6ac14a72084))


* image quality via configuration instead of [@input](https://na-at.xp-dev.com/input) ([f7f82e1](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/f7f82e1ee55b24af941ccc2571d5f2165c88d778))

## [6.1.0](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/v6.0.0...v6.1.0) (2023-07-10)


### Features

* improves the focus in iPhone and android devices; inproves the support for  low-end devices ([9e46436](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/9e46436d6d3ce33c28d188bc2f92209686e0c6fd))

## [6.0.0](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/v6.0.0-alpha.1...v6.0.0) (2023-07-07)


### Features

* imageQuality does not affect in the image upload process; instead only applies in the image response, after the image was uploaded to be processed in the server ([964574e](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/964574e10550fac4e392b81af7d8a8d696751ca0))

## [6.0.0-alpha.1](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/v6.0.0-alpha.0...v6.0.0-alpha.1) (2023-06-12)


### Bug Fixes

* logs removed ([ce12a18](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/ce12a18bc872baf978e1d064315933636bbf8fb8))

## [6.0.0-alpha.0](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/v5.1.0-alpha.0...v6.0.0-alpha.0) (2023-06-09)


### ⚠ BREAKING CHANGES

* scan, manualCapture.mobile and manualCapture.desktop has legends for front and back side.
> The customizable legeds of the module now has attributes for the front and the back side of the ID. Previous versions had no different attributes for the front and back side and the developer was the responsible of define the correct legends according
> to the process.
> ``` ts
> IAcuantLegends {
>   scan: {
>     front: {
>       none: 'ENFOCA EL FRENTE DE TU ID SOBRE LA GUÍA',
>       smallDocument: 'ACERCATE MÁS',
>       bigDocument: 'DEMASIADO CERCA',
>       goodDocument: null,
>       capturing: 'CAPTURANDO',
>       tapToCapture: 'TOCA LA PANTALLA PARA CAPTURAR',
>       title: 'Frente'
>      },
>      back: {
>         none: 'ENFOCA EL REVERSO DE TU ID SOBRE LA GUÍA',
>         smallDocument: 'ACERCATE MÁS',
>         bigDocument: 'DEMASIADO CERCA',
>         goodDocument: null,
>         capturing: 'CAPTURANDO',
>         tapToCapture: 'TOCA LA PANTALLA PARA CAPTURAR',
>         title: 'Reverso'
>       }
>    },
>    manualCapture: {
>     tooltip: 'Captura nuevamente',
>     mobile: {
>       front: {
>         instruction: 'Captura el frente de tu identificación',
>         buttonNext: 'Continuar',
>       },
>       back: {
>         instruction: 'Captura el reverso de tu identificación',
>         buttonNext: 'Continuar',
>       }
>     },
>     desktop: {
>       front: {
>         instruction: 'Sube el frente de tu identificación',
>         title: 'Frente'
>       },
>       back: {
>         title: 'Reverso',
>         instruction: 'Sube el reverso de tu identificación',
>       }
>     }
>   },
> };
> ``` 
> 
> For more details check the `IAcuantLegends` interface

* The id attribute of the AcuantResponse interface is of type AcuantResultIdImage  (contains front and back image) insteead of AcuantResultImage
> The AcuantResult now contains the image of the front and the back side of the ID. In previous versions the id attibute was of type `AcuantResultImage` and had only the image of one side of the id.
> ``` ts
> AcuantResult {
>  id: {
>    front?: AcuantResultImage;
>    back?: AcuantResultImage;
>  };
>  idData?: AcuantResultIdData;
>  idPhoto?: string;
> };
> ``` 
> 
> For more details check the `AcuantResult` and the `AcuantResultIdImage` interface

* cardtype property changes from string type to AcuantCardType enum type

> The cardtype attribute of `AcuantResultImage` interface changes from string to a new enum `AcuantCardType` enum
> ``` ts
> AcuantResultImage {
>  image: {
>    data: string;
>    width: number;
>    height: number;
>  };
>  glare: string;
>  dpi: string;
>  cardtype: AcuantCardType;
>  sharpness: number;
>  moire: string;
>  moireraw: string;
> };
> ``` 
> 
> For more details check the `AcuantResultImage` interface and the `AcuantCardType` enum
* sedDynamicConfiguration() and setCustomizationStyle() is not more available outside of the component
* initDone() is not more available outside of the component
* startCamera() is not more available outside of the component
* createInstance() is not more available outside of the component
* uploadImage() is not more available outside of the component
* getOcr() is not more available outside of the component
* getFaceImage() is not more available outside of the component
* documentInstance and side removed as ng-fad-acuant input

### Features

* AcuantBiographic in AcuantDocument ([3bad06b](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/3bad06ba485a2f0a6c22369e5c27f096077d3f16))
* AcuantCardType enum ([f7ee483](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/f7ee483df40318ae4b677d8ba38007e023df0928))
* automatic capture title ([c577d6c](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/c577d6c4b6188b9f8614651c84026c9fc0328f03))
* cardType in AcuantResult ([b4a5477](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/b4a54771fe6b2771e81c776c1ee9f6a78b9769d2))
* customizable legends by side. ([884950f](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/884950f98f16c0c6937f79cc1d9b6a8a0efabb5e))
* font and back image in the result ([f3819ab](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/f3819abb13939e9cda02173ce90ec8c3c7595d06))


### Bug Fixes

* cardtype in AcuantResultImage changes the string type to AcuantCardType ([c481011](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/c4810116e8a218e0cf011e19ece9400d733fe879))


* createInstance() private and async ([f46ba6a](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/f46ba6ae6bde042434d4f1836cb24c516170a5a8))
* getFaceImage methos is private ([b8b151d](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/b8b151d1b3d43c89ad8d1cd7733422421ec37ccc))
* getOcr() private and async ([d89e26a](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/d89e26a8f36fa70b4625a911c29916464e411179))
* initDone() private and async ([e334c7b](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/e334c7be18fe45a940609d7a7a8acc522b8c70ac))
* manages documentInstance and side internally ([14b6e83](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/14b6e83c6b095f8b2699afbfdb4415dd8e82db1f))
* sedDynamicConfiguration() and setCustomizationStyle() private ([ad5e9a7](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/ad5e9a703a67f8f6c957a0aaffa7272b3174f09a))
* startCamera() private ([c9af2a9](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/c9af2a9ed690e1915b29f820dd25a21e62970227))
* uploadImage() private and async ([4c37750](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/4c377502f8b41dbc1ce827126797aaa27201d384))

## [5.1.0-alpha.0](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/v5.0.1-alpha.1...v5.1.0-alpha.0) (2023-05-12)


### Features

* support for custom language response ([0d36a8c](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/0d36a8cabd111988c18fb0c3463d9fe1d4647645))

## [5.0.1-alpha.1](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/v5.0.1-alpha.0...v5.0.1-alpha.1) (2023-05-09)


### Bug Fixes

* fix AcuantForceRegularCapture to true for iphones with iframe ([0c82075](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/0c82075a8fe5643332e084787519ba0df34ceafe))

## [5.0.1-alpha.0](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/v5.0.0...v5.0.1-alpha.0) (2023-05-09)


### Bug Fixes

* capture mode in iframe ([f4ebfec](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/f4ebfece836b4c21a5b659ce2d7f6ffbdfc71e29))

## [5.0.0](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/v4.0.0...v5.0.0) (2023-03-21)


### ⚠ BREAKING CHANGES

* error response data is an objecto of type AcuantResultImage instead of string
> The error response now provides more information about the AcuantResponse through the data value. The new error response returns an object of AcuantResultImage instead of an base 64 image.
> ``` ts
> ResponseError {
>   error: string;
>   code: ErrorCode;
>   data: {
>     image: {
>       data: string;
>       width: number;
>       height: number;
>     };
>     glare: string;
>     dpi: string;
>     cardtype: string;
>     sharpness: number;
>     moire: string;
>     moireraw: string;
>   }
> };
> ``` 
> 
> For more details check the `ResponseError` class

### Features

* customizable images in manual capture ([1387597](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/13875973823cf3b30154681541bc6dc7ce458424))
* response-error data ([4c9d172](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/4c9d172fc2a78edfa96067177f49707c33625c3f))


### Bug Fixes

* align-items center in maunal capture ([3cdc926](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/3cdc926df39a15679236b39fcfd6804544c50ff1))

## [4.0.0](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/v3.12.0...v4.0.0) (2023-03-14)


### ⚠ BREAKING CHANGES

* tooltip out of mobile/desktop object
* Configurable legends
  

> Customizable legends structure has been modified for manual capture.
>
>Previus releases had a general legends for the manual capture. The newer structure divides the legends for the desktop view and the mobile view.
> ``` ts
> manualCapture: {
>   tooltip?: string;
>   mobile?: {
>     instruction?: string;
>     buttonNext?: string;
>   }
>   desktop?: {
>     instruction?: string;
>     title?: string;
>   }
> }
> ```
> For more details check the `IModuleCustomizationLegendsManualCapture` interface

### Features

* desktop version in manual capture ([5159a4f](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/5159a4fa67f5e73c364415e8b16159f33de13996))


* new structure of legends ([10cd0aa](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/10cd0aacdd1b101cb97cf0d9e56d28e4c72f4387))
* tooltip as general legend. ([eb20b02](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/eb20b02cc10f8ffc40d992a96696433c13b208b3))

## [3.12.0](https://na-at.xp-dev.com/git/FAD-ACUANT/compare/8ae134272bc8491b99b6215bbd346f67d33bd3f4...v3.12.0) (2023-03-07)


### Features

* @fad-producto/ng-fad-loader ([d1747c8](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/d1747c829ca1db0ee4f80cb9c8eca4a66735e521))
* active manual capture with parameter ([b09877c](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/b09877c4412091bd6dcb517f68274a1a1bc67ce8))
* activeBlackScreen to false in initDone ([11f3364](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/11f336414765455b5da5e68cc8b0dea1c092674c))
* Acuant fields exported ([43aadb6](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/43aadb6ebbfdde1d959fdc8482548cd93d0a33a3))
* Acuant SDK 11.7.1 ([04cb240](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/04cb240a1d7383b7396856d6413c57486965fd0e))
* Acuant SDK files updated ([efc428e](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/efc428e84190ee3fd2f0adcdd2df12092cd2601f))
* Acuant version v11.6.4 ([8e7de19](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/8e7de1987047ab744e1db9bf6b458a2735eaba5c))
* add dataFields to idData result ([135779f](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/135779fcad311b7f8e3127852fa2b68735d9e23f))
* add dynamic imageQuality ([63cea9e](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/63cea9e25cca89fc05e545492a27e060420494c2))
* add force photo ([fd03b34](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/fd03b3406dab2052b8014188e796e65d5131bc6a))
* add force photo for every case ([ca76c48](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/ca76c48d4f65ae3e7129da27a194e114c87894b3))
* add log ([b2b80d6](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/b2b80d63efe53490623d4294cc8e0b27c087d60e))
* add log ([110a2d1](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/110a2d17d0515754c952bd64b0b2f414631e09c5))
* add log to end of cropped ([49a3908](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/49a3908a438d72c533476e82cd3fdbdbb3e92a32))
* add result and alerts object ([2040736](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/2040736447c3c0ae889ce8428eefa4831f0f29a9))
* add surname to result ([9a1922b](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/9a1922b5e4154a4fccb40f77422d5117f1a6cfbe))
* add timeout to initDone in blackScren ([4b87a99](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/4b87a99e51c72a2f06f71bcf44fdf298599d5e89))
* BIG_DOCUMENT legend ([78cb8ff](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/78cb8ff4e9fd106415dee0f11cbf39f0d374d155))
* catch error when script failed to load resources ([b9852b5](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/b9852b58787555165ec3b0c78f71315d08dd3993))
* change  Personal Number by VZ2 Personal Number ([310f81f](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/310f81f76e13460dec8ab1119ee225d10be0e56e))
* change services to fecth to prevent interceptor ([f38a93c](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/f38a93c6d3a23968e00b40cf18017811bdb6108b))
* classification in idData ([618d405](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/618d40569cd9eac980122c2cd202233f28ec61d6))
* constants and models exported ([323b840](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/323b840b3f24c7a1e19b69090c2f5fa3180cd7d6))
* create fad-acuant brigde ([9abdf2a](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/9abdf2ae1d5890337fc7294a9c1d63f5a7c2b3b5))
* desktop support ([44b8dfa](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/44b8dfaf4747053b51942464178175ac25531e71))
* download optimization and active loader ([9b7ce31](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/9b7ce31ac324b510b62628118bc32a2195c2f48c))
* dynamic legends ([44b616e](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/44b616eac7e59f57330845deb8d64f91f62abb15))
* errorResponse with data ([b0d6848](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/b0d6848436d2b2967ac62349a0d06dcd7a8bab52))
* export models ([b0e7705](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/b0e77050634d62d5883351ac2ca40a573155ef04))
* export models and constants ([2927a05](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/2927a05a73877b8f27e91c3a4d4b4cb014d65437))
* first version acuant ([8ae1342](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/8ae134272bc8491b99b6215bbd346f67d33bd3f4))
* link images, front and back ([f67cd90](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/f67cd908fe863bb2a7a53921932fc145cf61decf))
* loader example ([da71d3d](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/da71d3d9ecf7feb541af6c8f3193fcc1eca6cd5e))
* local loader deleted ([17f620d](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/17f620dba292279e3292dc10a0a7d4cf23a23bd6))
* manual capture support ([42c58fd](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/42c58fd3f79e1b26291b6c882cf57d36cfabad6f))
* moduleConfiguration classes removed ([19bb1d6](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/19bb1d628a18f314cf6be76f9751e6dc3f2e4497))
* ModuleCustomizationStyle and ModuleCustomizationLegendsCommon ([d264069](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/d2640692013a7f58efdfed6327654112144c077a))
* ocr default false ([b0c2525](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/b0c2525d66949bd549da92f56b94ecdf22f1a4ce))
* refactor ([181c11c](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/181c11c7d12c37dec1a0e08881c9026eb53caa43))
* removing variables css on exit ([7894b96](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/7894b96d682fff4a2de891d8a063fee8ffb026c1))
* return of ocr and face image ([c5c389e](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/c5c389e5f7f4fa9c624ed0381728316d9c750136))
* sharpnessThreshold ([dd942d2](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/dd942d25920d61edd98ff156d7277d831ccabdbe))
* test-ng-fad-loader lib ([eafb328](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/eafb328ce1e265a35fa24304f055b4637a755a4b))
* TestNgFadLoader ([0d00210](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/0d00210860e796f584cc350859758bcdcaecf0e5))
* Type in AcuantField ([bef5376](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/bef5376cc115ec657a7828a832fd99313079bad3))
* UNSUPPORTED_IMAGE error ([3cc501d](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/3cc501db6a473905152d96455d28df37888ac94f))
* update acuant resources, acuant version: 11.6.3 ([9d91874](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/9d918749eee8b866ae2705ab4bc0ea3614f8c252))
* update acuant sdk ([d3e32fc](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/d3e32fcf6b60f585b25c812d50b5457d8f069f86))
* update acuant to las version 11.5.0 ([d7507d0](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/d7507d0701a38c13f08e0f958310f2a5cbc8180c))
* update new acuant version (11.6.1) ([039d5ba](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/039d5ba5b7af0bc51ec0c657f2f598ea430c5711))
* update version 1.0.1 ([0f2c7f4](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/0f2c7f42fb394cc114c5f012afb8edd854d7cb4c))
* update version 3.0.6 ([0040297](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/00402976caf4a8e91e9efdf45fac1555b94c964b))
* validate face image not empty ([a553cdc](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/a553cdc7a79071b5a28c3df5ec9ea44a150b345d))


### Bug Fixes

* AcuantAlert with Model ([0e254e2](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/0e254e275a9534c317f7cb4dabe259f93aef61ce))
* AcuantResultImage cardtype ([3fe2308](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/3fe23080b81bfe3eeb0a37887cc46c47eed527fc))
* backgroundColor #FFFFFF ([6f375ac](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/6f375ac563e603fe5211957e20f7f54f7546af39))
* change configuration for moduleConfiguration ([675ed08](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/675ed0816d9ccc96e41a7026fd686e3fe6f50bf3))
* check if AcuantConfig and CameraUI are declared ([499324f](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/499324fe5a4b1d97777c11d13b8fa390cfc36f42))
* classification sides null ([1b9c29e](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/1b9c29eabfa5b1b577ff0102713c67c878fa29ff))
* default loader configuration ([b2d65a2](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/b2d65a25b25806e45e5e7c371c746beeb70bf283))
* loader hidden when manualCapture starts ([3315542](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/331554241988718cdafe02071691d2adae904ba5))
* loader legend ([62745d5](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/62745d5cecf679e36b282fc959da5f752eb80ddd))
* loader show/hide ([add8ca8](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/add8ca8e9e0570a101dede01e13a612d3cb29e35))
* projects/**/node_modules added to gitignore ([03c8b96](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/03c8b96070a8c115c6d0f5c47472bca32da9d809))
* remove callled startManualCapture()  from showAutomaticCapture ([674a17a](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/674a17af6ee7485a65252fc10d6f00d522980f15))
* reomveCustomizationStyle() ([fa28786](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/fa2878641da8ab276e21e0cf2b4f38db254538cf))
* return to manual if is desktop ([0f53a8c](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/0f53a8ca2376956c23688615d76034317fb22017))
* showManualCapture  from failed in Automatic Capture ([c07d1a0](https://na-at.xp-dev.com/git/FAD-ACUANT/commit/c07d1a0d9fde805ac77bd88604cc88e6a62a9c7d))
