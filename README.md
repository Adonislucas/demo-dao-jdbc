# 📋 JDBC Project: Seller and Department Management

## 📌 Overview
Java application demonstrating pure JDBC implementation for:
- Complete CRUD operations for `Seller` and `Department` entities
- Database relationships (Seller-Department)
- MySQL database connectivity
- DAO (Data Access Object) pattern

## 🛠 Technologies
- **Java 11+**
- **JDBC** (Java Database Connectivity)
- **MySQL Connector/J** 8.0+
- **MySQL Server** 5.7+

## 🗂 Project Structure
src/
├── application/
│ ├── Program.java # Tests Seller CRUD operations
│ └── Program2.java # Tests Department CRUD operations
├── db/
│ ├── DB.java # Connection manager
│ ├── DbException.java
│ └── DbIntegrityException.java
├── model/
│ ├── entities/
│ │ ├── Department.java
│ │ └── Seller.java
│ └── dao/
│ ├── DepartmentDao.java
│ └── SellerDao.java
└── impl/
├── DaoFactory.java
├── DepartmentDaoJDBC.java
└── SellerDaoJDBC.java



## ⚙️ Configuration
1. Create `db.properties`:
```properties
db.url=jdbc:mysql://localhost:3306/your_database?useSSL=false&serverTimezone=UTC
db.user=your_username
db.password=your_password
Database schema:

sql
CREATE TABLE department (
    Id INT PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(60) NOT NULL
);

CREATE TABLE seller (
    Id INT PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(60) NOT NULL,
    Email VARCHAR(100) NOT NULL,
    BirthDate DATETIME NOT NULL,
    BaseSalary DOUBLE NOT NULL,
    DepartmentId INT NOT NULL,
    FOREIGN KEY (DepartmentId) REFERENCES department(Id)
);

▶️ How to Run
Testing Seller CRUD (Program.java)
java
// Example test cases:
// 1. findById
// 2. findByDepartment
// 3. findAll
// 4. insert
// 5. update
// 6. delete

Testing Department CRUD (Program2.java)
java
// Example test cases:
// 1. findById
// 2. findAll
// 3. insert
// 4. update
// 5. delete


