# 2018 Frank's Classic Cars

PHP + MySQL sample application for browsing classic car inventory, generating RSS feeds by product line, and providing a simple employee-only area for customer/inventory operations.

This repo is primarily intended as a portfolio/learning project.

## What’s Included

- Public pages (home, product browsing, RSS feeds)
- Employee account creation + login
- Member-only pages for inventory and customer/credit-limit workflows
- MySQL-backed data access
- Server-side chart generation (requires PHP GD)

## Key Pages & Endpoints

- Home: [index.php](index.php)
- Product catalog/details: [product.php](product.php)
- Create employee account: [createaccount.php](createaccount.php)
- Employee login: [login.php](login.php)
- RSS feed generator: [autorss.php](autorss.php)
	- Uses a `pl` query parameter for product line selection (examples: `classic`, `vintage`, `motorcycle`).
- Member area home: [members/index.php](members/index.php)
- Member tools:
	- Add customer: [members/addcustomer.php](members/addcustomer.php)
	- Credit limits + chart: [members/creditlimits.php](members/creditlimits.php)
	- Inventory listing: [members/inventory.php](members/inventory.php)
	- Logout: [members/logout.php](members/logout.php)

## Requirements

- PHP 5.4+ (newer versions generally work, but this codebase uses older-style patterns)
- MySQL 5.6+
- PHP extensions:
	- `mysqli`
	- `gd` (needed for server-side chart image generation)
- A web server capable of running PHP (IIS, Apache, Nginx, etc.)

## Database Setup

1. Create a MySQL database (name is configurable).
2. Import the schema/data dump: [uc_davis_web512.sql](uc_davis_web512.sql)
3. Create a database user with appropriate permissions for the imported schema.

## Configuration

Database connection settings live in [includes/variables.inc.php](includes/variables.inc.php). Update these values for your environment:

```php
$host = "<db-host>";
$web_user = "<db-username>";
$pwd = "<db-password>";
$dbname = "<db-name>";
```

## Running Locally

Use any PHP-capable web server pointed at the repository root.

If you prefer PHP’s built-in server (useful for quick smoke tests), run this from the project root:

```bash
php -S 127.0.0.1:8000
```

Then open `http://127.0.0.1:8000/` in your browser.

## RSS Feeds

The RSS generator is implemented in [autorss.php](autorss.php). It selects items by product line using the `pl` query parameter. The output can be styled/transformed with [rssfeed.xsl](rssfeed.xsl).

## Charts / Credit Limits

The credit-limit chart is generated server-side using PHP GD functions (see the graph helpers in [includes/functions.inc.php](includes/functions.inc.php)). If chart images don’t render, verify the `gd` extension is enabled in your PHP installation.

## Notes / Caveats

- Error output is suppressed in [includes/functions.inc.php](includes/functions.inc.php), which can make debugging harder. During local development, you may temporarily enable error reporting.
- This is a teaching/portfolio codebase and is not hardened for production use.
