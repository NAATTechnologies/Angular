# FAD-VIDEO-PREVIEW Migration Details (CHANGELOG)

All notable changes to this project will be documented in this file. See [commit-and-tag-version](https://github.com/absolute-version/commit-and-tag-version) for commit guidelines.

## [4.1.3](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/compare/v4.1.3-alpha.0...v4.1.3) (2023-04-20)

### Changes
* No relevant changes since 4.1.3-alpha.0

## [4.1.3-alpha.0](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/compare/v4.1.2...v4.1.3-alpha.0) (2023-03-22)

### Changes

* internal @fad-producto/fad-common library updated to v3.0.0


## [4.1.2](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/compare/v4.1.1...v4.1.2) (2023-03-15)

### Bug Fixes

* internal @fad-producto/fad-common library updated to v2.1.1 to fix the mixes of mobile media properties between different @fad-producto libs when the customization object was modified

## [4.1.1](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/compare/v4.1.0...v4.1.1) (2023-03-08)

### Features
* internal @fad-producto/fad-common library updated to v2.1.0 with changes for color property in title, subtitle, content and informative text


## [4.1.0](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/compare/v4.1.0-alpha.4...v4.1.0) (2023-01-31)

### Bug Fixes 
* internal @fad-producto/fad-common library updated to v2.0.1 to set the default primary button border color to transparent
  

## [4.1.0-alpha.4](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/compare/v4.1.0-alpha.3...v4.1.0-alpha.4) (2023-01-19)

### Changes

* `document.body` as referenceElement

## [4.1.0-alpha.3](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/compare/v4.1.0-alpha.2...v4.1.0-alpha.3) (2023-01-19)

### Bug Fixes
  
* internal @fad-producto/fad-common library updated to v2.0.0-alpha.4 to fix the optional attributes
  
## [4.1.0-alpha.2](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/compare/v4.1.0-alpha.1...v4.1.0-alpha.2) (2023-01-19)


### Features

* Adds an internal referenceElement option as a parent HTML element that contains the CSS variables that should not be overwritten. ([ba74843](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/ba74843ba87fe2e251377f18b6036d85212e3d00))

## [4.1.0-alpha.1](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/compare/v4.0.3...v4.1.0-alpha.1) (2023-01-19)


### Features

* Respects a parent CSS variable when the variables has the `!important` attribute ([b928037](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/b92803702918329df95e46ce3ac793c2e5763f3f))

## [4.0.3](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/compare/v4.0.1...v4.0.3) (2022-11-10)

### Changes
* Readme updated

## [4.0.1](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/compare/v4.0.0...v4.0.1) (2022-10-27)

### Bug Fixes
* VideoPreviewConfiguration class removed; use IVideoPreviewConfiguration instead 

## [4.0.0](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/compare/v3.0.0...v4.0.0) (2022-10-24)

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

* secondary button default color ([9b140c5](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/9b140c5a88fdf9c78407f51686d0ab5b03637afd))

## [3.0.0](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/compare/v2.0.2...v3.0.0) (2022-10-12)


### ⚠ BREAKING CHANGES

* `Configuration` object is renamed to `IVideoPreviewConfiguration`
  
> Configuration input structure has been modified. The new interface to set the configuration of the module is `IVideoPreviewConfiguration`.
>
>Previous versions had a `Configuration` interface
> ``` ts
>  import { IVideoPreviewConfiguration } from '@fad-producto/ng-fad-video-preview';
>
> const configuration: IVideoPreviewConfiguration {
>  ...
> }
> ```
> For more details check the `IVideoPreviewConfiguration` interface

### Features

* fad-loader ([03bac68](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/03bac6886ca122a75f3cd8154bfee2fbf584e26b))
* moduleConfiguration classes removed ([be8d7e2](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/be8d7e2f3a2bb51247a5482b43753242983e0507))

* new configuration object ([1a4c67a](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/1a4c67a01695de6f72eaa5c88a97336951ce46a7))
  

* add fad common and rectructuration ([1c62eaf](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/1c62eaf2a015d44612c065a7f3860a17ac875856))
* add legends of buttons like inputs ([d4fd77c](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/d4fd77c0075c6f4280886192b3ba618b9a77da82))
* add object-fit: cover to video style ([94b79d7](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/94b79d7068f799b6387060a2e32efc61c15e8a18))
* add onended and iOS poster preview ([b72a8d0](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/b72a8d019d4c4138bcf1da96f2c8a52428912f75))
* add tertiary variable css ([3b4f313](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/3b4f313847144dff4331f3807b1178db6f959e2f))


* preview with video signature ([f5f02a3](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/f5f02a33d38788081541b00d5c75ca21e4d4582a))
* remove general style button ([c2825ac](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/c2825ac79a41c5ed202978afe9b04bb1d5d254ca))
* removing variables css on exit ([10e9de3](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/10e9de3c19cab25bc83f96bcc888305e97f51638))
* show last frame to the end ([c098578](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/c098578cf83b3aa7585b575334e9d24a127cccde))
* style container title ([bd9fa5c](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/bd9fa5c53fbc4efaee5b0a0cb6d13d3b687fd521))
* vallidation blob size mayor to zero ([f65d7de](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/f65d7decec7acd75af7719eb27f54e92953c3cb7))
* video full screen ([07a81a0](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/07a81a0bc88b2a9b5e46ebeea5c06e7a03931871))
* video full screen and safeUrl ([f4aadf0](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/f4aadf0e39d662a395cd3cf719707d497465c0f0))

### Bug Fixes

* init muted videos ([776a10d](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/776a10d5bbef0173226fee05d2f45bfc1e0b23e6))
  
* adjust view to ipad preview ([e0417cb](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/e0417cbfe3ad72336706d9d49ca21627a539b700))
* controls in screen's size greater than 600px centered ([ef09cf0](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/ef09cf012e1711c693ffb4bd09183c02f7ec355e))
* iOS duration round and autoplay ([73fc3e5](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/73fc3e5de76d3c5bc964ec9eced5ed8ce70fe33a))
* iOS/Android autoplay variable ([7cbbc9f](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/7cbbc9f84021f1e58c34b5bc1b5420a1a846154d))
* autoplay via typescript ([fab496e](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/fab496eb96b276e512abd8d58a3278fcd3f339eb))
* video controls and pointer-events removed ([8d8bde4](https://na-at.xp-dev.com/git/FAD-VIDEO-PREVIEW/commit/8d8bde4ffd17f75695e3e04e6287041fe05dbf8b))

