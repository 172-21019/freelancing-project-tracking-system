
# 💼 Freelancer Project Tracker

A Java-based desktop application to manage and track freelance projects efficiently. Built using Java Swing and MySQL, this system supports role-based access for Admin and Clients, offering seamless project assignment, tracking, and feedback features.

---

## 📌 Features

### 🔐 Role-Based Login
- **Admin**
  - View all project details
  - Assign projects to clients
  - Track project statuses (Pending / Accepted / Completed)

- **Client**
  - View projects assigned to them
  - Accept or reject projects
  - Mark projects as completed
  - Upload files or attachments
    

---

## 🧱 Tech Stack

- **Frontend**: Java Swing (GUI)
- **Backend**: Java
- **Database**: MySQL
- **IDE**: Eclipse / IntelliJ / NetBeans

---

## 📂 Project Structure

```
freelancer/
│
├── src/
│   ├── login/               # Login and Signup Forms
│   ├── admin/               # Admin Dashboard
│   ├── client/              # Client Dashboard
│   ├── db/                  # Database connection logic
│   └── models/              # Reusable data models
│
├── sql/                     # SQL schema and seed files
├── assets/                  # Icons, images, etc.
├── README.md
```

---

## 🗃️ Database Schema

### 1. `credentials`
Stores login information and roles.
```sql
id INT PRIMARY KEY AUTO_INCREMENT
username VARCHAR(100) UNIQUE
password VARCHAR(100)
role VARCHAR(50)  -- admin or client
```

### 2. `users`
Stores personal details, linked to `credentials`.
```sql
user_id INT PRIMARY KEY  -- FK to credentials(id)
user_name VARCHAR(100)
phone_number VARCHAR(15)
email VARCHAR(100)
gender VARCHAR(10)
city VARCHAR(50)
```

### 3. `projects`
Tracks project information.
```sql
id INT PRIMARY KEY AUTO_INCREMENT
title VARCHAR(100)
description TEXT
assignedTo VARCHAR(50) -- username of the client
status VARCHAR(50)
```

### 4. `count_of_projects`
Tracks number of accepted and completed projects per client.
```sql
client_id INT PRIMARY KEY AUTO_INCREMENT
client_name VARCHAR(100) UNIQUE
count_of_accepted INT
count_of_completed INT
```

---

## 🧪 How to Run

### ✅ Prerequisites

- Java JDK 8+
- MySQL Server
- JDBC Driver (already included in most IDEs)
- Eclipse / IntelliJ

### ⚙️ Setup Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/freelancer.git
   cd freelancer
   ```

2. **Import Project**
   - Open in Eclipse/IntelliJ as a Java project.
   - Make sure MySQL is running.

3. **Set Up Database**
   - Import the SQL file (`freelancer_db.sql`) using MySQL Workbench or CLI.
   - Update DB credentials in `db/DbConnection.java`.

4. **Run the Application**
   - Right-click `LoginPage.java` → Run As → Java Application.

---

## 🧑‍💼 Roles in Action

| Role   | Can Assign Projects | Can Accept/Complete Projects | Can Give Feedback | Can View All |
|--------|---------------------|------------------------------|-------------------|--------------|
| Admin  | ✅ Yes              | ❌ No                         | ✅ Yes            | ✅ Yes       |
| Client | ❌ No               | ✅ Yes                        | ✅ Yes            | ❌ No        |

---

## 📸 Screenshots
-Login Page
>![image](https://github.com/user-attachments/assets/99661c25-2eb2-4f2e-b60c-28cf48ed563c)

-Sign up page
>![image](https://github.com/user-attachments/assets/5967730a-94bf-442c-92eb-888c38208728)

-Admin dashboard
>![image](https://github.com/user-attachments/assets/24ec3a22-ad67-42c3-87ef-4981b9013f2d)

-Client dashboard
>![image](https://github.com/user-attachments/assets/4afbfc26-5fd3-477a-b6bc-14afc03abd84)

-count_of_projects
>![image](https://github.com/user-attachments/assets/4f12072f-b887-4854-8a76-b8627a8521ab)


---

## 📌 Future Enhancements

- Notification system
- Auto email alerts
- Graphical analytics dashboard
- PDF reports

---

## 🙋‍♂️ Author

**K Manoj**  
- 📧 k.manoj2522005@gmail.com  
- 🌐 [LinkedIn](https://www.linkedin.com/in/k-manoj-a39a48277)  
- 💻 [GitHub](https://github.com/172-21019)
