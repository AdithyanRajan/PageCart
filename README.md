# Online Bookstore

A user-friendly **Online Bookstore** where users can log in or register, view available books, select books along with their quantity, and purchase them. Users receive a payment receipt after a successful transaction. Admins can manage books, prices, and selling history.

## Features

### **For Users:**
- Register and log in
- View available books
- Select books and quantity
- Buy books
- Receive payment receipt

### **For Admins:**
- Add new books
- View available books
- Remove books
- Increase or decrease book quantity
- Change book prices
- Maintain selling history

## Technologies Used

### **Frontend:**
- HTML
- CSS
- JavaScript
- Bootstrap

### **Backend:**
- Java (JDK 8+)
- JDBC
- Servlets

### **Database:**
- MySQL

## Prerequisites

Ensure you have the following installed:
- [Git](https://git-scm.com/)
- [Java JDK 8+](https://www.oracle.com/java/technologies/javase-downloads.html)
- [Eclipse EE](https://www.eclipse.org/downloads/packages/release/2023-06/r/eclipse-ide-enterprise-java-and-web-developers)
- [Apache Maven](https://maven.apache.org/install.html)
- [Tomcat v8.0+](https://tomcat.apache.org/download-80.cgi)
- [MySQL Server](https://dev.mysql.com/downloads/mysql/)
- [MySQL Workbench (Optional)](https://www.mysql.com/products/workbench/)

## Database Setup

1. Open MySQL Command Prompt or MySQL Workbench
2. Login to the administrator user:
   ```sh
   mysql -u <username> -p
   ```
3. Run the following SQL commands:
   ```sql
   CREATE DATABASE IF NOT EXISTS onlinebookstore;
   USE onlinebookstore;

   CREATE TABLE IF NOT EXISTS books (
       barcode VARCHAR(100) PRIMARY KEY,
       name VARCHAR(100),
       author VARCHAR(100),
       price INT,
       quantity INT
   );

   CREATE TABLE IF NOT EXISTS users (
       username VARCHAR(100) PRIMARY KEY,
       password VARCHAR(100),
       firstname VARCHAR(100),
       lastname VARCHAR(100),
       address TEXT,
       phone VARCHAR(100),
       mailid VARCHAR(100),
       usertype INT
   );

   INSERT INTO books VALUES ('9780134190563','The Go Programming Language','Alan A. A. Donovan and Brian W. Kernighan',400,8);
   INSERT INTO books VALUES ('9780133053036','C++ Primer','Stanley Lippman and Josée Lajoie and Barbara Moo',976,13);
   INSERT INTO users VALUES ('Admin', 'Admin', 'Mr.', 'Admin', 'Haldia WB', '9584552224521', 'admin@gmail.com', 1);
   INSERT INTO users VALUES ('shashi', 'shashi', 'Shashi', 'Raj', 'Bihar', '1236547089', 'shashi@gmail.com', 2);
   
   COMMIT;
   ```

## Project Setup

### **Cloning the Repository**
```sh
git clone https://github.com/AdithyanRajan/PageCart/.git
cd PageCart
```

### **Importing and Running in Eclipse EE**

1. Open **Eclipse Enterprise Edition**
2. Click **File > Import > Git > Projects from Git > Clone URI**
3. Paste the repository URL: `https://github.com/AdithyanRajan/PageCart.git`
4. Select the **master branch** > Next > Finish
5. Navigate to `src/main/resources/application.properties` and update database credentials
6. Right-click on the project > **Run As > Maven Build**
   - Enter the goals: `clean install`
   - Apply > Run
7. If required, configure Tomcat Server:
   - **Right-click on project > Run As > Run on Server > Select Tomcat v8.0 > Next > Add onlinebookstore > Finish**
   - In **Server Tab**, double-click **Tomcat Server** > Change **HTTP port to 8083** > Save
8. Run the project on Tomcat Server:
   ```sh
   http://localhost:8083/onlinebookstore/
   ```
9. **Admin Login:** Username: `Admin`, Password: `Admin`
10. **User Login:** Username: `adi`, Password: `adi`
