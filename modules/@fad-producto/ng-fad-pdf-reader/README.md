# Getting started

## Installation

```
npm i @fad-producto/ng-fad-pdf-reader
```

# Usage


## Add

In assets of angular.json file add

```json
"assets": [
.
.
.
    {
      "glob": "**/*",
      "input": "node_modules/ng-fad-pdf-reader/assets",
      "output": "/assets/"
    }
.
.
.
```


## Import

In the necessary file *example.component.ts* import the service.


## Typescript

``` ts
  import { NgFadPdfReaderService, ResponseError, ResponseSuccess } from '@fad-producto/ng-fad-pdf-reader';
  .
  .
  .

  @Component({
    .
    .
    .
    providers: [NgFadPdfReaderService]
  })
  
  .
  .
  .

  constructor(private pdf: NgFadPdfReaderService) { }

  ngOnInit() {   
    // 1.- Observe if module has error
    this.pdf.verifyErrorPdf.subscribe((res: ResponseError) => {
      console.log(res);
    });

    // 2.- Observe pdf pages response
    this.pdf.pages.subscribe((res: ResponseSuccess) => {
      console.log(res);
      this.pages.push(res);
    });

    // 3.- initialize pdf reader
    this.pdf.initialize('you pdf src');
  }

```
