# Display-WordPress-Errors-conditionaly-for-ADmin-

You can't run WP function on wp-config.php so its bit tricky to check for the current user is admin or not, 
you can check by $_GET variable isset or not 

```
/*Put this code to config.php*/

if( isset($_GET['debug'])) {
define('WP_DEBUG', true);
define('WP_DEBUG_DISPLAY', true);
}
else{

ini_set('display_errors','Off');
ini_set('error_reporting', E_ALL );
define('WP_DEBUG', false);
define('WP_DEBUG_DISPLAY', false);
}

/*End of code*/```

Then visit by adding url parameter debug on your url
http://yoursite.com/?debug

Error will only display when debug parameter is set on your url
