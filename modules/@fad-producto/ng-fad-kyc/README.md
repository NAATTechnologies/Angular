# Getting started

## Installation

``` bash
npm install @fad-producto/ng-fad-kyc
```

## Update
``` bash
npm install @fad-producto/ng-fad-kyc@latest
```

## Import

In the file necessary *example.module.ts* import the module.

In this case  *app.module.ts*

``` ts
import { NgFadKYCModule } from '@fad-producto/ng-fad-kyc';
.
.
.
... imports: [
       ...,
       BrowserAnimationsModule 
       NgFadKYCModule
    ]...
```

# Usage

## HTML


Add the selector inside some component and configure the output events:


``` html
<ng-fad-kyc
  [configuration]="configuration"
  [questions]="questions"
  (onerror)="onerror($event)"
  (oncomplete)="oncomplete($event)">
</ng-fad-kyc>
```

## Typescript 

Listen to the events:

``` ts
import { CONFIGURATION_DEFAULT, Credentials, IKycConfiguration, Questionnaire, ResponseError, ResponseSuccess } from '@fad-producto/ng-fad-kyc';
.
.
.

public configuration: IKycConfiguration = {
  credentials: {
    baseURL: 'https://your_enviroment/',
    idProductScript: 'uuid-uuid-uuid-uuid',
    user: {
      password: 'sha256_password',
      username: 'email@email.com.mx'
    }
  }
};

questions: Questionnaire[];

oncomplete(result: ResponseSuccess) {
  console.log(result)
}

onerror(error: ResponseError) {
   alert(JSON.stringify(error));
}

```



# Inputs


| Name           | Required   | Default                                 |  Type                  | Description                                            |
| -------------- | ---------- | --------------------------------------- | ---------------------- | ------------------------------------------------------ |
| configuration  |   false    |  CONFIGURATION_DEFAULT                  | IKycConfiguration      | Configuration module                                   |
| questionnaire  |   false    |  undefined                              | Questionnaire          | Questions that will be displayed on the screen         |


## IKycConfiguration
The following properties are for a more specific configuration of the module

| Name                | Type                       |  Required  | Default                   | Description                                                |
| ------------------- | -------------------------- | ---------- |-------------------------- | ---------------------------------------------------------- |
| credentials         | Credentials                |  false     | undefined                 | Data that is needed for the module to internally obtain the questions. This would not be executed if the input "questions" has some value   |
| changeQuestionTime  | number                |  false     | 750                 |  Waiting time between each question change   |


# Outputs

| Name        | Return          | Description                                  |
| ----------- | --------------- | -------------------------------------------- |
| oncomplete  | ResponseSuccess | Fires when the questionary ends successfully |
| onerror     | ResponseError   | Is called when an error happens              |
