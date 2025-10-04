# Database Connection (`db_connect.php`)

Provides a `$mysqli` instance connected to MySQL. On connection error, the script terminates.

## Usage
```php
require_once 'db_connect.php';
$stmt = $mysqli->prepare('SELECT * FROM students LIMIT 10');
$stmt->execute();
$result = $stmt->get_result();
```

## Configuration
- Host: `localhost`
- User: `root`
- Password: empty
- Database: `student_db`

Adjust credentials in `school_system/db_connect.php` to match your local setup.
