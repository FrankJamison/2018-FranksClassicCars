# 2018 RSS Feed Portfolio

This project is a PHP-based web application for managing and displaying product and customer data, with integrated RSS feed functionality. It was originally developed as a portfolio project for UC Davis Web512 coursework.

## Features

- Customer and employee management
- Product catalog and inventory
- RSS feed generation for product updates
- User authentication and account creation
- Data visualization with charts
- Modular includes for easy code maintenance
- MySQL database integration

## Project Structure

- `index.php` — Main landing page
- `autorss.php` — Automatic RSS feed generator
- `createaccount.php` — User registration
- `login.php` — User login
- `product.php` — Product catalog and details
- `members/` — Member-only pages (add customer, inventory, etc.)
- `includes/` — Reusable PHP includes (header, footer, session, variables)
- `css/style.css` — Main stylesheet
- `charts/` — Data visualization scripts
- `images/` — Project images
- `uc_davis_web512.sql` — MySQL database schema and sample data

## Database

The application uses a MySQL database. Connection variables are set in `includes/variables.inc.php`:

```php
$host = "localhost";
$web_user = "rss_feed_user";
$pwd = "lvg!(VQ8a47TXssh";
$dbname = "rss_feed";
```

Import the provided `uc_davis_web512.sql` file to set up the database schema and sample data.

## Setup Instructions

1. Clone this repository.
2. Import `uc_davis_web512.sql` into your MySQL server.
3. Update database credentials in `includes/variables.inc.php` if needed.
4. Ensure your web server supports PHP and has access to the MySQL database.
5. Access the site via your local server (e.g., http://2018rssfeed.localhost/).

## Requirements

- PHP 5.4+
- MySQL 5.6+
- Web server (Apache, Nginx, etc.)

## License

This project is for educational and portfolio purposes. Please contact the author for reuse or distribution.

---

**Author:** Frank Jamison

For questions or support, contact frank@frankjamison.com
