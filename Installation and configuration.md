# lumencheatsheet
Cheatsheet of Lumen framework

<h2>Installing Lumen:</h2>
<code>composer global require "laravel/lumen-installer"
lumen new blog</code>

<h3>Serving Your Application:</h3>

<code>php -S localhost:8000 -t public</code>

<h2>Configuration:</h2>

<h3>Accessing Configuration Values:</h3>
The configuration values may be accessed using "dot" syntax, which includes the name of the file and option you wish to access

<code>$value = config('app.locale');</code>

To set configuration values at runtime, pass an array to the config helper:

<code>config(['app.locale' => 'en']);</code>

Before a configuration file can be used, you should load it into the application using the configure method. This may be done within your bootstrap/app.php file:

<code>$app->configure('app');</code>

<h4>Environment Configuration:</h4>

The env function may be used to retrieve the values of your environment variables:

<code>$debug = env('APP_DEBUG', true);</code>

The second value passed to the env function is the "default value". This value will be used if no environment variable exists for the given key.

<b>Determining The Current Environment:</b>

<code>
 $environment = app()->environment();</code>

<code>if (app()->environment('local')) {
    // The environment is local
}</code>
<code>
if (app()->environment('local', 'staging')) {
    // The environment is either local OR staging...
}
</code>


