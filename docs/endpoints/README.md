# Endpoints Overview

All endpoints are served by Apache/PHP under `school_system/`.

- `GET /school_system/view_students.php`: List students (paged, sortable)
- `GET /school_system/search_student.php`: Get a single student by `roll_no`
- `POST /school_system/add_student.php`: Create a new student
- `GET /school_system/edit_student.php`: Render edit form by `id`
- `POST /school_system/update_student.php`: Update a student by `id`
- `GET /school_system/delete_student.php`: Delete a student by `id`
- `POST /school_system/login.php`: Staff login
- `GET /school_system/logout.php`: Staff logout
