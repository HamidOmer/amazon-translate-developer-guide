# TranslateText<a name="API_TranslateText"></a>

Translates input text from the source language to the target language\. It is not necessary to use English \(en\) as either the source or the target language but not all language combinations are supported by Amazon Translate\. For more information, see [Supported Language Pairs](https://docs.aws.amazon.com/translate/latest/dg/pairs.html)\.
+ Arabic \(ar\)
+ Chinese \(Simplified\) \(zh\)
+ Chinese \(Traditional\) \(zh\-TW\)
+ Czech \(cs\)
+ Danish \(da\)
+ Dutch \(nl\)
+ English \(en\)
+ Finnish \(fi\)
+ French \(fr\)
+ German \(de\)
+ Hebrew \(he\)
+ Indonesian \(id\)
+ Italian \(it\)
+ Japanese \(ja\)
+ Korean \(ko\)
+ Polish \(pl\)
+ Portuguese \(pt\)
+ Russian \(ru\)
+ Spanish \(es\)
+ Swedish \(sw\)
+ Turkish \(tr\)

To have Amazon Translate determine the source language of your text, you can specify `auto` in the `SourceLanguageCode` field\. If you specify `auto`, Amazon Translate will call Amazon Comprehend to determine the source language\.

## Request Syntax<a name="API_TranslateText_RequestSyntax"></a>

```
{
   "[SourceLanguageCode](#Translate-TranslateText-request-SourceLanguageCode)": "string",
   "[TargetLanguageCode](#Translate-TranslateText-request-TargetLanguageCode)": "string",
   "[TerminologyNames](#Translate-TranslateText-request-TerminologyNames)": [ "string" ],
   "[Text](#Translate-TranslateText-request-Text)": "string"
}
```

## Request Parameters<a name="API_TranslateText_RequestParameters"></a>

For information about the parameters that are common to all actions, see [Common Parameters](CommonParameters.md)\.

The request accepts the following data in JSON format\.

 ** [SourceLanguageCode](#API_TranslateText_RequestSyntax) **   <a name="Translate-TranslateText-request-SourceLanguageCode"></a>
One of the supported language codes for the source text\.   
To have Amazon Translate determine the source language of your text, you can specify `auto` in the `SourceLanguageCode` field\. If you specify `auto`, Amazon Translate will call Amazon Comprehend to determine the source language\.  
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 5\.  
Required: Yes

 ** [TargetLanguageCode](#API_TranslateText_RequestSyntax) **   <a name="Translate-TranslateText-request-TargetLanguageCode"></a>
One of the supported language codes for the target text\.   
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 5\.  
Required: Yes

 ** [TerminologyNames](#API_TranslateText_RequestSyntax) **   <a name="Translate-TranslateText-request-TerminologyNames"></a>
Type: Array of strings  
Length Constraints: Minimum length of 1\. Maximum length of 256\.  
Pattern: `^([A-Za-z0-9-]_?)+$`   
Required: No

 ** [Text](#API_TranslateText_RequestSyntax) **   <a name="Translate-TranslateText-request-Text"></a>
The text to translate\. The text string can be a maximum of 5,000 bytes long\. Depending on your character set, this may be fewer than 5,000 characters\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 5000\.  
Pattern: `[\P{M}\p{M}]{1,5000}`   
Required: Yes

## Response Syntax<a name="API_TranslateText_ResponseSyntax"></a>

```
{
   "[AppliedTerminologies](#Translate-TranslateText-response-AppliedTerminologies)": [ 
      { 
         "[Name](API_AppliedTerminology.md#Translate-Type-AppliedTerminology-Name)": "string",
         "[Terms](API_AppliedTerminology.md#Translate-Type-AppliedTerminology-Terms)": [ 
            { 
               "[SourceText](API_Term.md#Translate-Type-Term-SourceText)": "string",
               "[TargetText](API_Term.md#Translate-Type-Term-TargetText)": "string"
            }
         ]
      }
   ],
   "[SourceLanguageCode](#Translate-TranslateText-response-SourceLanguageCode)": "string",
   "[TargetLanguageCode](#Translate-TranslateText-response-TargetLanguageCode)": "string",
   "[TranslatedText](#Translate-TranslateText-response-TranslatedText)": "string"
}
```

## Response Elements<a name="API_TranslateText_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** [AppliedTerminologies](#API_TranslateText_ResponseSyntax) **   <a name="Translate-TranslateText-response-AppliedTerminologies"></a>
Type: Array of [AppliedTerminology](API_AppliedTerminology.md) objects

 ** [SourceLanguageCode](#API_TranslateText_ResponseSyntax) **   <a name="Translate-TranslateText-response-SourceLanguageCode"></a>
The language code for the language of the input text\.   
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 5\.

 ** [TargetLanguageCode](#API_TranslateText_ResponseSyntax) **   <a name="Translate-TranslateText-response-TargetLanguageCode"></a>
The language code for the language of the translated text\.   
Type: String  
Length Constraints: Minimum length of 2\. Maximum length of 5\.

 ** [TranslatedText](#API_TranslateText_ResponseSyntax) **   <a name="Translate-TranslateText-response-TranslatedText"></a>
The text translated into the target language\.  
Type: String  
Length Constraints: Maximum length of 10000\.  
Pattern: `[\P{M}\p{M}]{0,10000}` 

## Errors<a name="API_TranslateText_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **DetectedLanguageLowConfidenceException**   
The confidence that Amazon Comprehend accurately detected the source language is low\. If a low confidence level is acceptable for your application, you can use the language in the exception to call Amazon Translate again\. For more information, see the [DetectDominantLanguage](https://docs.aws.amazon.com/comprehend/latest/dg/API_DetectDominantLanguage.html) operation in the *Amazon Comprehend Developer Guide*\.  
HTTP Status Code: 400

 **InternalServerException**   
An internal server error occurred\. Retry your request\.  
HTTP Status Code: 500

 **InvalidRequestException**   
The request is invalid\.  
HTTP Status Code: 400

 **ResourceNotFoundException**   
HTTP Status Code: 400

 **ServiceUnavailableException**   
Amazon Translate is unavailable\. Retry your request later\.  
HTTP Status Code: 400

 **TextSizeLimitExceededException**   
The size of the input text exceeds the length constraint for the `Text` field\. Try again with a shorter text\.   
HTTP Status Code: 400

 **TooManyRequestsException**   
The number of requests exceeds the limit\. Resubmit your request later\.  
HTTP Status Code: 400

 **UnsupportedLanguagePairException**   
Amazon Translate cannot translate input text from the source language into this target language\.   
HTTP Status Code: 400

## See Also<a name="API_TranslateText_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:
+  [AWS Command Line Interface](https://docs.aws.amazon.com/goto/aws-cli/translate-2017-07-01/TranslateText) 
+  [AWS SDK for \.NET](https://docs.aws.amazon.com/goto/DotNetSDKV3/translate-2017-07-01/TranslateText) 
+  [AWS SDK for C\+\+](https://docs.aws.amazon.com/goto/SdkForCpp/translate-2017-07-01/TranslateText) 
+  [AWS SDK for Go](https://docs.aws.amazon.com/goto/SdkForGoV1/translate-2017-07-01/TranslateText) 
+  [AWS SDK for Java](https://docs.aws.amazon.com/goto/SdkForJava/translate-2017-07-01/TranslateText) 
+  [AWS SDK for JavaScript](https://docs.aws.amazon.com/goto/AWSJavaScriptSDK/translate-2017-07-01/TranslateText) 
+  [AWS SDK for PHP V3](https://docs.aws.amazon.com/goto/SdkForPHPV3/translate-2017-07-01/TranslateText) 
+  [AWS SDK for Python](https://docs.aws.amazon.com/goto/boto3/translate-2017-07-01/TranslateText) 
+  [AWS SDK for Ruby V2](https://docs.aws.amazon.com/goto/SdkForRubyV2/translate-2017-07-01/TranslateText) 