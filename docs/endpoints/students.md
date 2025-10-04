# Students Endpoints

## GET /school_system/view_students.php
List students with pagination and sorting.

### Query Parameters
- `page` (int, optional): 1-based page index. Default: 1
- `sort` (enum, optional): One of `id`, `roll_no`, `name`, `class`, `admission_date`. Default: `id`
- `order` (enum, optional): `asc` or `desc`. Default: `asc`

### Response
Renders an HTML table. For API-like usage, parse the table or create a JSON variant.

### Example
```bash
curl 'http://localhost/school_system/view_students.php?sort=name&order=asc&page=2'
```

---

## GET /school_system/search_student.php
Fetch a single student by roll number.

### Query Parameters
- `roll_no` (string, required)

### Response
Renders an HTML page with student details or a warning if not found.

### Example
```bash
curl 'http://localhost/school_system/search_student.php?roll_no=1001'
```

---

## POST /school_system/add_student.php
Create a new student.

### Form Fields (application/x-www-form-urlencoded)
- `roll_no` (string, required)
- `name` (string, required)
- `class` (string, optional)
- `email` (string, optional)
- `contact` (string, optional)
- `address` (string, optional)
- `admission_date` (date, optional `YYYY-MM-DD`)

### Validation
- `roll_no` and `name` are required. Duplicate roll numbers are rejected (MySQL 1062).

### Response
Alerts success or error via JavaScript and redirects to `view_students.php`.

### Example
```bash
curl -X POST 'http://localhost/school_system/add_student.php' \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  --data 'roll_no=1002&name=Fatima%20Noor&class=5&email=f@example.com'
```

---

## GET /school_system/edit_student.php
Render edit form for a student by id.

### Query Parameters
- `id` (int, required)

### Response
HTML form prefilled with student fields. Submits to `update_student.php`.

### Example
```bash
curl 'http://localhost/school_system/edit_student.php?id=12'
```

---

## POST /school_system/update_student.php
Update a student by id.

### Form Fields
- `id` (int, required)
- `roll_no` (string, required)
- `name` (string, required)
- `class` (string, optional)
- `email` (string, optional)
- `contact` (string, optional)
- `address` (string, optional)
- `admission_date` (date, optional)

### Response
Alerts success or error via JavaScript and redirects back.

### Example
```bash
curl -X POST 'http://localhost/school_system/update_student.php' \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  --data 'id=12&roll_no=1002&name=Fatima%20Noor&class=6'
```

---

## GET /school_system/delete_student.php
Delete a student by id.

### Query Parameters
- `id` (int, required)

### Response
Alerts success or error and redirects to `view_students.php`.

### Example
```bash
curl 'http://localhost/school_system/delete_student.php?id=12'
```
