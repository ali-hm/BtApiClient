# BtApiClient - the C# library for the behTIME Public API

project:

- API version: v1
- SDK version: 1.0.0
- Build package: io.swagger.codegen.languages.CSharpClientCodegen

<a name="frameworks-supported"></a>
## Frameworks supported
- .NET 4.0 or later
- Windows Phone 7.1 (Mango)

<a name="dependencies"></a>
## Dependencies
- [RestSharp](https://www.nuget.org/packages/RestSharp) - 105.1.0 or later
- [Json.NET](https://www.nuget.org/packages/Newtonsoft.Json/) - 7.0.0 or later
- [JsonSubTypes](https://www.nuget.org/packages/JsonSubTypes/) - 1.2.0 or later

The DLLs included in the package may not be the latest version. We recommend using [NuGet](https://docs.nuget.org/consume/installing-nuget) to obtain the latest version of the packages:
```
Install-Package RestSharp
Install-Package Newtonsoft.Json
Install-Package JsonSubTypes
```

NOTE: RestSharp versions greater than 105.1.0 have a bug which causes file uploads to fail. See [RestSharp#742](https://github.com/restsharp/RestSharp/issues/742)

<a name="installation"></a>
## Installation
Run the following command to generate the DLL
- [Mac/Linux] `/bin/sh build.sh`
- [Windows] `build.bat`

Then include the DLL (under the `bin` folder) in the C# project, 
Or Use the DLLs in the bin.zip package of release 
and use the namespaces:
```csharp
using BtApiClient.Api;
using BtApiClient.Client;
using BtApiClient.Model;
```
<a name="getting-started"></a>
## Getting Started
To Use each method you should get a token using **PublicApiAuthenticate**(docs/PublicApiApi.md#publicapiauthenticate) method


```csharp
using System;
using System.Diagnostics;
using BtApiClient.Api;
using BtApiClient.Client;
using BtApiClient.Model;

namespace Example
{
    public class Example
    {
        public void main()
        {

            var apiInstance = new PublicApiApi();
            var username = "SampleUsername";  // string | UserName
            var password = "SamplePassword";  // string | Password
            var clientInfo = null;  // Object | a dictionary (or json object) like information of client. could be {}
            var clientLanguage = "fa";  // string | could be fa,en (optional) 
            var oldToken = null;  // string | old token to be renewed (optional) 

            try
            {
                // Authenticate user and Generate a token to be used with other api calls
                PublicApiAuthenticateResult result = apiInstance.PublicApiAuthenticate(username, password, clientInfo, clientLanguage, oldToken);
                Debug.WriteLine(result);

                // Get All Projects that the user has access
                var token = result.Token;  // string | 
                var startIndex = 0;  // int? | it is used for paging. could be 0 to start from first
                var pageSize = 50;  // int? | should be greater than 0
                var searchTitle = null;  // string |  (optional) 
                var onlyActive = true;  // bool? |  (optional) 

                
                ApiListResultApiProjectModel result = apiInstance.PublicApiGetProjects(token, startIndex, pageSize, searchTitle, onlyActive);
                Debug.WriteLine(result);

            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling PublicApiApi.PublicApiAuthenticate: " + e.Message );
            }

        }
    }
}
```

<a name="documentation-for-api-endpoints"></a>
## Documentation for API Endpoints

All URIs are relative to *https://app.behtime.ir*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*PublicApiApi* | [**PublicApiAddTask**](docs/PublicApiApi.md#publicapiaddtask) | **POST** /papi/addTask | Add a task
*PublicApiApi* | [**PublicApiAuthenticate**](docs/PublicApiApi.md#publicapiauthenticate) | **POST** /papi/authenticate | Authenticate user and Generate a token to be used with other api calls
*PublicApiApi* | [**PublicApiGetProjectTasks**](docs/PublicApiApi.md#publicapigetprojecttasks) | **POST** /papi/projectTasks | Get Project Tasks
*PublicApiApi* | [**PublicApiGetProjects**](docs/PublicApiApi.md#publicapigetprojects) | **POST** /papi/projects | Get All Projects that the user has access
*PublicApiApi* | [**PublicApiGetTaskCategories**](docs/PublicApiApi.md#publicapigettaskcategories) | **POST** /papi/taskcategories | Get Task Categories
*PublicApiApi* | [**PublicApiGetUsers**](docs/PublicApiApi.md#publicapigetusers) | **POST** /papi/users | Get All Users


<a name="documentation-for-models"></a>
## Documentation for Models

 - [Model.ApiAddTaskViewModel](docs/ApiAddTaskViewModel.md)
 - [Model.ApiListResultApiProjectModel](docs/ApiListResultApiProjectModel.md)
 - [Model.ApiListResultApiTaskModel](docs/ApiListResultApiTaskModel.md)
 - [Model.ApiListResultApiUserModel](docs/ApiListResultApiUserModel.md)
 - [Model.ApiListResultTaskCategoryViewModel](docs/ApiListResultTaskCategoryViewModel.md)
 - [Model.ApiProjectModel](docs/ApiProjectModel.md)
 - [Model.ApiSingleResultApiTaskModel](docs/ApiSingleResultApiTaskModel.md)
 - [Model.ApiTaskModel](docs/ApiTaskModel.md)
 - [Model.ApiUserModel](docs/ApiUserModel.md)
 - [Model.PublicApiAuthenticateResult](docs/PublicApiAuthenticateResult.md)
 - [Model.PublicApiUserInfo](docs/PublicApiUserInfo.md)
 - [Model.TaskCategoryViewModel](docs/TaskCategoryViewModel.md)


<a name="documentation-for-authorization"></a>
## Documentation for Authorization

All endpoints do not require authorization.
