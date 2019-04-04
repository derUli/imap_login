# imap_login

Enables users to use their login from a mail server to login into UliCMS.

## Dependencies

* [KLogger](https://extend.ulicms.de/klogger.html)
* [php imap Module](http://php.net/manual/de/book.imap.php)

## Installation instructions

1. Add this snippet to your cms-config.php before installation of packages. Adjust it to your individual requirements.

```php
	public $imap_login = [ 
			"imap_mailbox" => "{imap.domain.de:993/imap/ssl}INBOX",
			"log_enabled" => false,
			"skip_on_error" => true,
			"create_user" => true,
			"remove_realm" => true,
			"sync_passwords" => true 
	];
```

2. Install KLogger
3. Install imap_login

## Configuration

imap_login offers some tweakable configuration parameters.

**imap_mailbox** Address of an IMAP Mailbox. For syntax see 
[imap_open()](http://php.net/manual/de/function.imap-open.php)

**log_enabled** Write log files. The log files will be saved in ULICMS_ROOT/content/logs/imap_login.

**skip_on_error** If this is true imap_login will pass credentials to regular UliCMS login procedure, when login with IMAP fails.

**create_user** Create local user if it doesn't exists.

**remove_realm** remove domain from mail address to construct user names for local users.

**sync_passwords**
Sync IMAP passwords with local users on login.