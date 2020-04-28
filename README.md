# serverless-now
* AWS Serverless (Lambda) function that interacts with UoA ServiceNow.
* Supports unit testing and debugging with vs code

## Setup

Install Serverless Framework globally
```
npm install -g serverless
```

Install NPM modules
```
npm install
```

Obtain temporary AWS credentials for UoA account:
[AWS Temporary Credentials for CLI](https://wiki.auckland.ac.nz/pages/viewpage.action?spaceKey=UC&title=AWS+Temporary+Credentials+for+CLI)

## Run locally
* To run the tsts locally simply execute:
```
npm start
```

## Debug Locally
* Inside Visual Studio Code hit `F5` and select `Debug` as config file. Attach breakpoints as desired.

## Test
* To run all unit tests once simply execute:
```
npm test
```
### Test and watch for changes
* To run all unit tests and have them watch your files for changes:
```
npm run testw
```

## Deploy to AWS
* To deploy to AWS execute (**note**: will only deploy after all unit tests have passed):
```
npm run deploy
```

### Deploy to a different stage
* By default the above command deploys to the `dev` stage
* You can optionally pass a `-- --stage STAGE_NAME` flag (**note the extra `--`**)
```
npm run deploy -- --stage=test
```

## Get info about existing deployment
* To get information about the currently deployed endpoints, region, stage, layers etc execute:
```
sls info
```

## Invoke a deployed Lambda function running on AWS
```
sls invoke -f serverless-now
```

## Resources
* For general Serverless Framework help run: `sls help`
* [Serverless Mocha Plugin](https://www.npmjs.com/package/serverless-mocha-plugin)
