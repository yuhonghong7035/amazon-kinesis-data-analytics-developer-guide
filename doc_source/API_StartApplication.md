# StartApplication<a name="API_StartApplication"></a>

Starts the specified Amazon Kinesis Analytics application\. After creating an application, you must exclusively call this operation to start your application\.

After the application starts, it begins consuming the input data, processes it, and writes the output to the configured destination\.

 The application status must be `READY` for you to start an application\. You can get the application status in the console or using the [DescribeApplication](API_DescribeApplication.md) operation\.

After you start the application, you can stop the application from processing the input by calling the [StopApplication](API_StopApplication.md) operation\.

This operation requires permissions to perform the `kinesisanalytics:StartApplication` action\.

## Request Syntax<a name="API_StartApplication_RequestSyntax"></a>

```
{
   "[ApplicationName](#analytics-StartApplication-request-ApplicationName)": "string",
   "[InputConfigurations](#analytics-StartApplication-request-InputConfigurations)": [ 
      { 
         "[Id](API_InputConfiguration.md#analytics-Type-InputConfiguration-Id)": "string",
         "[InputStartingPositionConfiguration](API_InputConfiguration.md#analytics-Type-InputConfiguration-InputStartingPositionConfiguration)": { 
            "[InputStartingPosition](API_InputStartingPositionConfiguration.md#analytics-Type-InputStartingPositionConfiguration-InputStartingPosition)": "string"
         }
      }
   ]
}
```

## Request Parameters<a name="API_StartApplication_RequestParameters"></a>

The request accepts the following data in JSON format\.

 ** [ApplicationName](#API_StartApplication_RequestSyntax) **   <a name="analytics-StartApplication-request-ApplicationName"></a>
Name of the application\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 128\.  
Pattern: `[a-zA-Z0-9_.-]+`   
Required: Yes

 ** [InputConfigurations](#API_StartApplication_RequestSyntax) **   <a name="analytics-StartApplication-request-InputConfigurations"></a>
Identifies the specific input, by ID, that the application starts consuming\. Amazon Kinesis Analytics starts reading the streaming source associated with the input\. You can also specify where in the streaming source you want Amazon Kinesis Analytics to start reading\.  
Type: Array of [InputConfiguration](API_InputConfiguration.md) objects  
Required: Yes

## Response Elements<a name="API_StartApplication_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response with an empty HTTP body\.

## Errors<a name="API_StartApplication_Errors"></a>

 **InvalidApplicationConfigurationException**   
User\-provided application configuration is not valid\.  
HTTP Status Code: 400

 **InvalidArgumentException**   
Specified input parameter value is invalid\.  
HTTP Status Code: 400

 **ResourceInUseException**   
Application is not available for this operation\.  
HTTP Status Code: 400

 **ResourceNotFoundException**   
Specified application can't be found\.  
HTTP Status Code: 400

 **UnsupportedOperationException**   
HTTP Status Code: 400

## See Also<a name="API_StartApplication_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/kinesisanalytics-2015-08-14/StartApplication) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/kinesisanalytics-2015-08-14/StartApplication) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/kinesisanalytics-2015-08-14/StartApplication) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/kinesisanalytics-2015-08-14/StartApplication) 
+  [AWS SDK for Java](https://docs.aws.amazon.com/goto/SdkForJava/kinesisanalytics-2015-08-14/StartApplication) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/kinesisanalytics-2015-08-14/StartApplication) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/kinesisanalytics-2015-08-14/StartApplication) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/kinesisanalytics-2015-08-14/StartApplication) 
+  [AWS SDK for Ruby V2](https://docs.aws.amazon.com/goto/SdkForRubyV2/kinesisanalytics-2015-08-14/StartApplication) 