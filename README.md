MailChimp API 3.0 Wrapper
=============

Very Easy to use MailChimp REST Enabled API 3.0 Wrapper Class in PHP.

Requires PHP 5.3 and curl extension.

Installation
------------

You can install the mailchimp-rest-api using Composer. Just add the following to your composer.json:

    {
        "require": {
            "vatps/mailchimp-rest-api": "dev-master"
        }
    }

You will then need to:
* run ``composer install`` to get these dependencies added to your vendor directory
* add the autoloader to your application with this line: ``require("vendor/autoload.php")``

Alternatively you can just download the MailChimp.php file and include it manually.

Laravel Installation
--------------------

Run ``composer require vatps/mailchimp-rest-api`` in terminal.

Laravel Example
---------------

	<?php
	use \VPS\MailChimp;
	
	$mc = new MailChimp();
	$mc->setApiKey('yourapikeyhere-us1');
	
	$result = $mc->get('/lists/');
	return $result;

You can find all available Resources at http://kb.mailchimp.com/api/resources

Examples
--------

Create New Instance and set mailchimp API Key.

	<?php
	$mc = new \VPS\MailChimp('yourapikeyhere-us1');
	
Lists Collection  (GET /lists/)

	<?php
	$result = $mc->get('/lists/');
	print_r($result);
	
Lists Instance  (GET /lists/{list_id})

	<?php
	$result = $mc->get('/lists/{list_id}');
	print_r($result);
	
REMOVE LIST (DELETE /lists/{list_id})

	<?php
	$mc->delete('/lists/{list_id}');

Subscribe to a list (POST /lists/{list_id}/members)

	<?php
	$result = $mc->post('/lists/{list_id}/members', array(
					'email_address' => 'test@vps.com',
					'merge_fields' => array('FNAME'=>'VAT', 'LNAME'=>'PS'),
					'status' => 'subscribed'
				));
	print_r($result);
	
Contact me if you need any help.	
