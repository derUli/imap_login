# imap_login

Ermöglicht Usern sich über einen IMAP (E-Mail) Server an UliCMS anzumelden.

## Abhängigkeiten

* [KLogger](https://extend.ulicms.de/klogger.html)
* [php imap Modul](http://php.net/manual/de/book.imap.php)

## Installationsanleitung

1. Fügen Sie vor der Installation des Moduls folgendes Snippet in die Datei **cms-config.php** ein. Passen Sie die Konfiguration wie gewünscht an

```php
	var $imap_login = [ 
			"imap_mailbox" => "{imap.domain.de:993/imap/ssl}INBOX",
			"log_enabled" => false,
			"skip_on_error" => true,
			"create_user" => true,
			"remove_realm" => true,
			"sync_passwords" => true 
	];
```

2. Installieren Sie **KLogger**
3. Installiere Sie **imap_login**

## Konfiguration

imap_login enthält einige anpassbare Konfigurationsparameter

**imap_mailbox** Adresse einer IMAP Mailbox, für Informationen zur Syntax schauen Sie bitte in der PHP-Dokumentation unter.
[imap_open()](http://php.net/manual/de/function.imap-open.php)

**log_enabled** Ob Log-Dateien erzeugt werden sollen. Die Logs werden im Ordner ULICMS_ROOT/content/logs/imap_login erzeugt.

**skip_on_error** Wenn diese Option **true** ist, erfolgt ein Login über das reguläre Login-System von UliCMS, wenn der Login mehr IMAP fehl schlägt.

**create_user** Erzeuge einen Lokalen Benutzer, wenn dieser nicht existiert.

**remove_realm** entferne die Domain ab dem @-Zeichen aus der E-Mail Adresse bei Generierung des Nutzernamens

**sync_passwords**
Sollen IMAP Passwörter mit UliCMS synchronisiert werden?