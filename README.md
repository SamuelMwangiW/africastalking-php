<p align="center"><a href="https://developers.africastalking.com/" target="_blank"><img src="https://africastalking.com/img/logo_color.svg" width="400"></a></p>

# Africa's Talking PHP SDK

[![Latest Version on Packagist](https://img.shields.io/packagist/v/africastalking/sdk.svg?style=flat-square)](https://packagist.org/packages/africastalking/sdk)
[![Tests](https://img.shields.io/github/actions/workflow/status/SamuelMwangiW/php-sdk/run-tests.yml?branch=main&label=tests&style=flat-square)](https://github.com/samuelmwangiw/php-sdk/actions/workflows/run-tests.yml)
[![Total Downloads](https://img.shields.io/packagist/dt/africastalking/sdk.svg?style=flat-square)](https://packagist.org/packages/africastalking/sdk)

> This SDK provides convenient access to the Africa's Talking API for applications written in PHP.


## Documentation

Take a look at the [API docs here](https://developers.africastalking.com).

## Installation

You can install the package via composer:

```bash
composer require africastalking/sdk
```

## Usage

The SDK needs to be instantiated using your username and API key, which you can get from the [dashboard](https://account.africastalking.com).

> You can use this SDK for either production or sandbox apps. For sandbox, the app username is **ALWAYS** `sandbox`

### Basic Usage

```php
use Africastalking\Services\SMS;
use AfricasTalking\DTO\Credentials;
use Africastalking\DTO\Response\MessageResponse;

$username = 'YOUR_USERNAME'; // use 'sandbox' for development in the test environment
$apiKey   = 'YOUR_API_KEY'; // use your sandbox app API key for development in the test environment
$auth = new Credentials($username, $apiKey);

// Get one of the services
$sms = new SMS($auth);

// Use the service
$result = $sms
    ->as('SENDER_ID')
    ->to(['2XXYYYOOO'])
    ->message('Hello World!')
    ->send();

// If successful, $result is an instance of `MessageResponse::class`
print_r($result);
```

## Testing

```bash
composer test
```

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

## Contributing

Please see [CONTRIBUTING](https://github.com/spatie/.github/blob/main/CONTRIBUTING.md) for details.

## Security Vulnerabilities

Please review [our security policy](../../security/policy) on how to report security vulnerabilities.

## Credits

- [Africa's Talking Community](https://github.com/AfricasTalkingLtd)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
