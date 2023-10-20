# Getting started

## Installation

``` bash
npm install @fad-producto/fad-services
```

## Update
``` bash
npm install @fad-producto/fad-services@latest
```

# Usage

By default, all the request uses the UAT environments. For send the request to a different environment (uat, uatha, production) set the specific environment through the options paramenter

## Authorization server
### Authentication / Authorization (Login)

``` ts
import {login} from '@fad-producto/fad-services';

const USER = {
	username: 'username', 
	password: 'sha256-password'
}

const token = await login(USER, options);
```

> For more details check the function definition


## Middleware
### Get third party info

``` ts
import {getThirdPartyInfo, MiddlewarePlatform} from '@fad-producto/fad-services';

const middlewareResponse: MiddlewareResponse<T> = await getThirdPartyInfo<T>(
	{
		module: 'Face',
		provider: 'FaceTec',
		platform: MiddlewarePlatform.WEB,
		app: 'fadweb',
		version: '1'
	}, 
	'token', 
	options);
```

> For more details check the function definition

## Advanced functions
### Facetec credentials

``` ts
import {getFacetecCredentials, AdditionaInfoProcessType, MiddlewarePlatform, Environment} from '@fad-producto/fad-services';

const facetecCredentials = await getFacetecCredentials(
	'fadweb', 
	{
		processId: '',
  	processTypeId: AdditionaInfoProcessType.SIGNATURE
	},
	{
		token: 'eyJjdHkiOiJKV1QiLCJlbmMiOi...',
		// user: {
		//	username: 'someuser',
		//	password: 'sha256-password'
		// }
	}, 
	{ 
		environment: Environment.UAT
	}
);
```

> For more details check the function definition
> FadCredentials can be the token string or an user-password pair 

---
### RequestOptions

All the funcions contains an options parameter with custom values that will be used in the request. These options are described below.
- environment: An environment constant to determine which urls will be used in all the internal requests of a function.