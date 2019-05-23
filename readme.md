# Addon requirements check

Simple drop-in library for Posterno addons to check for core plugin version requirements.

## Usage

Install the library via composer:

```
composer require posterno/addon-requirements-check
```

In your main plugin file, instantiate the class using something like this:

```php
if ( file_exists( dirname( __FILE__ ) . '/vendor/autoload.php' ) ) {
	require dirname( __FILE__ ) . '/vendor/autoload.php';
}
$requirements_check = new \PosternoRequirements\Check(
	array(
		'title' => 'Addon name',
		'php'   => '5.5',
		'wp'    => '4.7',
		'pno'   => '1.0.0',
		'file'  => __FILE__,
	)
);
if ( $requirements_check->passes() ) {
	// Proceed here.
}
unset( $requirements_check );
```

## Credits:

Original library from [https://github.com/wearerequired/wp-requirements-check](https://github.com/wearerequired/wp-requirements-check) modified to add support for Posterno's plugin version checks.