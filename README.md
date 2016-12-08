# Azure Application Insights
Azure Application Insights is a service that can help your team gain insights into the usage, reliability and performance of your live Node.js Express applications.

[Learn about Azure Application Insights](https://azure.microsoft.com/en-us/services/application-insights/ "Documentation")

The Application Insights extension for Visual Studio Code brings information from your production services right into your code editor to help you find and fix issues faster.

## Features
### Request data in CodeLens
Three request metrics are available in CodeLens in Visual Studio Code. Each shows data from the last 24 hours as measured by the Application Insights resource you set up with Visual Studio Code:
* **Total Requests** - Number of requests made to this route
* **Failed Request** - Number of failed requests to this route
* **Average Response Times** - Average response time for requests made to this route.

![Example of request CodeLens functionality](https://aidevtools.blob.core.windows.net/vscode-assets/codelens.gif)

## Getting started with Express and Application Insights
### Install the Express generator and create an app
```
$ npm install express-generator -g
$ express mywebapp
$ cd mywebbapp && npm install
```
[Learn about using the Express generator](http://expressjs.com/en/starter/generator.html)

### Add the Application Insights package
```
$ npm install applicationinsights --save
```

### Add an Application Insights Instrumentation Key
Your app needs an Application Insights resource in Azure where it will send telemetry. [Create an Application Insights resource](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource) in the Azure Portal. Application Insights resources are free for the first gigabyte of data per month.  

```
$ code .
```
Add this code snippet at the beginning of app.js. 
```javascript
var appInsights = require("applicationinsights");
appInsights.setup("<instrumentation_key>").start();
```
Make sure to replace *&lt;instrumentation key&gt;* with your actual Application Insights instrumentation key from the Essentials section at the top of the Overview blade for your Application Insights resource in the Azure Portal.

## Setup Visual Studio Code to see CodeLens for requests
### Choose an Application Insights resource
Select the Application Insights resource you'd like to see data from in CodeLens.

`Ctrl + Shift + P ->  "Application Insights: Choose CodeLens resource"`

![How to select a resource](https://aidevtools.blob.core.windows.net/vscode-assets/selectresource.gif)

### See CodeLens on request definitions
![Example of request CodeLens functionality](https://aidevtools.blob.core.windows.net/vscode-assets/codelens.gif)

Click on the CodeLens indicator to see more details.

## Release Notes
### Version 0.1.0
Support CodeLens with request statistics for Node.js Express applications.

## Feedback
In order to report bugs or provide general feedback please visit our repository's [Issues](https://github.com/Microsoft/applicationinsights-vscode/issues) page.

## Privacy Statement
The [Microsoft Online Services Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=512156) describes the privacy statement of this software.

## License
The extension is made available under the [Microsoft Software License Terms](https://github.com/Microsoft/applicationinsights-vscode/blob/master/LICENSE). Please see the [third-party notices](https://github.com/Microsoft/applicationinsights-vscode/blob/master/ThirdPartyNotices.txt) file for additional copyright notices and license terms applicable to portions of the software.