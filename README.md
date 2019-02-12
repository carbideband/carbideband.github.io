# carbideband.github.io
#### The repository for Carbide's website

www.carbi.de.com is made possible by the following awesome projects & services:
- [Github](https://github.com/)
- [FullPage.js](https://alvarotrigo.com/fullPage/)
- [Jekyll](https://jekyllrb.com/)'s [Minima Theme](https://github.com/jekyll/minima)

Using Github as a host, requires only a domain name to be registered (if you even want a custom domain).
CNAME must be set within repo & domain provider DNS settings, if you do.
Caveat being that gh-pages only allows the use of static pages.
Fullpage.js allows the use of JavaScript to make Github's static pages a bit more versatile.
In our usecase, what we wanted was for users to be able to browse the webpage, without interrupting the music player.

Reference the [README for FullPage.js](https://github.com/alvarotrigo/fullPage.js/blob/master/README.md) to modify and understand how slides are set up for your usecase.

To validate our licenseKey, we use a hosted Apache server and [authenticate our license via AJAX](https://github.com/carbideband/carbideband.github.io/commit/39ade5ab531239a0cd17f56cb612a7e9b3d5c16c).

You can create your own server-side 'keyring.php' with something like this:
```php
<?php
header("Access-Control-Allow-Origin: http://website.org");
header("Access-Control-Allow-Headers: XRequested-With, Content-Type");
header("Content-Type: application/json");

include(__DIR__ . '/path/to/hidden_keys.php');

$key = array();

if(isset($_POST['findkey'])) {
	switch($_POST['findkey']) {
		case 'fullpage':
			$key['result'] = $selectkey[0];
			break;
 		case 'secondkey':
			$key['result'] = $selectkey[1];
			break;
		default:
			$key['error'] = 'Invalid key selected.';
			break;
	}
}

echo  json_encode($key);

?>
```
hidden_keys.php 
```php
<?php
$selectkey = array('your-keycode-here', 'second-keycode'); /*invoked by: ($selectkey[0], selectkey[1])*/
?>
```
```hidden_keys.php``` can be hidden by moving it into an include folder outside of web root.

Using an array will allow you to store multiple keys and use them whenever you need to by invoking the proper array value.

Sidenote about Jekyll: It is a great way to make an exceptional static blog with little to no programming background
and their Minima theme is amazing.
It is great for just about any website (so long as you do some modifying).

Hope this helps out anyone else looking to create a website similar to ours.
