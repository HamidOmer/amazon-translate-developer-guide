# GetTerminology<a name="API_GetTerminology"></a>

## Request Syntax<a name="API_GetTerminology_RequestSyntax"></a>

```
{
   "[Name](#Translate-GetTerminology-request-Name)": "string",
   "[TerminologyDataFormat](#Translate-GetTerminology-request-TerminologyDataFormat)": "string"
}
```

## Request Parameters<a name="API_GetTerminology_RequestParameters"></a>

For information about the parameters that are common to all actions, see [Common Parameters](CommonParameters.md)\.

The request accepts the following data in JSON format\.

 ** [Name](#API_GetTerminology_RequestSyntax) **   <a name="Translate-GetTerminology-request-Name"></a>
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 256\.  
Pattern: `^([A-Za-z0-9-]_?)+$`   
Required: Yes

 ** [TerminologyDataFormat](#API_GetTerminology_RequestSyntax) **   <a name="Translate-GetTerminology-request-TerminologyDataFormat"></a>
Type: String  
Valid Values:` CSV | TMX`   
Required: Yes

## Response Syntax<a name="API_GetTerminology_ResponseSyntax"></a>

```
{
   "[TerminologyDataLocation](#Translate-GetTerminology-response-TerminologyDataLocation)": { 
      "[Location](API_TerminologyDataLocation.md#Translate-Type-TerminologyDataLocation-Location)": "string",
      "[RepositoryType](API_TerminologyDataLocation.md#Translate-Type-TerminologyDataLocation-RepositoryType)": "string"
   },
   "[TerminologyProperties](#Translate-GetTerminology-response-TerminologyProperties)": { 
      "[Arn](API_TerminologyProperties.md#Translate-Type-TerminologyProperties-Arn)": "string",
      "[CreatedAt](API_TerminologyProperties.md#Translate-Type-TerminologyProperties-CreatedAt)": number,
      "[Description](API_TerminologyProperties.md#Translate-Type-TerminologyProperties-Description)": "string",
      "[EncryptionKey](API_TerminologyProperties.md#Translate-Type-TerminologyProperties-EncryptionKey)": { 
         "[Id](API_EncryptionKey.md#Translate-Type-EncryptionKey-Id)": "string",
         "[Type](API_EncryptionKey.md#Translate-Type-EncryptionKey-Type)": "string"
      },
      "[LastUpdatedAt](API_TerminologyProperties.md#Translate-Type-TerminologyProperties-LastUpdatedAt)": number,
      "[Name](API_TerminologyProperties.md#Translate-Type-TerminologyProperties-Name)": "string",
      "[SizeBytes](API_TerminologyProperties.md#Translate-Type-TerminologyProperties-SizeBytes)": number,
      "[SourceLanguageCode](API_TerminologyProperties.md#Translate-Type-TerminologyProperties-SourceLanguageCode)": "string",
      "[TargetLanguageCodes](API_TerminologyProperties.md#Translate-Type-TerminologyProperties-TargetLanguageCodes)": [ "string" ],
      "[TermCount](API_TerminologyProperties.md#Translate-Type-TerminologyProperties-TermCount)": number
   }
}
```

## Response Elements<a name="API_GetTerminology_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [TerminologyDataLocation](#API_GetTerminology_ResponseSyntax) **   <a name="Translate-GetTerminology-response-TerminologyDataLocation"></a>
Type: [TerminologyDataLocation](API_TerminologyDataLocation.md) object

 ** [TerminologyProperties](#API_GetTerminology_ResponseSyntax) **   <a name="Translate-GetTerminology-response-TerminologyProperties"></a>
Type: [TerminologyProperties](API_TerminologyProperties.md) object

## Errors<a name="API_GetTerminology_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **InternalServerException**   
An internal server error occurred\. Retry your request\.  
HTTP Status Code: 500

 **InvalidParameterValueException**   
HTTP Status Code: 400

 **ResourceNotFoundException**   
HTTP Status Code: 400

 **TooManyRequestsException**   
The number of requests exceeds the limit\. Resubmit your request later\.  
HTTP Status Code: 400

## See Also<a name="API_GetTerminology_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/translate-2017-07-01/GetTerminology) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/translate-2017-07-01/GetTerminology) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/translate-2017-07-01/GetTerminology) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/translate-2017-07-01/GetTerminology) 
+  [AWS SDK for Java](https://docs.aws.amazon.com/goto/SdkForJava/translate-2017-07-01/GetTerminology) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/translate-2017-07-01/GetTerminology) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/translate-2017-07-01/GetTerminology) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/translate-2017-07-01/GetTerminology) 
+  [AWS SDK for Ruby V2](https://docs.aws.amazon.com/goto/SdkForRubyV2/translate-2017-07-01/GetTerminology) 