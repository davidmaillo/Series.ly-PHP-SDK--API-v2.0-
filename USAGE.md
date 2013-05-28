	# SERIESLY API PHP SDK #
	## USAGE EXAMPLE: ##

	* api_config.php

	<code>
	// Run the Series.ly class
	require_once("seriesly.class.php");
	$api = new seriesly_api();

	// Your APP parameters
	$id_app = "XXX";
	$secret = "XXXXXXXXXXXXX";
	$callback_url = "http://mydomain.com/mypage.php"; // Page to redirect after login (Where the application starts)
	</code>

	* login.php
	<code>
		// ( Remember: It is necessary to start with the login file )
		require_once("api_config.php");
		$api->get_auth_token($id_app, $secret);
		$api->user_login($callback_url);
	</code>

	* mypage.php
	<code>
		require_once("api_config.php");
		$api->get_auth_token($id_app, $secret);
		$api->get_user_token();
	</code>