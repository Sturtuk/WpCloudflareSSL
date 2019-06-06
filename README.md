# Enable Cloudflare Flexible SSL
Enable Cloudlfare Flexible ssl on shared hosting

```php
<?php
/**
* @author Edwin F Sturt
* @uses Enable Cloudflare Flexible SSL
* @usage Just Copy paste the code in functions.php 
* @dated June-06-2019
*/
class CloudflareSSL {

	public function enableSSL() {

		// for cloudflare
		if ( isset( $_SERVER[ 'HTTP_CF_VISITOR' ] ) && ( strpos( $_SERVER[ 'HTTP_CF_VISITOR' ], 'https' ) !== false ) ) {
			$_SERVER[ 'HTTPS' ] = 'on';
		}

		// for other...
		if(isset($_SERVER['HTTP_X_FORWARDED_PROTO']) && $_SERVER['HTTP_X_FORWARDED_PROTO'] == 'https'){
		    $_SERVER['HTTPS']='on';
		}

	}


}

$ssl = new CloudflareSSL();

$ssl->enableSSL();
```
