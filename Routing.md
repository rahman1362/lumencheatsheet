# Routing
You will define all of the routes for your application in the routes/web.php file
<h3>Route Parameters</h3>
<h3>Required Parameters:</h3>
<code>$router->get('user/{id}', function ($id) {
    return 'User '.$id;
});</code>

<h3>Regular Expression Constraints</h3>
<code>$router->get('user/{name:[A-Za-z]+}', function ($name) {
    //
});</code>
<h3>Named Routes</h3>
<code>
$router->get('profile', [
    'as' => 'profile', 'uses' => 'UserController@showProfile'
]);
</code>

 you may use the route's name when generating URLs or redirects via the global route function:
<code>
// Generating URLs...
$url = route('profile');

// Generating Redirects...
return redirect()->route('profile', ['id' => 1]);;
</code>

<h3>Middleware</h3>
Assigning middleware to all routes within a group:
<code>
$router->group(['middleware' => 'auth'], function () use ($router) {
    $router->get('/', function () {
        // Uses Auth Middleware
    });

    $router->get('user/profile', function () {
        // Uses Auth Middleware
    });
});
</code>
<h3>Route Prefixes</h3>
<code>
$router->group(['prefix' => 'admin'], function () use ($router) {
    $router->get('users', function ()    {
        // Matches The "/admin/users" URL
    });
});
</code>

