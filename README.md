Keypasco Authenticator
======================

Keypasco Authenticator is a Wordpress-plugin to use with the Keypasco authentication service. 
It will give you the option to use a two-part authentication method, using either the Vakten 
desktop application or the Vakten smartphone application.

##Functions

###Admin Settings
The administrator is able to set the following settings: 

 * Customer ID
 * API-server URL
 * Enable/Disable sitewide authentication
 * Hide Users ability to enable/disable authentication
 * Enable/disable single users authentication
 
###User Options
Every user is able to do the following: 

 * Enable/Disable authentication (if the option is not hidden)
 * Register device with Desktop Vakten
 * Test Authentication with Desktop Vakten
 * Generate association code for smartphone

###Log in
 * Regular log in if the authentication is disabled.
 * Using the desktop vakten if authentication is enabled.
 * Using smartphone vakten if authentication is enabled.
 
##Installation
 
###Requirements
 * Wordpress 3.6+
 * PHP 5.3+ with SOAP Enabled
 
###Enable SOAP
If SOAP is not enabled the site will not work. Here is a step by step guide to enable SOAP:
####Windows:
Look up the following inside your script file:

	phpinfo();
	
If you can't find Soap Client set to enabled or cant even find the soap header you have to do the following:

 1. Locate php.ini in your apache bin folder, I.e Apache/bin/php.ini
 2. Remove the ; from the beginning of 
 
 	;extension=php_soap.dll
 
 3. Restart your Apache server
 4. Look up your phpinfo(); again and check if you can find soap
 5. If you do, problem solved!
 
If this won't solve it, check [the requirements of SOAP](http://php.net/manual/en/soap.requirements.php).
 
####Unix
For good measure, check to see what your phpinfo says, if anything, about SOAP extensions:

    $ php -i | grep -i soap

to ensure that it is the PHP extension that is missing.

Assuming you do not see anything about SOAP in the phpinfo, see what PHP SOAP packages might be available to you.

In Ubuntu/Debian you can search with:

    $ apt-cache search php | grep -i soap

or in RHEL/Fedora you can search with:

    $ yum search php | grep -i soap

There are usually two PHP SOAP packages available to you, usually `php-soap` and `php-nusoap`. `php-soap` is typically what you get with configuring PHP with `--enable-soap`.

In Ubuntu/Debian you can install with:

    $ sudo apt-get install php-soap

Or in RHEL/Fedora you can install with:

    $ sudo yum install php-soap

After the installation, you might need to place an ini file and restart Apache.

###Installation

####Using Wordpress Dashboard
 1. Visit 'Plugins > Add new'
 2. Go to 'Upload'
 3. Upload the a zip-file of the plugin directory.
 4. Activate Keypasco Authenticator from your Plugins page.
 
####Using other methods
 1. Upload the 'keypasco' directory to your '/wp-content/plugins/' directory, using your favorite method (ftp, sftp, scp, etc...)
 2. Activate Keypasco Authenticator from your Plugins page.
 
 
