# IO.Swagger - the C# library for the The SMS Works API

The SMS Works provides a low-cost, reliable SMS API for developers. Pay only for delivered texts, all failed messages are refunded.

This C# SDK is automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen) project:

- API version: 1.3.0
- SDK version: 1.0.4
- Build package: io.swagger.codegen.v3.generators.dotnet.CSharpClientCodegen

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

Then include the DLL (under the `bin` folder) in the C# project, and use the namespaces:
```csharp
using IO.Swagger.Api;
using IO.Swagger.Client;
using IO.Swagger.Model;
```
<a name="packaging"></a>
## Packaging

A `.nuspec` is included with the project. You can follow the Nuget quickstart to [create](https://docs.microsoft.com/en-us/nuget/quickstart/create-and-publish-a-package#create-the-package) and [publish](https://docs.microsoft.com/en-us/nuget/quickstart/create-and-publish-a-package#publish-the-package) packages.

This `.nuspec` uses placeholders from the `.csproj`, so build the `.csproj` directly:

```
nuget pack -Build -OutputDirectory out IO.Swagger.csproj
```

Then, publish to a [local feed](https://docs.microsoft.com/en-us/nuget/hosting-packages/local-feeds) or [other host](https://docs.microsoft.com/en-us/nuget/hosting-packages/overview) and consume the new package via Nuget as usual.

<a name="getting-started"></a>
## Getting Started

```csharp
using System;
using System.Diagnostics;
using IO.Swagger.Api;
using IO.Swagger.Client;
using IO.Swagger.Model;

namespace Example
{
    public class Example
    {
        public void main()
        {
            var apiInstance = new AuthApi();
            var customerid = customerid_example;  // string | Utility method. Please generate your API key by following the instructions on your account page at https://thesmsworks.co.uk/user/login

            try
            {
                ApiKeyResponse result = apiInstance.KeySecret(customerid);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling AuthApi.KeySecret: " + e.Message );
            }
        }
    }
}
```

<a name="documentation-for-api-endpoints"></a>
## Documentation for API Endpoints

All URIs are relative to *https://api.thesmsworks.co.uk/v1*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AuthApi* | [**KeySecret**](docs/AuthApi.md#keysecret) | **GET** /auth/getApiKey |
*AuthApi* | [**Login**](docs/AuthApi.md#login) | **POST** /auth/token |
*BatchMessagesApi* | [**CancelScheduledBatchJob**](docs/BatchMessagesApi.md#cancelscheduledbatchjob) | **DELETE** /batches/schedule/{batchid} |
*BatchMessagesApi* | [**GetBatchById**](docs/BatchMessagesApi.md#getbatchbyid) | **GET** /batch/{batchid} |
*BatchMessagesApi* | [**ScheduleBatch**](docs/BatchMessagesApi.md#schedulebatch) | **POST** /batch/schedule |
*BatchMessagesApi* | [**SendBatch**](docs/BatchMessagesApi.md#sendbatch) | **POST** /batch/send |
*CreditsApi* | [**Credits**](docs/CreditsApi.md#credits) | **GET** /credits/balance |
*MessagesApi* | [**CancelScheduledJob**](docs/MessagesApi.md#cancelscheduledjob) | **DELETE** /messages/schedule/{messageid} |
*MessagesApi* | [**GetInboxMessages**](docs/MessagesApi.md#getinboxmessages) | **POST** /messages/inbox |
*MessagesApi* | [**GetMessageById**](docs/MessagesApi.md#getmessagebyid) | **GET** /messages/{messageid} |
*MessagesApi* | [**GetMessages**](docs/MessagesApi.md#getmessages) | **POST** /messages |
*MessagesApi* | [**ScheduleMessage**](docs/MessagesApi.md#schedulemessage) | **POST** /message/schedule |
*MessagesApi* | [**SendMessage**](docs/MessagesApi.md#sendmessage) | **POST** /message/send |
*UtilsApi* | [**GetError**](docs/UtilsApi.md#geterror) | **GET** /utils/errors/{errorcode} |
*UtilsApi* | [**Test**](docs/UtilsApi.md#test) | **GET** /utils/test |

<a name="documentation-for-models"></a>
## Documentation for Models

 - [Model.ApiKeyResponse](docs/ApiKeyResponse.md)
 - [Model.BatchMessage](docs/BatchMessage.md)
 - [Model.BatchMessageResponse](docs/BatchMessageResponse.md)
 - [Model.CancelledMessageResponse](docs/CancelledMessageResponse.md)
 - [Model.CreditsResponse](docs/CreditsResponse.md)
 - [Model.ErrorModel](docs/ErrorModel.md)
 - [Model.ExtendedErrorModel](docs/ExtendedErrorModel.md)
 - [Model.Login](docs/Login.md)
 - [Model.Message](docs/Message.md)
 - [Model.MessageResponse](docs/MessageResponse.md)
 - [Model.MetaData](docs/MetaData.md)
 - [Model.Query](docs/Query.md)
 - [Model.ScheduledBatchResponse](docs/ScheduledBatchResponse.md)
 - [Model.ScheduledMessageResponse](docs/ScheduledMessageResponse.md)
 - [Model.SendMessageResponse](docs/SendMessageResponse.md)
 - [Model.TestResponse](docs/TestResponse.md)
 - [Model.TokenResponse](docs/TokenResponse.md)

<a name="documentation-for-authorization"></a>
## Documentation for Authorization

<a name="JWT"></a>
### JWT

- **Type**: API key
- **API key parameter name**: Authorization
- **Location**: HTTP header
