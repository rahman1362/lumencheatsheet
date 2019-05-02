# lumencheatsheet
Cheatsheet of Lumen framework

<h3>Installing Lumen:</h3>
composer global require "laravel/lumen-installer"
lumen new blog

Serving Your Application:
php -S localhost:8000 -t public

Configuration:

Accessing Configuration Values:
The configuration values may be accessed using "dot" syntax, which includes the name of the file and option you wish to access
$value = config('app.locale');

To set configuration values at runtime, pass an array to the config helper:
config(['app.locale' => 'en']);

Before a configuration file can be used, you should load it into the application using the configure method. This may be done within your bootstrap/app.php file:
$app->configure('app');

Environment Configuration:

The env function may be used to retrieve the values of your environment variables:

$debug = env('APP_DEBUG', true);

The second value passed to the env function is the "default value". This value will be used if no environment variable exists for the given key.

Determining The Current Environment:

$environment = app()->environment();

if (app()->environment('local')) {
    // The environment is local
}

if (app()->environment('local', 'staging')) {
    // The environment is either local OR staging...
}



