# How-to-Set-Up-a-Secure-MySQL-Connection-in-FiveM-2025-Using-oxmysql
This article explains how to configure a secure MySQL connection string for a FiveM server in 2025 using oxmysql, including enabling debug and query time logging.
---

## ✅ Requirements

Before starting, make sure you have:

- A FiveM server running the latest recommended build.
- `oxmysql` installed in your resources folder.
- Access to your MySQL or MariaDB database.
- A database user dedicated to your FiveM server (recommended).

---

## 🔧 1. Installing oxmysql

Download the latest version from GitHub : https://github.com/overextended/oxmysql 

Place the folder in:

resources/[ox]/oxmysql

pgsql
Copier le code

Then add this line in your `server.cfg`:

ensure oxmysql

yaml
Copier le code

---

## 🔐 2. Setting the MySQL Connection String (2025 Format)

oxmysql uses a modern URL-style connection string.  
Here is the cleaned and readable version:

set mysql_connection_string "mysql://database_user.database_password@database_host:3306/database_name?charset=utf8mb4"

pgsql
Copier le code

### 🔎 Breakdown of the Connection String

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

## 🐞 3. Enabling MySQL Debug Mode

Debug mode prints every SQL query in your server console.  
Useful for development or when you’re debugging scripts.

set mysql_debug true

yaml
Copier le code

---

## ⏱️ 4. Showing Query Execution Time

This helps you detect slow or heavy queries:

set mysql_show_query_time 1

yaml
Copier le code

---

## 🧩 5. Full Example Configuration

Here is a complete, clean, production-ready example of what your `server.cfg` could look like:

ensure oxmysql

set mysql_connection_string "mysql://database_user.database_password@10.0.0.20:3306/fivem_database?charset=utf8mb4"
set mysql_debug true
set mysql_show_query_time 1

yaml
Copier le code

---

## 🧪 6. Testing the Database Connection

Restart your FiveM server.  
If the connection works, you should see:

[oxmysql] connection established

yaml
Copier le code

If not, check:

- Wrong username/password
- Incorrect database name
- Firewall blocking port 3306
- MySQL user not allowed to connect remotely
- Missing permissions (SELECT, INSERT, UPDATE, DELETE…)

---

## 🔐 Security Tips

To keep your FiveM environment secure:

- Use a **strong password** for your MySQL user.
- Avoid using the root account.
- Restrict the MySQL user to your FiveM server’s IP only.
- Do NOT expose port 3306 publicly without a firewall.
- Use `ufw`, pfSense, or OPNsense to restrict access.
- Keep backups of your database.

---

## ✔️ Final Notes

This configuration is fully compatible with FiveM in 2025 and follows the recommended practices for oxmysql.  
It’s simple, reliable, and easy to maintain.

If you need extra help — such as testing queries, optimizing your database, or creating sample scripts 
