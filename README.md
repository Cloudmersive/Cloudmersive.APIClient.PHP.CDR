# cloudmersive_cdr_api_client
Use the Content Disarm and Reconstruction API to remove security risks from documents by tearing them down, removing unsafe content and rebuilding them.

[Cloudmersive CDR API](https://cloudmersive.com/cdr-api) provides advanced document sanitization CDR capabilities.

- API version: v1
- Package version: 3.0.0


## Requirements

PHP 5.5 and later

## Installation & Usage
### Composer

To install the bindings via [Composer](http://getcomposer.org/), add the following to `composer.json`:

```
{
  "repositories": [
    {
      "type": "git",
      "url": "https://github.com/cloudmersive/cloudmersive_cdr_api_client.git"
    }
  ],
  "require": {
    "cloudmersive/cloudmersive_cdr_api_client": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
    require_once('/path/to/cloudmersive_cdr_api_client/vendor/autoload.php');
```

## Tests

To run the unit tests:

```
composer install
./vendor/bin/phpunit
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

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
    $apiInstance->file($input_file);
} catch (Exception $e) {
    echo 'Exception when calling FileSanitizationApi->file: ', $e->getMessage(), PHP_EOL;
}

?>
```

## Documentation for API Endpoints

All URIs are relative to *https://api.cloudmersive.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*FileSanitizationApi* | [**file**](docs/Api/FileSanitizationApi.md#file) | **POST** /cdr/sanitization/file | Complete Content Disarm and Reconstruction on an Input File, and output in same file format
*FileSanitizationApi* | [**fileToPdf**](docs/Api/FileSanitizationApi.md#filetopdf) | **POST** /cdr/sanitization/file/to/pdf | Complete Content Disarm and Reconstruction on an Input File with PDF/A Output


## Documentation For Models



## Documentation For Authorization


## Apikey

- **Type**: API key
- **API key parameter name**: Apikey
- **Location**: HTTP header


## Author




