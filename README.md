# EBAY-PHP

**This repository is updated version of EBAY-SDK-PHP which was abondeded.**

## Features

  - Compatible with PHP 8.0 or greater.
  - Easy to install with [Composer](http://getcomposer.org/).
  - Compliant with [PSR-1](http://www.php-fig.org/psr/psr-1/), [PSR-2](http://www.php-fig.org/psr/psr-2/) and [PSR-4](http://www.php-fig.org/psr/psr-4/).

## Resources

  - [User Guides](https://github.com/davidtsadler/ebay-sdk-php/wiki) - Getting started guide and in-depth information.
  - [Examples](https://github.com/davidtsadler/ebay-sdk-examples) - Several examples of using the SDK.
 
## Requirements

  - PHP 8.0 or greater with the following extensions:
      - cURL
      - libxml
  - 64 bit version of PHP recommended as there are some [issues when using the SDK with 32 bit](http://devbay.net/sdk/guides/getting-started/requirements.html#using-the-sdk-with-32-bit-systems).
  - SSL enabled on the cURL extension so that https requests can be made.

## Installation

The SDK can be installed with [Composer](http://getcomposer.org/).

  1. Install Composer.

     ```
     curl -sS https://getcomposer.org/installer | php
     ```

  1. Install the SDK.

     ```
     php composer.phar require rajarizwan2007/ebay-php
     ```

  1. Require Composer's autoloader by adding the following line to your code.

     ```php
     require 'vendor/autoload.php';
     ```

## Example

### Get the official eBay time

```php
<?php

require 'vendor/autoload.php';

use \DTS\eBaySDK\Shopping\Services;
use \DTS\eBaySDK\Shopping\Types;

// Create the service object.
$service = new Services\ShoppingService();

// Create the request object.
$request = new Types\GeteBayTimeRequestType();

// Send the request to the service operation.
$response = $service->geteBayTime($request);

// Output the result of calling the service operation.
printf("The official eBay time is: %s\n", $response->Timestamp->format('H:i (\G\M\T) \o\n l jS Y'));
```

## License

Licensed under the [Apache Public License 2.0](http://www.apache.org/licenses/LICENSE-2.0.html).
