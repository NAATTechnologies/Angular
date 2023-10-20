# FAD-SIGNATURE Migration Details (CHANGELOG)

## [5.0.1](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v5.0.1-alpha.0...v5.0.1) (2023-05-03) v2.0.0

### Changes
* No relevant changes since v5.0.1-alpha.0

## [5.0.1-alpha.0](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v5.0.0...v5.0.1-alpha.0) (2023-04-27)


### Bug Fixes

* SignaturePad fixes for Samsung mobiles with Chrome  ([8d82566](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/8d825662469fd96ba063dd7b66f2180d0832b899))

## [5.0.0](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v5.0.0-alpha.0...v5.0.0) (2023-04-20)

### Changes 
* internal @fad-producto/ng-fad-image-inline updated to v2.0.0

## [5.0.0-alpha.0](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v4.1.2...v5.0.0-alpha.0) (2023-03-22)


### ⚠ BREAKING CHANGES

* faceUndected is renamed to faceUndetected


> Customizable timer property structure has been modified. The new property to set the time to trigger the error for an undetected face is  `faceUndetected`.
>
>Previous versions had a typo for this property (faceUndected)
> ``` ts
> configuration: ISignatureConfiguration {
>  ...
>   timer: {
>      recording: { min: number, max: number },
>      faceUndetected: number
>    }
>    ...
> }
> ```
> For more details check the `ITimer` interface

### Bug Fixes

* @fad-producto/fad-common v3.0.0  updated to fix the faceUndetected variable name in the configuration object ([5cbd85c](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/5cbd85c955c66194b1bd194eaa1c5d7e4db0ac4f))

## [4.1.2](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v4.1.1...v4.1.2) (2023-03-15)
  
### Bug Fixes
* internal @fad-producto/fad-common library updated to v2.1.1 to fix the mixes of mobile media properties between different @fad-producto libs when the customization object was modified

## [4.1.1](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v4.1.0...v4.1.1) (2023-03-08)


### Bug Fixes

* fonts colors changed to #FFFFFF ([4de777c](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/4de777c42e13b0550a510ec23f48f805edd1b9f7))

## [4.1.0](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v4.1.0-alpha.4...v4.1.0) (2023-01-31)

### Bug Fixes 
* internal @fad-producto/fad-common library updated to v2.0.1 to set the default primary button border color to transparent
## [4.1.0-alpha.4](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v4.1.0-alpha.3...v4.1.0-alpha.4) (2023-01-20)


### Features
* Adds an internal referenceElement option as a parent HTML element that contains the CSS variables that should not be overwritten. ([2bd31a9](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/2bd31a9c2a7c3638e680c9dd604cf7f6082b5301))

## [4.1.0-alpha.3](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v4.1.0-alpha.2...v4.1.0-alpha.3) (2023-01-19)

### Changes
* internal changes in Utils to manage the customizable styles

## [4.1.0-alpha.2](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v4.1.0-alpha.0...v4.1.0-alpha.2) (2023-01-19)


### Features

* Adds an internal referenceElement option as a parent HTML element that contains the CSS variables that should not be overwritten. ([65f7246](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/65f7246856641dec6c4e437eac7ed82f79fb31b9))

## [4.1.0-alpha.0](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v4.0.7...v4.1.0-alpha.0) (2023-01-19)


### Features

* Respects a parent CSS variable when the variables has the `!important` attribute ([4d8a1c5](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/4d8a1c50eeab1174b1fcc50fb8a85c9fa29c4826))

## [4.0.7](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v4.0.6...v4.0.7) (2022-12-16)

### Bug Fixes 
* internal @fad-producto/fad-common library updated to v1.1.2 to fix the mixes of styles between different @fad-producto libs when the customization object was modified using functions instead of constants

## [4.0.6](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v4.0.4...v4.0.6) (2022-12-12)


### Bug Fixes

* signture mediaRecorder stops on errors ([3e7aa00](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/3e7aa004186dec91ad017744ce76323f16183511))

## [4.0.5](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v4.0.5...v4.0.6) (2022-12-12)


### Bug Fixes
* internal @fad-producto/fad-common library updated to v1.1.1 to fix the mixes of mobile media properties between different @fad-producto libs when the customization object was modified


## [4.0.4](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v4.0.3...v4.0.4) (2022-11-09)


### Bug Fixes

* stop stream before mediaRecorder ([6937c0f](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/6937c0f576e0285574df8b511330a727a583071b))

## [4.0.3](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v4.0.2...v4.0.3) (2022-11-09)


### Bug Fixes

* try-finally for prevent errors when the media recorder erros has been closed previously ([381372b](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/381372b6ac17119889d7225577398b883076da2a))

## [4.0.2](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v4.0.1...v4.0.2) (2022-11-09)


### Bug Fixes

* signature's media recorder stops when the component is destroyed to fix an error in iOS 15 devices when the recorder stream is not manually closed ([49ea49e](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/49ea49ea75d1473c1d213c3484ea1b41f8debdba))

## [4.0.1](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v4.0.0...v4.0.1) (2022-10-26)

### Bug Fixes
* SingatureConfiguration class removed; use ISingatureConfiguration instead


## [4.0.0](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v3.0.1...v4.0.0) (2022-10-24)


### ⚠ BREAKING CHANGES
* Background color for disabled buttons as general attribute of buttons instead of a specific property for each button type (primary, secondary)
* Label color for disabled buttons as general attribute of buttons instead of a specific property for each button type (primary, secondary)
* Border attribute for buttons removed; instead use borderColor, borderStyle and borderWidth attributes

> Customizable buttons (`fadCustomization`) structure has been modified. Now `backgroundColorDisabled` and `labelColorDisabled` can be modified using the `buttons.common` property. Border properties of each type of button must be modified using the specific property (`borderColor`, `borderStyle` or `borderWidth`) instead of the use a general `border` property
>
>Previous versions had a `backgroundColorDisabled` and a `labelColorDisabled` for each button type (primary, secondary). The `border` properties could be modified using a single border attribute to customize the width, color and style (`'1px solid green'`).
> ``` ts
> buttons: {
>   primary: {
>     backgroundColor?: string,
>     labelColor?: string,
>     borderColor?: string,
>     borderStyle?: string,
>     borderWidth?: string
>   },
>   secondary: {
>     backgroundColor?: string,
>     labelColor?: string,
>     borderColor?: string,
>     borderStyle?: string,
>     borderWidth?: string,
>   },
>   common: {
>     height?: string,
>     width?: string,
>     borderRadius?: string,
>     backgroundColorDisabled?: string,
>     labelColorDisabled?: string,
>     padding?: string,
>     margin?: string,
>     outline?: string,
>   }
> }
> ```
> For more details check the `IFadCustomizationButtons` interface


### Features
* errorColor
* primary button border style
* primary button border width
* secondary button border style
* secondary button border width
* common button background color disabled
* common button label color disabled

## [3.0.1](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/v3.0.0...v3.0.1) (2022-10-12)


### Bug Fixes

* maxRecording in timer ([fd4d645](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/fd4d645abd67c1658d4d88073b56ccc1ba51704d))

## [3.0.0](https://na-at.xp-dev.com/git/FAD-SIGNATURE/compare/dc0c3d676da5bfbfae0dca56fa143c65e96616b9...v3.0.0) (2022-10-12)


### Features

* add invalid signature validation ([ad1c48e](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/ad1c48e1e461eeaf39b8b9023b3ebe93cdd0e222))
* add log and validation to mediaRecorder ([c006d9f](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/c006d9f3de468461f70dc7ebcc208fd123e2ff0c))
* add log to validateVideo ([d66fe76](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/d66fe76dd0676ee9ce0ac952c35a6dd7b3390591))
* add signature data complete ([99729e2](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/99729e20bf088650b42257b21ac8cc611134d77a))
* add signature pad integration ([4b4444f](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/4b4444f125d8c218d9639bd50ff2fd48fa3ec031))
* add user-select: none to module ([0ef845f](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/0ef845fcbb36dee29db9833484ef09ab61237343))
* add validation (video empty) ([f14ca56](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/f14ca56af358a1ba4d50684f06461c374892fc79))
* add video validation (empty and no audio) ([11d1cfc](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/11d1cfc23ae9ad031c70296ccc68f0dd18a51ea0))
* capure-selfie ([b4d36b5](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/b4d36b5e62e710fa8e250619dd60ec2542365a08))
* catch NotReadableError in getUserMedia ([52bb0fb](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/52bb0fb7e4438317021a3aa81f7d8e2e48a9fb38))
* ceil cancas signature android ([170922c](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/170922cef0432b140911bcca5d205511d8393384))
* change audio detection to float ([6f86654](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/6f866544aadc3446e7f638930344ac10e04a41b4))
* change autoplay for play method and catch video error ([aca9171](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/aca9171bba817e460f16a557233196c0a29078cc))
* change facedetection  dependencies ([8b86277](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/8b8627783ac0d34a7fc6277ebf53d8dc7330a9c3))
* change platform to configuration ([b597220](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/b597220f78f2ab85383e867cf25f796bd4f41b9b))
* change support ffmpeg to MediaRecorder when is necessary ([39d1a4d](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/39d1a4d8672ae8f77c5fc448de0851b65b25aff7))
* change title to project ([37e02a8](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/37e02a84b8f1f2be145c2fd23531f9122faddcc3))
* change unit test module ([0ca6d3b](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/0ca6d3bf2133507d737b20741b936e9572052a6c))
* close button removed ([1cbb905](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/1cbb9055942c5991732df31cb71d075269b657c8))
* down setTimeout  mediaRecorder.stop() to 800 ms ([b9e4e3c](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/b9e4e3ca1fcd7fd03b3f2fd1fb5f45b9a0530d06))
* drawGuides with timeout ([e6005c2](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/e6005c27339401194af3e805db724a275f1a5d09))
* export models and const ([38d300e](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/38d300ef6ea898e79ecd7440a28106672f4aae06))
* face detction flexible and add legend to view ([b9b7a84](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/b9b7a842ef5c4cd2e850f0d089dd362665cb1f17))
* face detection ellipse center and change constraints iOS ([5821fef](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/5821fef098327c7575ee2d4e3b3ac55dde7d36e2))
* face detection guides ([dadbeeb](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/dadbeebdc02d94ee35bc90a15e35bfcc25a92258))
* face detection restiction and face detection validation to init ([db15e7e](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/db15e7e603c0de66e235256183a3142fb636f989))
* faceUndected time up to 5 seconds ([341f978](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/341f9780d600e506010b79d33ef0b45d17d6fe0b))
* fad signature module pad integration ([dc0c3d6](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/dc0c3d676da5bfbfae0dca56fa143c65e96616b9))
* fix old devices AudioContext ([9026065](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/90260655b923c87059df499e058768c3694d18f4))
* moduleConfiguration classes removed ([d1b40fd](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/d1b40fdb6465d47d73b7a1398bc17a84a2140278))
* ModuleCustomizationStyle and ModuleCustomizationLegendsCommon ([672c2a6](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/672c2a6d6a1d7234f54a2c83053df5742951d00a))
* new configuration (faceDetection) ([cc2ba9f](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/cc2ba9f7f883741819a7687d2f1efa29343a625d))
* No media recorder deprecated ([e05e094](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/e05e094dfe01ea186018b707da850992b38ef7c6))
* no record audio by default ([665d669](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/665d6691f8d531145cc5b0110135a604db9dafc6))
* record audio again and no validate audioRequired ([460feda](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/460fedad5c1aabc23a3f135219e740e3a536542c))
* reduce menory ([e640c2a](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/e640c2aa83755f7899ae2fa097ec06ea91aad77c))
* reduce video size in iOS with mediaRecorder ([d81b6c0](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/d81b6c0b776cd6c029b083704742a5a43a72d02d))
* refactor structure and android recording signature ([350590a](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/350590ac6cfc67d10ae924d1456b8d85d33ab464))
* remove legend validation ([4f3c810](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/4f3c8107f5bdfdc72f85a5c995e9fc5bed44edc7))
* remove pipe unused ([393d588](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/393d588fa17b127f5dff26943c72cd70da67cca4))
* remove unused code and classes ([a8905b7](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/a8905b774483b0accfccdc1d196355d160bcd1e7))
* removing variables css on exit ([c7ba9cd](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/c7ba9cd848f4fe071536e55ed750b7e340d182bd))
* rename to signature ([2a926dd](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/2a926ddfa1b1bfa412f88e00718d60b93fcfcc07))
* return error to fail load model wasm ([79a5d92](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/79a5d92c2cfca06c81dc77df07a7c4e4e4e96e65))
* revert always face detection ([cbbff0e](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/cbbff0e84fc059863f51d0aab11dc1aa814e9916))
* show dowload posibility ([f6aefba](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/f6aefba5d956645da576ff046fd58ad2657a2ab7))
* signature not pixelated ([ad7b445](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/ad7b44562ba883ad0941c4181998a1317dfdf6ed))
* sucsuccessful-color in recording.svg ([db56c79](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/db56c796ffe8aa041532dadeed2d359fd6346692))
* support safari browser ([c0c2965](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/c0c2965403e42d1b544cd7857d31cfb8c77b0bb7))
* test-ng-fad-loader lib ([8773608](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/8773608de454653f36d274b6d3a9406280ee616a))
* up frames signature ([9d428f9](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/9d428f96f0ef705e2e757730d651f3db5920162c))
* up setTimeout  mediaRecorder.stop() to 1000 ms and add black screen in signature pad ([5fcfde4](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/5fcfde4cc7b52c89b958042f7c265bfd8ff37909))
* up setTimeout  mediaRecorder.stop() to 600m ms ([7600933](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/760093312d6e6fb712b186f155841efaf988f2f5))
* use code vp9 by default ([c20ec73](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/c20ec73a0f1b40eb5b3aaa8ead7eacef228bee38))
* video mirror implementation ([608dcd5](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/608dcd581ba029d23313868231709b3835602a2f))
* videos size optimization ([e2a3949](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/e2a3949b23be887ab6569e970eeb9ca743dfdcd8))
* warning instruction ([a2b28bf](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/a2b28bf81ae88de0bba60205f74f9ce1f899532d))


### Bug Fixes

* adjust to tablet android ([06f02db](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/06f02dbc54c39e745e378d120b7c6fa865571f1e))
* android 11 chrome freeze ([ec6ef0c](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/ec6ef0c4a7d3b560b4ab25fb33afe5fda8a4bd02))
* blobSignature validated via validateVideo() ([590bf25](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/590bf255de96325d05f42339e291de7349a04199))
* captureStream with default frames ([718888f](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/718888f4b038edc90560e5ed57bcf846bbeea382))
* code-protection after camera accepted ([33021bf](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/33021bfdbbc5bc7db4d378f9627ff245ceff4c20))
* duplicated response removed ([ef7e1f7](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/ef7e1f7469e0b6e2a1152452d6ec6f318f9a2a4a))
* host container to 100% height ([0fa3e4f](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/0fa3e4fd86dc749291a16a29c0de8e25a1c9dc6b))
* image tap ([fb1895a](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/fb1895ae4a8c3e174aac6ff16b573ef3bfefdd08))
* iOS 15 black screen ([6edd956](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/6edd9569fb2276b1704214370a6f0687c6cbc740))
* ipad and small devices ([0450597](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/04505973bfeccf285dad40afc2aaaa1ae46bc3e7))
* MediaStream error ([35785b3](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/35785b366a998e2ac5d95052c1ae65939c914a2f))
* projects/ng-fad-signature/node_modules deleted ([a1d0124](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/a1d0124292750e25490d7985b0fecd989f8d2cd7))
* signaturePad recording in iOS ([ec9e9ea](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/ec9e9ea31a84f98cedac32964b389606bf8a15b0))
* stream.removeTrack removed ([7746b52](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/7746b52981a56f14c6394a701a9d0b5d014e9849))
* video object fit cover ([87f1575](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/87f1575ce68313fd111783785b3282fbfe1cc5d8))
* videos cropped ([bc2b8d5](https://na-at.xp-dev.com/git/FAD-SIGNATURE/commit/bc2b8d54fb589f80424bf01a9e94064ed77a9e29))
