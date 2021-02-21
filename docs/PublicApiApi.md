# BtApiClient.Api.PublicApiApi

All URIs are relative to *https://app.behtime.ir*

Method | HTTP request | Description
------------- | ------------- | -------------
[**PublicApiAddTask**](PublicApiApi.md#publicapiaddtask) | **POST** /papi/addTask | Add a task
[**PublicApiAuthenticate**](PublicApiApi.md#publicapiauthenticate) | **POST** /papi/authenticate | Authenticate user and Generate a token to be used with other api calls
[**PublicApiGetProjectTasks**](PublicApiApi.md#publicapigetprojecttasks) | **POST** /papi/projectTasks | Get Project Tasks
[**PublicApiGetProjects**](PublicApiApi.md#publicapigetprojects) | **POST** /papi/projects | Get All Projects that the user has access
[**PublicApiGetTaskCategories**](PublicApiApi.md#publicapigettaskcategories) | **POST** /papi/taskcategories | Get Task Categories
[**PublicApiGetUsers**](PublicApiApi.md#publicapigetusers) | **POST** /papi/users | Get All Users


<a name="publicapiaddtask"></a>
# **PublicApiAddTask**
> ApiSingleResultApiTaskModel PublicApiAddTask (string token, ApiAddTaskViewModel taskData, string usersAssigned = null)

Add a task

### Example
```csharp
using System;
using System.Diagnostics;
using BtApiClient.Api;
using BtApiClient.Client;
using BtApiClient.Model;

namespace Example
{
    public class PublicApiAddTaskExample
    {
        public void main()
        {
            var apiInstance = new PublicApiApi();
            var token = token_example;  // string | 
            var taskData = new ApiAddTaskViewModel(); // ApiAddTaskViewModel | task data
            var usersAssigned = usersAssigned_example;  // string | comma separated userIds like 1,22,2005 (optional) 

            try
            {
                // Add a task
                ApiSingleResultApiTaskModel result = apiInstance.PublicApiAddTask(token, taskData, usersAssigned);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling PublicApiApi.PublicApiAddTask: " + e.Message );
            }
        }
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **token** | **string**|  | 
 **taskData** | [**ApiAddTaskViewModel**](ApiAddTaskViewModel.md)| task data | 
 **usersAssigned** | **string**| comma separated userIds like 1,22,2005 | [optional] 

### Return type

[**ApiSingleResultApiTaskModel**](ApiSingleResultApiTaskModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json, application/xml, text/xml

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a name="publicapiauthenticate"></a>
# **PublicApiAuthenticate**
> PublicApiAuthenticateResult PublicApiAuthenticate (string username, string password, Object clientInfo, string clientLanguage = null, string oldToken = null)

Authenticate user and Generate a token to be used with other api calls

### Example
```csharp
using System;
using System.Diagnostics;
using BtApiClient.Api;
using BtApiClient.Client;
using BtApiClient.Model;

namespace Example
{
    public class PublicApiAuthenticateExample
    {
        public void main()
        {
            var apiInstance = new PublicApiApi();
            var username = username_example;  // string | UserName
            var password = password_example;  // string | Password
            var clientInfo = ;  // Object | a dictionary (or json object) like information of client. could be {}
            var clientLanguage = clientLanguage_example;  // string | could be fa,en (optional) 
            var oldToken = oldToken_example;  // string | old token to be renewed (optional) 

            try
            {
                // Authenticate user and Generate a token to be used with other api calls
                PublicApiAuthenticateResult result = apiInstance.PublicApiAuthenticate(username, password, clientInfo, clientLanguage, oldToken);
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

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **username** | **string**| UserName | 
 **password** | **string**| Password | 
 **clientInfo** | **Object**| a dictionary (or json object) like information of client. could be {} | 
 **clientLanguage** | **string**| could be fa,en | [optional] 
 **oldToken** | **string**| old token to be renewed | [optional] 

### Return type

[**PublicApiAuthenticateResult**](PublicApiAuthenticateResult.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json, application/xml, text/xml

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a name="publicapigetprojecttasks"></a>
# **PublicApiGetProjectTasks**
> ApiListResultApiTaskModel PublicApiGetProjectTasks (string token, long? projectId = null, string searchTitle = null)

Get Project Tasks

### Example
```csharp
using System;
using System.Diagnostics;
using BtApiClient.Api;
using BtApiClient.Client;
using BtApiClient.Model;

namespace Example
{
    public class PublicApiGetProjectTasksExample
    {
        public void main()
        {
            var apiInstance = new PublicApiApi();
            var token = token_example;  // string | 
            var projectId = 789;  // long? |  (optional) 
            var searchTitle = searchTitle_example;  // string |  (optional) 

            try
            {
                // Get Project Tasks
                ApiListResultApiTaskModel result = apiInstance.PublicApiGetProjectTasks(token, projectId, searchTitle);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling PublicApiApi.PublicApiGetProjectTasks: " + e.Message );
            }
        }
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **token** | **string**|  | 
 **projectId** | **long?**|  | [optional] 
 **searchTitle** | **string**|  | [optional] 

### Return type

[**ApiListResultApiTaskModel**](ApiListResultApiTaskModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, application/xml, text/xml

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a name="publicapigetprojects"></a>
# **PublicApiGetProjects**
> ApiListResultApiProjectModel PublicApiGetProjects (string token, int? startIndex, int? pageSize, string searchTitle = null, bool? onlyActive = null)

Get All Projects that the user has access

### Example
```csharp
using System;
using System.Diagnostics;
using BtApiClient.Api;
using BtApiClient.Client;
using BtApiClient.Model;

namespace Example
{
    public class PublicApiGetProjectsExample
    {
        public void main()
        {
            var apiInstance = new PublicApiApi();
            var token = token_example;  // string | 
            var startIndex = 56;  // int? | it is used for paging. could be 0 to start from first
            var pageSize = 56;  // int? | should be greater than 0
            var searchTitle = searchTitle_example;  // string |  (optional) 
            var onlyActive = true;  // bool? |  (optional) 

            try
            {
                // Get All Projects that the user has access
                ApiListResultApiProjectModel result = apiInstance.PublicApiGetProjects(token, startIndex, pageSize, searchTitle, onlyActive);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling PublicApiApi.PublicApiGetProjects: " + e.Message );
            }
        }
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **token** | **string**|  | 
 **startIndex** | **int?**| it is used for paging. could be 0 to start from first | 
 **pageSize** | **int?**| should be greater than 0 | 
 **searchTitle** | **string**|  | [optional] 
 **onlyActive** | **bool?**|  | [optional] 

### Return type

[**ApiListResultApiProjectModel**](ApiListResultApiProjectModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, application/xml, text/xml

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a name="publicapigettaskcategories"></a>
# **PublicApiGetTaskCategories**
> ApiListResultTaskCategoryViewModel PublicApiGetTaskCategories (string token, int? startIndex, int? pageSize, string searchTitle = null, long? projectId = null)

Get Task Categories

### Example
```csharp
using System;
using System.Diagnostics;
using BtApiClient.Api;
using BtApiClient.Client;
using BtApiClient.Model;

namespace Example
{
    public class PublicApiGetTaskCategoriesExample
    {
        public void main()
        {
            var apiInstance = new PublicApiApi();
            var token = token_example;  // string | 
            var startIndex = 56;  // int? | It is used for paging. could be 0 to start from first
            var pageSize = 56;  // int? | Should be greater than 0
            var searchTitle = searchTitle_example;  // string |  (optional) 
            var projectId = 789;  // long? | If this parameter is specified, only task categories of this project will be returned (optional) 

            try
            {
                // Get Task Categories
                ApiListResultTaskCategoryViewModel result = apiInstance.PublicApiGetTaskCategories(token, startIndex, pageSize, searchTitle, projectId);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling PublicApiApi.PublicApiGetTaskCategories: " + e.Message );
            }
        }
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **token** | **string**|  | 
 **startIndex** | **int?**| It is used for paging. could be 0 to start from first | 
 **pageSize** | **int?**| Should be greater than 0 | 
 **searchTitle** | **string**|  | [optional] 
 **projectId** | **long?**| If this parameter is specified, only task categories of this project will be returned | [optional] 

### Return type

[**ApiListResultTaskCategoryViewModel**](ApiListResultTaskCategoryViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, application/xml, text/xml

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a name="publicapigetusers"></a>
# **PublicApiGetUsers**
> ApiListResultApiUserModel PublicApiGetUsers (string token, int? startIndex, int? pageSize, string searchTitle = null)

Get All Users

### Example
```csharp
using System;
using System.Diagnostics;
using BtApiClient.Api;
using BtApiClient.Client;
using BtApiClient.Model;

namespace Example
{
    public class PublicApiGetUsersExample
    {
        public void main()
        {
            var apiInstance = new PublicApiApi();
            var token = token_example;  // string | 
            var startIndex = 56;  // int? | It is used for paging. could be 0 to start from first
            var pageSize = 56;  // int? | Should be greater than 0
            var searchTitle = searchTitle_example;  // string |  (optional) 

            try
            {
                // Get All Users
                ApiListResultApiUserModel result = apiInstance.PublicApiGetUsers(token, startIndex, pageSize, searchTitle);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling PublicApiApi.PublicApiGetUsers: " + e.Message );
            }
        }
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **token** | **string**|  | 
 **startIndex** | **int?**| It is used for paging. could be 0 to start from first | 
 **pageSize** | **int?**| Should be greater than 0 | 
 **searchTitle** | **string**|  | [optional] 

### Return type

[**ApiListResultApiUserModel**](ApiListResultApiUserModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, application/xml, text/xml

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

