# How-to-Set-Up-MySQL-Connection-in-FiveM-2025-Using-oxmysql
This article explains how to configure a secure MySQL connection string for a FiveM server in 2025 using oxmysql.
---

## ✅ Requirements

Before starting, make sure you have:

- A FiveM server running the latest recommended build.
- `oxmysql` installed in your resources folder.
- Access to your MySQL or MariaDB database.
- A database user dedicated to your FiveM server (recommended).

---

##  1. Installing oxmysql

Download the latest version from GitHub : https://github.com/overextended/oxmysql 

Place the folder in:

resources/[ox]/oxmysql

Copier le code

Then add this line in your `server.cfg`:

`ensure oxmysql`

---

##  2. Setting the MySQL Connection String (2025 Format)

oxmysql uses a modern URL-style connection string.  
```cfg
set mysql_slow_query_warning 150
set mysql_connection_string "mysql://database_user:database_password@database_host:3306/database_name?charset=utf8mb4"
set mysql_debug 0
```

Copier le code

###  Breakdown of the Connection String

| Key | Description |
|-----|-------------|
| `database_user` | Your MySQL username |
| `database_password` | Your MySQL password |
| `database_host` | Your database IP or domain |
| `3306` | Default MySQL port |
| `database_name` | The database the server should use |
| `charset=utf8mb4` | Required for emojis and special characters |

This format is the recommended way for oxmysql in 2025.

---
##  3. Testing the Database Connection

Restart your FiveM server.  
If the connection works, you should see:
```Console 
[oxmysql] connection established
```

If not, check:

- Wrong username/password
- Incorrect database name
- Firewall blocking port 3306
- MySQL user not allowed to connect remotely
- Missing permissions (SELECT, INSERT, UPDATE, DELETE…)

---
This article is made with an ai for the correction. 
