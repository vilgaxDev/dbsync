#vilgax

## Installation

Run `composer require "scottjs/db-sync:1.*" --dev` from the root of your project.

Alternatively, you can manually add `"scottjs/db-sync": "1.*"` to your `composer.json` file:

```
"require-dev": {
	"scottjs/db-sync": "1.*"
}
```

Then add the following scripts to your `composer.json` file:

```
"scripts": {
	"database-update" : [
		"vendor/scottjs/db-sync/database-update.sh"
	],
	"database-prepare" : [
		"vendor/scottjs/db-sync/database-prepare.sh"
	],
	"database-import" : [
		"vendor/scottjs/db-sync/database-import.sh"
	],
	"database-export" : [
		"vendor/scottjs/db-sync/database-export.sh"
	]
}
```

Run the `composer update` command from the root of your project. 

Create a `.env` file in the root of your project and add/update the following configuration options:

```
DOMAIN_REMOTE=www.example.com
DOMAIN_LOCAL=www.example.local

DB_HOST=localhost
DB_DATABASE=example
DB_USERNAME=root
DB_PASSWORD=password

REMOTE_DB_HOST=123.123.123.123
REMOTE_DB_DATABASE=example
REMOTE_DB_USERNAME=root
REMOTE_DB_PASSWORD=password
```
.

## Config

See below for an explanation of each configuration option used within the .env file.

* ***DOMAIN_REMOTE*** - It should point to your remote or production environment (if available) and not include http:// or trailing slashes. Example: `www.example.com` or `subdomain.example.com`.

* ***DOMAIN_LOCAL*** - It should not include http:// or trailing slashes. Example: `www.example.local` or `subdomain.example.local`.

* ***DB_**** - Provides options to set the local database connection details.

* ***REMOTE\_DB_**** - Provides options to set the remote staging or production database connection details.
