# FAD-VIDEOAGREEMENT Migration Details (CHANGELOG)


All notable changes to this project will be documented in this file. See [commit-and-tag-version](https://github.com/absolute-version/commit-and-tag-version) for commit guidelines.

## [6.1.0-alpha.0](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/compare/v6.0.0...v6.1.0-alpha.0) (2023-08-31)


### Features

* header with face detection ([a14c3ef](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/a14c3efbdd675d190f5fd433ee8ca5f9eb12d56f))

## [6.0.0](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/compare/v5.1.0...v6.0.0) (2023-07-04)


### ⚠ BREAKING CHANGES

* Removes the unused property desktop inside the configuration object

* IMediaConfigurationMobile instead of IMediaConfiguration ([4b0fe07](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/4b0fe0774d2f51a25a426f0be54ac167a57c3733))

## [5.1.0](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/compare/v5.0.0...v5.1.0) (2023-06-23)


### Features

* allow to close the component. ([057a58e](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/057a58eb140d25ae07e385fd4883070cac22e6c3))

## [5.0.0](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/compare/v5.0.0-alpha.0...v5.0.0) (2023-04-20)

### Changes 
* internal @fad-producto/ng-fad-image-inline updated to v2.0.0

## [5.0.0-alpha.0](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/compare/v4.1.2...v5.0.0-alpha.0) (2023-03-22)


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


## [4.1.2](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/compare/v4.1.1...v4.1.2) (2023-03-15)

### Bug Fixes
* internal @fad-producto/fad-common library updated to v2.1.1 to fix the mixes of mobile media properties between different @fad-producto libs when the customization object was modified

## [4.1.1](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/compare/v4.1.0...v4.1.1) (2023-03-15)


### Bug Fixes

* fonts colors changed to #FFFFFF ([7ea6b15](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/7ea6b152c8884b7ed294c51300ece4c69daa1835))

## [4.1.0](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/compare/v4.1.0-alpha.0...v4.1.0) (2023-01-31)

### Bug Fixes 
* internal @fad-producto/fad-common library updated to v2.0.1 to set the default primary button border color to transparent
  
## [4.1.0-alpha.0](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/compare/v4.0.4...v4.1.0-alpha.0) (2023-01-23)

### Changes

* Customization styles are injected in the module tag for avoiding customization mixes

## [4.0.4](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/compare/v4.0.1...v4.0.4) (2022-11-10)

### Changes
* Removes unused code lines
  
## [4.0.1](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/compare/v4.0.0...v4.0.1) (2022-10-27)


### Features

* VideoagreementConfiguration removed; use IVideoagreementConfiguration instead ([cd369e5](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/cd369e5fbef472b72c131a6932d0f1218151f9a3))


### Bug Fixes

* videoConstraints removed in custom config ([3c2899d](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/3c2899d6f8c92397a74cb3062a6bd5fe19ebf78e))

## [4.0.0](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/compare/v3.0.0...v4.0.0) (2022-10-24)


### ⚠ BREAKING CHANGES
* Background color for disabled buttons as general attribute of buttons instead of a specific property for each button type (primary, secondary)
* Label color for disabled buttons as general attribute of buttons instead of a specific property for each button type (primary, secondary)
* Border attribute for buttons removed; instead use borderColor, borderStyle and borderWidth attributes

> Customizable buttons (`fadCustomization`) structure has been modified. Now `backgroundColorDisabled` and `labelColorDisabled` can be modified using the `buttons.common` property. Border properties of each type of button must be modified using the specific property (`borderColor`, `borderStyle` or `borderWidth`) instead of using a general `border` property
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
* common button label color disabled ([b3e1cef](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/b3e1cefc1dafb91b1ee360cb225e3d56160e9b7f))

## [3.0.0](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/compare/efd98d4612e2728733d7604357ff92fe60be465c...v3.0.0) (2022-10-12)


### Features

* @fad-producto/ng-fad-loader ([9cbe944](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/9cbe944ae290509d00d7416f761ea3864d39adf0))
* add log to legend span ([cf1ee04](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/cf1ee04415ad199d652defea9556f79ddbab52b8))
* add log to legend span ([f99520d](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/f99520dac807a76a3d1c09a3fc0810d41334bac3))
* add new varibles css ([cb8e871](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/cb8e871160c8095a419b6ebf2f94f4aa680bfbb0))
* add new varibles css ([35313cb](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/35313cb90a4479c398097f6bd96583b49607ba83))
* add no translate to legend ([e6f6bb3](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/e6f6bb30fcd6560c05931cd7c339ad6c6886943c))
* add no translate to legend ([e5f3690](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/e5f3690c7fbf23eea6e419c6b3a2fcca8094d25a))
* add tertiary variable css ([8293c77](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/8293c77376b62eb6a259c9c35a7e07955bd74d21))
* add tertiary variable css ([52f88f8](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/52f88f8fb03d60631a86f295a9b48cbafe3a0e1d))
* add validation (video empty) ([6085cb4](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/6085cb4e168d8d113d1ba5e12391ad7003f120a4))
* add validation (video empty) ([addc1cf](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/addc1cf2daf9c63bd4b729b5c0cba3e1d19f49c1))
* add video validation (empty and no audio) ([8c7af62](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/8c7af62b9d4b1c1ec78dbd6ffc8ff0320b5f6e46))
* better capture selfie ([67d95f5](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/67d95f5c0f6e42584c99d00b918eeafb5f29eca2))
* catch NotReadableError in getUserMedia ([74139bb](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/74139bb241b9590eafa94caa071039e02e994f96))
* catch NotReadableError in getUserMedia ([750ac63](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/750ac634a9062c09e9ffb735ae9807a9368e283d))
* change audio detection to float ([b3ba173](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/b3ba17303115b4afca027c8a546deeecfa2dd7c4))
* change autoplay for play method and catch video error ([6eb73f4](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/6eb73f4c98ed128680dbd0b9f9613650fdbf0883))
* change image audiowave and remove white space ([aad165c](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/aad165ca03ed0acdd742a94afe74ad53162cad6e))
* change image audiowave and remove white space ([23fb295](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/23fb295eb5434e0b09edbc23df1cfb03ef3ec5dd))
* change span for font ([d48e813](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/d48e813f9a6a65f1e637dcbd14c0dc9353aa0f32))
* change span for font ([a286232](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/a2862323ed321726d6f7555984d0f19d348f8988))
* change support ffmpeg to MediaRecorder when is necessary ([85cfc0e](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/85cfc0e7559b487441dce1994a22957ca434731e))
* change support ffmpeg to MediaRecorder when is necessary ([dc10df7](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/dc10df7e84a007b0b7b3fb3761d2babeacb8e8df))
* close button removed ([4c918db](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/4c918db085f1574c8d862241a30fa18158df1af9))
* close button removed ([fca3578](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/fca3578a6ae723588ead4460d601600664cc1fa5))
* code-protection ([aa85fe6](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/aa85fe624790880327716378ebc12ec8b30c7896))
* configuration object exported ([e1c7642](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/e1c76420f0c36dbe3668facd4c4c865bb6e55fc0))
* default values taken from @fad-producto/fad-common ([3d97eb6](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/3d97eb651aac3de1aa0f4dbdfee5b5b4815b5f81))
* export errors ([2712bd3](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/2712bd3f751ff40dcf51705bd9e73e0bf238d263))
* export models ([52724ae](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/52724ae7385006f74dbb6231679f93780b5a517f))
* export models and const ([7bb2e56](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/7bb2e56e0280f983211e2271700e2874995f7a82))
* face detction flexible and add legend to view ([cb808f1](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/cb808f110d8d8bfc9ad92f19dbbb469be192853c))
* face detction flexible and add legend to view ([d441f13](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/d441f132407cffe9b6dcd1cbaeef7d1e22af3d4d))
* face detecction restriction ([21b7b36](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/21b7b3644fce1be56eb4b02ad66350657720c471))
* face detecction restriction ([093c967](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/093c967e2c232e8ed4a55191120a302376ec761a))
* face detection ellipse center and change constraints iOS ([d734931](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/d734931032702aaad7172d6eae82bb5455b78fff))
* face detection ellipse center and change constraints iOS ([b18414e](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/b18414ec39cdab4ee505d85f8d9d272012f29061))
* face detection guides ([c8918ed](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/c8918ed627cf1e76b506f8f570175b917add2a4d))
* face detection guides ([b63f17a](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/b63f17a6d29f179dba61e1382e2ccbe6ea660fc9))
* faceUndected time up to 5 seconds ([bf948f3](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/bf948f347dfb8181073afae96ef1c7e88930bdbf))
* faceUndected time up to 5 seconds ([41510ba](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/41510ba5bc1252f0c44c87ddef17f8616ff7c93b))
* hide box whe face is undetected ([695eaa2](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/695eaa26f52eb8a9d9e225f6c98fb1c632d4c836))
* hide box whe face is undetected ([fc348bb](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/fc348bb953863c0f350bae5bc4d341f05585e269))
* import fad-common and restructuration ([8b73cc5](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/8b73cc5e9ce313a31c6eb615a5e4f56b35520492))
* import fad-common and restructuration ([9dae47b](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/9dae47b15100074bce045bbd201512435753370d))
* min recording to 5 and style button ([b0a4991](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/b0a49914ac8630548cfbbd985f1132a4b6b5e50b))
* min recording to 5 and style button ([b161f32](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/b161f321f47d7bc1875a0aca45de843667bdf74e))
* module new version 2.0.0 ([bf8bd76](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/bf8bd76b781598511217d019cbfa210bfdc4936e))
* module new version 2.0.0 ([cb68a52](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/cb68a52bcb6b54bbbfe188432531dc65940720db))
* moduleConfiguration classes removed ([97e48a1](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/97e48a1e195d9de0c037c1f83884671570d7e400))
* ModuleCustomizationStyle and ModuleCustomizationLegendsCommon ([6737c38](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/6737c38854748986e3f4835648856f7c54ccdf4d))
* new configuration (faceDetection) ([5986a0a](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/5986a0a40c2111d3199c0e59752276eb287db7cc))
* new configuration (faceDetection) ([3af82d0](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/3af82d050a255f41ca12503ff360690afa24e97f))
* new version 1.0.4 ([86314ab](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/86314abc85413917b34129d8c272fdfae86345ad))
* new version 1.0.4 ([8e7cd18](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/8e7cd18ec4f774b81db2ac7bc5636d8fc435a525))
* No media recorder deprecated ([c171ed6](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/c171ed6aeac78df8d4a0e5f98d5747f6539b53f2))
* reduce video size in iOS with mediaRecorder ([2c8b081](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/2c8b08101c06f61c7c1ea678ce621ab2c77a3a01))
* reduce video size in iOS with mediaRecorder ([4e95053](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/4e95053e4702dfbd20a5a79b04f2070fe1fd267b))
* remove orientation legends ([efd98d4](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/efd98d4612e2728733d7604357ff92fe60be465c))
* remove unused code ([0ed3dcc](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/0ed3dcc92d98e8c5c5e7338b8ce87a5d926b46d4))
* remove unused code ([1043270](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/10432703b18cfdcb4262d509f3245c5a1e92c7d0))
* removing variables css on exit ([c9f602d](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/c9f602dcb4faf4aa17ad3597dc43c0ca26ebc22c))
* removing variables css on exit ([af65666](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/af6566612768ae8866d48d4acd2087d36f7535e2))
* return initials selfie when is required ([09a3ad4](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/09a3ad4004b810c9798e495599dac627feaaeba4))
* sucsuccessful-color in recording.svg ([be4c49d](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/be4c49dfeef5566ccb6945e208c0d2f8d6e99c1b))
* support safari browser ([8846643](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/8846643d1e49685b23910140b0107c2acd69ad0c))
* support safari browser ([1867f4e](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/1867f4e1748600fc0b92bdd51cb6ac163f6d0491))
* test-ng-fad-loader lib ([cddd66d](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/cddd66dc4a2bb92810c55808c9c3609167fb24d5))
* up setTimeout  mediaRecorder.stop() to 800m ms ([8575745](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/85757452844534a665f513a05571f964c0e2637c))
* up setTimeout  mediaRecorder.stop() to 800m ms ([aa9e39a](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/aa9e39ab5b82ed58709b55965ef4ce3269e05b7c))
* update  version 4.0.0 ([b5118ea](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/b5118ea39cbbf56d5009ad30785403cee6777c32))
* update  version 4.0.0 ([1a2f037](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/1a2f03789e50286e9170edf33974846e8a02b4e3))
* update tensorflow dependencies ([2cff755](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/2cff755e4296659b28b06cbb250637d233df90c8))
* update tensorflow dependencies ([e26fe84](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/e26fe84b5f64c3c07de2e1bd0e304c822401db2c))
* update veresion 4.0.1 ([3ef6a6f](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/3ef6a6f39935cb7fb0a9b28c344bcb9d1c00e434))
* update veresion 4.0.1 ([2f312f2](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/2f312f27bed373ac68be9a0aa56e552c8f313f51))
* update version 3.0.0 ([271ea91](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/271ea9174db4a4349b9a80f69c4944711a8df202))
* update version 3.0.0 ([87c0a9d](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/87c0a9d33040da556c6f0620f1400c5a9a9bae95))
* update version 4.0.2 ([c504617](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/c504617d4877fdcd2f52a2310ad7d2eab52c8215))
* update version 4.0.2 ([6c5bed3](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/6c5bed32467fe15804524ec17300227ba3159a4f))
* update version 4.0.3 ([2ae3c23](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/2ae3c23b5844dc0e949403c6a48b9daaa577e501))
* update version 4.0.3 ([2a92697](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/2a92697aad9330bfe99716b6da60dc2b95d7db35))
* update version 5.0.0 ([51d6719](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/51d6719ad02ebf5878fe966de858ba02bf6bafa0))
* update version 6.0.0 ([56ec225](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/56ec22538e71238de2417e7d08996cda693162b0))
* update version 6.0.0 ([25e5973](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/25e5973f7b4664b59801156cfb1409e01ad4fe9d))
* update version 6.0.1 ([737302e](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/737302e93b6f7a2e5e579f60c0f1db7204ed6364))
* update version 6.0.1 ([8c5322b](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/8c5322bf080950fe73f3de3117bd3e5aa5ef6463))
* update version 6.0.10 ([7c2f036](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/7c2f0360f3c0af4af041be4ac669d67633b12b90))
* update version 6.0.10 ([bc14bb5](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/bc14bb543e894986ae37efebca6ea367eb43aae2))
* update version 6.0.2 ([6b5a789](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/6b5a789b2e19e53b4e3bea1f99b2677e1a3c103e))
* update version 6.0.2 ([394864a](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/394864ad2a98b27d199ebcca56e636b2bf075fc5))
* update version 6.0.3 ([b51c33e](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/b51c33e04c00bd6546b816a7e5dfdc92fe3992ed))
* update version 6.0.3 ([d065f7a](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/d065f7a8783c476cd394fde46748fb41bff1a969))
* update version 6.0.4 ([869cfd5](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/869cfd5d1ff0b8d40b992c54a04ed506ad306aff))
* update version 6.0.4 ([449000a](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/449000aeda66a26a0520c74cb32b9432fbd8ed48))
* update version 6.0.5 ([bc2a5a3](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/bc2a5a3e0c3e455008243199a6d4b21e1ed9148d))
* update version 6.0.5 ([9a2ca36](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/9a2ca36506c5890f344f69f754a89380bf90517b))
* update version 6.0.6 ([f87bfa2](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/f87bfa2c193b5e43853264eda114d9c1a17b3c48))
* update version 6.0.6 ([fe2752f](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/fe2752f104406f62499b033796eb44df5f4a4932))
* update version 6.0.7 ([5043ada](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/5043ada0baf4f8ec1b92115e00fdcfbec9782c3a))
* update version 6.0.7 ([366b179](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/366b179870ecca7bcbb77a51ca12d6dd4b5e9e1e))
* update version and add rule ([02ac803](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/02ac803fe7094a876b72d97521889245e875c40a))
* use code vp9 by default ([c5e2b7d](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/c5e2b7de557b57380d3b39adc5cb04f6f6a363d1))
* use code vp9 by default ([e9977e1](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/e9977e12dddfd6a7f93f0f08dadfeaf675309541))
* using @fad-producto/ng-fad-videoagreement import ([f1fbe2a](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/f1fbe2aa1725d3c35d62df7c672c2897a09fd531))
* video mirror implementation ([63d858d](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/63d858de6b6065e7701ef4606268873bace8146f))
* video mirror implementation ([28fcbb8](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/28fcbb8852a9cfbad3721b45698238381f9ce5f8))
* videos size optimization ([66fd285](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/66fd2856dcb349d26d58c005dce5ba23f4e23281))
* videos size optimization ([cbb7d53](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/cbb7d536dc65ab708258f4c80e33d0f8424153ad))


### Bug Fixes

* add BrowserAnimationsModule to main module ([f43ff67](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/f43ff6755a0ca59dd45dbef46654bafc60e81f7e))
* add BrowserAnimationsModule to main module ([a8f9730](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/a8f9730b854f198d2e85a8e41da11665bfe12035))
* add flow android again ([02b4942](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/02b49428c68cda75a73ef944bb688f38f792e820))
* add flow android again ([2093a40](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/2093a400ef4cb3b40c3b0f593689bcbf89ae0614))
* allow old devices AudioContext ([3302d7e](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/3302d7e761ab931a6570647973db160fa2b1ca75))
* android 11 chrome freeze ([bce69aa](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/bce69aab605dd0838ec5f28a84dcbf97c8361344))
* android 11 chrome freeze ([f9dcace](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/f9dcace44e98183c1fdc7dea218ab822b1de0882))
* code-protection after camera accepted ([38fc8fd](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/38fc8fdb4f3d47af968172ae4a1935a9fdf17467))
* hide box whe face is undetected ([788a118](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/788a118399b0ad327b383c62e66890783e23fd18))
* hide box whe face is undetected ([5e9467b](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/5e9467b1371bccaee5a3c220103a6bdc321c519d))
* iOS 15 black screen ([ac054d2](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/ac054d228812d91b368ce138461353d9a00e2772))
* iOS 15 black screen ([f6aedc1](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/f6aedc1b03d96252ce034d4ca04be953e526d2e8))
* mediarecorder stop event in new context ([01c4c3b](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/01c4c3b41beeeed2cdc70f8d0ed3c800c6659bfc))
* mediarecorder stop event in new context ([4d9f846](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/4d9f84695d37468bc1e162ec369b97a1689665ef))
* projects/**/node_modules added to gitignore ([a3b6331](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/a3b63316e217b87e90c549baae8823f14e806322))
* projects/ng-fad-videoagreement/node_modules deleted ([606f78e](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/606f78e534e173952dbe62ea61d16f8e250f0e02))
* remove BrowserAnimationsModule from module ([89f430b](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/89f430b0f209c71db3f693bd35d2e3df8a645735))
* remove BrowserAnimationsModule from module ([15ebd31](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/15ebd31701b3eeeb2350ad8c0e451d5cd805ee03))
* stream.removeTrack removed ([4a71d40](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/4a71d4092d2149e4063148713e2f14c020133d83))
* stream.removeTrack removed ([d2609cd](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/d2609cd919823bb15649f92eb588c4c1d9255bb9))
* video object fit cover ([bfeb101](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/bfeb101c12c143c745bf650fb2c6ac092ee793d2))
* video object fit cover ([a5404a7](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/a5404a71b3dd5cf9a83e4fc0f8e2a7ac51122514))
* videoConstraints taken from moduleConfiguration ([2f1911b](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/2f1911bf06d6e90bae834c449583044d28a45c8c))
* videos cropped ([a3672e5](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/a3672e57caf6ede120aeac55924222df181e04bf))
* videos cropped ([afb3a31](https://na-at.xp-dev.com/git/FAD-VIDEOAGREEMENT/commit/afb3a314b950b2921ffe46e65466a75b7f8504f0))
