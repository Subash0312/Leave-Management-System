
🔸Manages user accounts, roles, and access permissions.

### Profile Management
🔸Enables users to view and update their personal information.

### Settings
🔸Allows configuration of system preferences and management options.

### Reports (Future Enhancement)
🔸Generates reports and analytics related to leave records and user activities.


## Use Case Diagram

🔸The use case diagram below shows the major actors and functionalities of the Leave Management System.

![Use Case Diagram](file_000000003430722facbd7dd187ff2046.png)


## Table List

| Table Name | Purpose |
|------------|---------|
| Users | Stores login and user information for Student, Staff, HOD, and Principal |
| Leave_Requests | Stores leave application details submitted by users |
| Leave_Approvals | Tracks approval or rejection status at different levels |
| Roles | Stores user role information and permissions |
| Departments | Stores department details for users |
| Notifications | Stores system notifications and leave status updates |

# ER Diagram

## Description

🔸This ER Diagram represents the database structure of the Leave Management System. It shows the relationship between Student, Staff, HOD, Principal, and Leave Request entities.

## Diagram

![ER Diagram](file_00000000d504720895087c8a6b959c78.png)

# SQL Schema

## Description

🔸This SQL schema defines the database structure for the Leave Management System. It includes tables for users and leave requests, along with the necessary fields required for managing the leave approval workflow.

## Users Table

```sql
CREATE TABLE users (
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    email VARCHAR(100),
    password VARCHAR(100),
    role VARCHAR(20)
);
```

## Leave Requests Table

```sql
CREATE TABLE leave_requests (
    leave_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    leave_type VARCHAR(50),
    from_date DATE,
    to_date DATE,
    reason TEXT,
    status VARCHAR(20),
    FOREIGN KEY (user_id) REFERENCES users(user_id)
);
```
