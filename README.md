
# 🚗 Car Rental Web App

A simple **Car Rental Web Application** built using **Flask (Python)** and **MySQL**.
This project allows users to browse cars, search, rent vehicles, and manage bookings with role-based access (**Admin & Member**).

---

## ✨ Features

### 👤 Authentication

* User registration & login
* Role-based access:

  * **Member** → Rent cars & view history
  * **Admin** → Approve/reject rental requests

### 🚘 Car Management

* View all available cars
* Search cars by name (AJAX-based search)
* Detailed car information page

### 📅 Booking System

* Rent a car (7 days default rental)
* Booking status:

  * Waiting Approval
  * Approved
  * Rejected

### 🛠 Admin Panel

* View all pending bookings
* Approve / Reject rental requests

---

## 🧠 Tech Stack

* **Backend:** Flask (Python) 
* **Database:** MySQL (mysql-connector) 
* **Frontend:** HTML, CSS, Bootstrap
* **Template Engine:** Jinja2

---

## ⚠️ IMPORTANT WARNING

> ⚠️ **BEFORE RUNNING THE PROJECT**
>
> You MUST change your MySQL credentials in:
>
> ```python
> database.py
> ```
>
> Specifically this part:
>
> ```python
> self.conn = mysql.connector.connect(
>     host="localhost",
>     user="root",
>     password="YOUR_PASSWORD_HERE"
> )
> ```
>
> If not changed, the app will fail to connect to the database.

---

## 📁 Project Structure

```
project/
│
├── main.py               # Flask application (routes & logic)
├── database.py           # Database connection & queries
│
├── templates/
│   ├── HomePage.html
│   ├── Cars.html
│   ├── CarDetail.html
│   ├── Login.html
│   ├── Register.html
│   ├── Rental_History.html
│   ├── Rent_Approval.html
│   └── (other HTML files)
│
├── static/
│   ├── css files
│   ├── Images/
│   │   ├── car1.jpeg
│   │   ├── car2.jpeg
│   │   └── ...
│   └── other assets
│
└── README.md
```


## 🗄 Database Schema

Database akan otomatis dibuat saat pertama kali dijalankan.

### Tables:

* **Account**
* **Car**
* **Booking**

Relasi:

* Booking → Account (user_id)
* Booking → Car (car_id)

Default data juga langsung diinsert (akun & mobil) 

---

## 🔄 Application Flow

### 1. Homepage

* Landing page (`/`) 

### 2. Explore Cars

* `/explore`
* Menampilkan semua mobil 

### 3. Search

* AJAX fetch → `/search`
* Hasil langsung render ulang halaman

### 4. Car Detail

* `/detail/<car_id>` 

### 5. Rental

* `/rental/<car_id>`
* Harus login dulu
* Auto booking 7 hari

### 6. Account Page

* Member → History rental
* Admin → Approval page

---

## 🚀 How to Run

### 1. Install dependencies

```bash
pip install flask mysql-connector-python
```

### 2. Setup MySQL

* Pastikan MySQL running
* Ubah credential di `database.py`

### 3. Run application

```bash
python main.py
```

### 4. Open browser

```
http://127.0.0.1:5000/
```

---

## 🔑 Default Accounts

| Role   | Email                                         | Password |
| ------ | --------------------------------------------- | -------- |
| Member | [member1@gmail.com](mailto:member1@gmail.com) | aaaa     |
| Admin  | [admin1@gmail.com](mailto:admin1@gmail.com)   | aaaa     |

---

