# Swagger\Client\FileSanitizationApi

All URIs are relative to *https://api.cloudmersive.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**file**](FileSanitizationApi.md#file) | **POST** /cdr/sanitization/file | Content Disarm and Reconstruction on a File
[**fileAdvanced**](FileSanitizationApi.md#fileAdvanced) | **POST** /cdr/sanitization/file/advanced | Advanced Content Disarm and Reconstruction on a File
[**fileToPdf**](FileSanitizationApi.md#fileToPdf) | **POST** /cdr/sanitization/file/to/pdf | Content Disarm and Reconstruction on a File with PDFA Output
[**fileToPdfAdvanced**](FileSanitizationApi.md#fileToPdfAdvanced) | **POST** /cdr/sanitization/file/to/pdf/advanced | Advanced Content Disarm and Reconstruction on a File with PDFA Output


# **file**
> string file($input_file)

Content Disarm and Reconstruction on a File

Processes the input file via CDR to produce a secured output file.  Input content is parsed, disarmed, and then reconstructed into a new output file with the same file format as the input.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure API key authorization: Apikey
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKey('Apikey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Apikey', 'Bearer');

$apiInstance = new Swagger\Client\Api\FileSanitizationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$input_file = "/path/to/file.txt"; // \SplFileObject | Input document, or photos of a document, to extract data from

try {
    $result = $apiInstance->file($input_file);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FileSanitizationApi->file: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **input_file** | **\SplFileObject**| Input document, or photos of a document, to extract data from | [optional]

### Return type

**string**

### Authorization

[Apikey](../../README.md#Apikey)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/octet-stream

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **fileAdvanced**
> string fileAdvanced($allow_executables, $allow_invalid_files, $allow_scripts, $allow_password_protected_files, $allow_macros, $allow_xml_external_entities, $allow_insecure_deserialization, $allow_html, $allow_unsafe_archives, $allow_ole_embedded_object, $allow_unwanted_action, $restrict_file_types, $input_file)

Advanced Content Disarm and Reconstruction on a File

Processes the input file via CDR to produce a secured output file with advanced scan options and response headers containing scan metadata.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure API key authorization: Apikey
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKey('Apikey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Apikey', 'Bearer');

$apiInstance = new Swagger\Client\Api\FileSanitizationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$allow_executables = true; // bool | Set to false to block executable files (EXE, DLL, etc.)
$allow_invalid_files = true; // bool | Set to false to block files that are not valid for their detected type
$allow_scripts = true; // bool | Set to false to block script files. PDF and Office macro sanitization still runs regardless.
$allow_password_protected_files = true; // bool | Set to false to block password-protected files
$allow_macros = true; // bool | Set to false to block files containing macros. Office macro removal still runs regardless.
$allow_xml_external_entities = true; // bool | Set to false to block XML files with external entity references (XXE)
$allow_insecure_deserialization = true; // bool | Set to false to block files with insecure deserialization patterns
$allow_html = true; // bool | Set to false to block HTML files
$allow_unsafe_archives = true; // bool | Set to false to block archive files flagged as unsafe (e.g., zip bombs)
$allow_ole_embedded_object = true; // bool | Set to false to block files with embedded OLE objects
$allow_unwanted_action = true; // bool | Set to false to block files with unwanted actions
$restrict_file_types = "restrict_file_types_example"; // string | Comma-separated list of allowed file extensions (e.g., \".pdf,.docx,.xlsx\"). Files not matching will be blocked.
$input_file = "/path/to/file.txt"; // \SplFileObject | Input document to CDR process

try {
    $result = $apiInstance->fileAdvanced($allow_executables, $allow_invalid_files, $allow_scripts, $allow_password_protected_files, $allow_macros, $allow_xml_external_entities, $allow_insecure_deserialization, $allow_html, $allow_unsafe_archives, $allow_ole_embedded_object, $allow_unwanted_action, $restrict_file_types, $input_file);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FileSanitizationApi->fileAdvanced: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **allow_executables** | **bool**| Set to false to block executable files (EXE, DLL, etc.) | [optional]
 **allow_invalid_files** | **bool**| Set to false to block files that are not valid for their detected type | [optional]
 **allow_scripts** | **bool**| Set to false to block script files. PDF and Office macro sanitization still runs regardless. | [optional]
 **allow_password_protected_files** | **bool**| Set to false to block password-protected files | [optional]
 **allow_macros** | **bool**| Set to false to block files containing macros. Office macro removal still runs regardless. | [optional]
 **allow_xml_external_entities** | **bool**| Set to false to block XML files with external entity references (XXE) | [optional]
 **allow_insecure_deserialization** | **bool**| Set to false to block files with insecure deserialization patterns | [optional]
 **allow_html** | **bool**| Set to false to block HTML files | [optional]
 **allow_unsafe_archives** | **bool**| Set to false to block archive files flagged as unsafe (e.g., zip bombs) | [optional]
 **allow_ole_embedded_object** | **bool**| Set to false to block files with embedded OLE objects | [optional]
 **allow_unwanted_action** | **bool**| Set to false to block files with unwanted actions | [optional]
 **restrict_file_types** | **string**| Comma-separated list of allowed file extensions (e.g., \&quot;.pdf,.docx,.xlsx\&quot;). Files not matching will be blocked. | [optional]
 **input_file** | **\SplFileObject**| Input document to CDR process | [optional]

### Return type

**string**

### Authorization

[Apikey](../../README.md#Apikey)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/octet-stream

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **fileToPdf**
> string fileToPdf($input_file)

Content Disarm and Reconstruction on a File with PDFA Output

Processes the input file via CDR to produce a secured PDF/A output file.  Input content is parsed, disarmed, and then reconstructed into a new PDF/A output file.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure API key authorization: Apikey
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKey('Apikey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Apikey', 'Bearer');

$apiInstance = new Swagger\Client\Api\FileSanitizationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$input_file = "/path/to/file.txt"; // \SplFileObject | Input document, or photos of a document, to extract data from

try {
    $result = $apiInstance->fileToPdf($input_file);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FileSanitizationApi->fileToPdf: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **input_file** | **\SplFileObject**| Input document, or photos of a document, to extract data from | [optional]

### Return type

**string**

### Authorization

[Apikey](../../README.md#Apikey)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/octet-stream

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **fileToPdfAdvanced**
> string fileToPdfAdvanced($allow_executables, $allow_invalid_files, $allow_scripts, $allow_password_protected_files, $allow_macros, $allow_xml_external_entities, $allow_insecure_deserialization, $allow_html, $allow_unsafe_archives, $allow_ole_embedded_object, $allow_unwanted_action, $restrict_file_types, $input_file)

Advanced Content Disarm and Reconstruction on a File with PDFA Output

Processes the input file via CDR to produce a secured PDF/A output file with advanced scan options and response headers containing scan metadata.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure API key authorization: Apikey
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKey('Apikey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Apikey', 'Bearer');

$apiInstance = new Swagger\Client\Api\FileSanitizationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$allow_executables = true; // bool | Set to false to block executable files (EXE, DLL, etc.)
$allow_invalid_files = true; // bool | Set to false to block files that are not valid for their detected type
$allow_scripts = true; // bool | Set to false to block script files. PDF and Office macro sanitization still runs regardless.
$allow_password_protected_files = true; // bool | Set to false to block password-protected files
$allow_macros = true; // bool | Set to false to block files containing macros. Office macro removal still runs regardless.
$allow_xml_external_entities = true; // bool | Set to false to block XML files with external entity references (XXE)
$allow_insecure_deserialization = true; // bool | Set to false to block files with insecure deserialization patterns
$allow_html = true; // bool | Set to false to block HTML files
$allow_unsafe_archives = true; // bool | Set to false to block archive files flagged as unsafe (e.g., zip bombs)
$allow_ole_embedded_object = true; // bool | Set to false to block files with embedded OLE objects
$allow_unwanted_action = true; // bool | Set to false to block files with unwanted actions
$restrict_file_types = "restrict_file_types_example"; // string | Comma-separated list of allowed file extensions (e.g., \".pdf,.docx,.xlsx\"). Files not matching will be blocked.
$input_file = "/path/to/file.txt"; // \SplFileObject | Input document to CDR process

try {
    $result = $apiInstance->fileToPdfAdvanced($allow_executables, $allow_invalid_files, $allow_scripts, $allow_password_protected_files, $allow_macros, $allow_xml_external_entities, $allow_insecure_deserialization, $allow_html, $allow_unsafe_archives, $allow_ole_embedded_object, $allow_unwanted_action, $restrict_file_types, $input_file);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FileSanitizationApi->fileToPdfAdvanced: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **allow_executables** | **bool**| Set to false to block executable files (EXE, DLL, etc.) | [optional]
 **allow_invalid_files** | **bool**| Set to false to block files that are not valid for their detected type | [optional]
 **allow_scripts** | **bool**| Set to false to block script files. PDF and Office macro sanitization still runs regardless. | [optional]
 **allow_password_protected_files** | **bool**| Set to false to block password-protected files | [optional]
 **allow_macros** | **bool**| Set to false to block files containing macros. Office macro removal still runs regardless. | [optional]
 **allow_xml_external_entities** | **bool**| Set to false to block XML files with external entity references (XXE) | [optional]
 **allow_insecure_deserialization** | **bool**| Set to false to block files with insecure deserialization patterns | [optional]
 **allow_html** | **bool**| Set to false to block HTML files | [optional]
 **allow_unsafe_archives** | **bool**| Set to false to block archive files flagged as unsafe (e.g., zip bombs) | [optional]
 **allow_ole_embedded_object** | **bool**| Set to false to block files with embedded OLE objects | [optional]
 **allow_unwanted_action** | **bool**| Set to false to block files with unwanted actions | [optional]
 **restrict_file_types** | **string**| Comma-separated list of allowed file extensions (e.g., \&quot;.pdf,.docx,.xlsx\&quot;). Files not matching will be blocked. | [optional]
 **input_file** | **\SplFileObject**| Input document to CDR process | [optional]

### Return type

**string**

### Authorization

[Apikey](../../README.md#Apikey)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/octet-stream

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

