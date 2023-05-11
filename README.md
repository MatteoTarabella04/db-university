## Entities

- Student
- Teacher
- Degree course
- Course
- Department
- Exam session

## Tables

- students
- teachers
- degrees
- courses
- departments
- exam sessions

## Table columns:

### departments

- id | BIGINT, PK, AI, NN, UNIQUE, INDEX
- name | VARCHAR(60), NULL
- location | VARCHAR(100), NULL

### degrees courses

- id | BIGINT, PK, AI, NN, UNIQUE, INDEX
- name | BIGINT, PK, AI, NN, UNIQUE
- duration | TINYINT(1), DEFAULT(6) NULL
- type | VARCHAR(20), DEFAULT("live") NULL,
- access | TINYINT (1), NULL
- id_departments | FK, BIGINT

### courses

- id | BIGINT, PK, AI, NN, UNIQUE, INDEX
- name | VARCHAR(100), NN, INDEX
- type | VARCHAR(20), DEFAULT("live") NULL,
- semester | TINYINT(1)
- mandatory | TINYINT (1)
- id_degrees | FK

### courses_teacher (pivot)

- id_course | FK
- id_teacher | FK

### teachers

- id | BIGINT, PK, AI, NN, UNIQUE, INDEX
- full_name | VARCHAR(50), NN
- serial_number | MEDIUMINT, NN
- id_course |FK

### vote_pivot

- id_student
- id_exam_session
- vote |

### exam_session

- id | BIGINT, PK, AI, NN, UNIQUE, INDEX
- season VARCHAR(10)
- data | DATETIME | NULL
- max_students_number | SMALLINT | NULL
- id_course | VARCHAR(20), NN

### students

- id | BIGINT, PK, AI, NN, UNIQUE, INDEX
- fullname | VARCHAR(200), NN, INDEX
- birthdate | DATE, NULL
- address | VARCHAR(100), NN, FK,
- vote_avarege | DECIMAL(2,2), NULL,
- seriale_number | MEDIUMINT, NULL