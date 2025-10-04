# Authentication Endpoints

## POST /school_system/login.php
Authenticate staff user and start a session.

### Form Fields
- `username` (string, required)
- `password` (string, required)

### Behavior
- Verifies credentials against `staff` table using a prepared statement and `password_verify`.
- On success, sets `$_SESSION['staff_id']` and `$_SESSION['staff_name']`, then redirects to `view_students.php`.
- On failure, shows alert and redirects to `login.html`.

### Example
```bash
curl -X POST 'http://localhost/school_system/login.php' \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  --data 'username=admin&password=secret'
```

## GET /school_system/logout.php
Destroy session and redirect to login page.

### Example
```bash
curl 'http://localhost/school_system/logout.php'
```
