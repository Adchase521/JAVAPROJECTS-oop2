# JAVAPROJECTS-oop2
Adrix StudentManagementSystem
================================================================================
STUDENT MANAGEMENT SYSTEM - DOCUMENTATION
================================================================================

1. SYSTEM OVERVIEW
--------------------------------------------------------------------------------
A desktop GUI application for managing student records using Java Swing and 
SQLite database. Implements full CRUD operations with search functionality.

2. CLASS DESCRIPTIONS
--------------------------------------------------------------------------------

| Class Name      | Purpose                                           |
|-----------------|---------------------------------------------------|
| StudentDB       | Handles database creation and initialization      |
| DBConnection    | Manages SQLite database connection                |
| Student         | Model class representing student entity           |
| StudentDAO      | Data Access Object - all database operations      |
| StudentGUI      | Main GUI interface with event handling            |

3. DATABASE SCHEMA
--------------------------------------------------------------------------------
Table: students
- id (INTEGER, Primary Key, Auto-increment)
- name (TEXT, Not Null)
- age (INTEGER, Not Null)
- email (TEXT, Unique, Not Null)
- course (TEXT)
- grade (TEXT)

4. JDBC USAGE EXPLANATION
--------------------------------------------------------------------------------
- Connection Management: DBConnection class uses DriverManager to establish
  SQLite connections (jdbc:sqlite:studentdb.db)
- Prepared Statements: All CRUD operations use PreparedStatement to prevent
  SQL injection attacks
- Auto-close Resources: Try-with-resources ensures connections, statements,
  and result sets are properly closed
- Transaction Handling: Each operation is atomic (single statement execution)

5. OOP PRINCIPLES APPLIED
--------------------------------------------------------------------------------
- Encapsulation: Private fields with public getters/setters in Student class
- Separation of Concerns: Database logic (DAO) separated from GUI (View)
- Single Responsibility: Each class has one specific purpose
- Data Hiding: Database connection details hidden in DBConnection class

6. VALIDATION IMPLEMENTED
--------------------------------------------------------------------------------
- Required field validation (all fields must be filled)
- Email format validation (regex pattern)
- Age range validation (0-120 years)
- Duplicate email prevention (database check)
- Numeric age validation (prevents text input)

7. BONUS FEATURES IMPLEMENTED
--------------------------------------------------------------------------------
- Search functionality (by name, email, or course)
- Prepared statements for SQL injection prevention
- Enhanced UI design (colors, layouts, button styling)
- Confirmation dialogs for delete operations
- Auto-generated ID display (read-only field)

================================================================================
