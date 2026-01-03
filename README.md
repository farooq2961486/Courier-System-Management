===============================================================
          COURIER MANAGEMENT SYSTEM - README
===============================================================

Project Name: Simple Courier Management System
Developer: Grok (with love for bhai)
Date: January 02, 2026
Language: PHP + MySQL
Framework: Pure PHP (Bootstrap 5 for design)
Folder Name: couriersystem (no space)

---------------------------------------------------------------
1. SYSTEM OVERVIEW
---------------------------------------------------------------
Yeh ek simple lekin powerful courier management system hai jo chhote-medium courier business ke liye perfect hai.

Main Features:
- Login with OTP (testing ke liye screen par dikhta hai)
- Dashboard with stats (Total Parcels, Delivered, In-Transit etc.)
- Orders page – new parcel add karo, status update karo, search karo
- Reports page – charts + CSV export
- Notifications – new parcel ya status change par alert
- Dedicated Notifications page
- Tech Support page – ticket submit karo aur admin manage kare
- Settings page – profile aur password change
- Beautiful modern design (green/teal theme)

---------------------------------------------------------------
2. REQUIREMENTS
---------------------------------------------------------------
- XAMPP / LAMP / WAMP (Apache + MySQL + PHP)
- PHP version 7.4 ya upper (8 bhi chalega)
- MySQL
- Browser (Chrome recommended)

---------------------------------------------------------------
3. INSTALLATION STEPS
---------------------------------------------------------------
1. XAMPP start karo (Apache + MySQL)

2. htdocs folder mein ek folder banao naam: couriersystem

3. Is folder mein yeh sab files paste karo:
   - db_connect.php
   - login.php
   - index.php          (Dashboard)
   - orders.php
   - reports.php
   - notifications.php
   - support.php
   - settings.php
   - logout.php
   - track.php          (public tracking page – optional)

4. Browser mein http://localhost/phpmyadmin kholo

5. New database banao naam: courier_db

6. Is database mein ja kar yeh tables banao (SQL run karo):

-- Parcels table
CREATE TABLE parcels (
    id INT AUTO_INCREMENT PRIMARY KEY,
    tracking_number VARCHAR(20) UNIQUE,
    sender_name VARCHAR(100),
    sender_address TEXT,
    receiver_name VARCHAR(100),
    receiver_address TEXT,
    status VARCHAR(50) DEFAULT 'Pending',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Admins table
CREATE TABLE admins (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(100) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    email VARCHAR(100),
    mobile VARCHAR(15)
);

-- Notifications table
CREATE TABLE notifications (
    id INT AUTO_INCREMENT PRIMARY KEY,
    message TEXT NOT NULL,
    type VARCHAR(50) DEFAULT 'info',
    is_read TINYINT DEFAULT 0,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Support tickets table
CREATE TABLE support_tickets (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL,
    subject VARCHAR(200) NOT NULL,
    message TEXT NOT NULL,
    status VARCHAR(20) DEFAULT 'Open',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

7. Admins table mein apna admin add karo:
INSERT INTO admins (username, password, email, mobile) 
VALUES ('FarooqMurad', 'farooq12345', 'farooq@example.com', '03001234567');

---------------------------------------------------------------
4. LOGIN DETAILS
---------------------------------------------------------------
URL: http://localhost/couriersystem/login.php

Username: FarooqMurad
Password: farooq12345

Login karne ke baad OTP screen par dikhega (testing ke liye) – wo OTP daal do.

---------------------------------------------------------------
5. PAGES AUR UNKE LINKS
---------------------------------------------------------------
- Dashboard:       index.php
- Orders:          orders.php
- Reports:         reports.php
- Notifications:   notifications.php
- Tech Support:    support.php
- Settings:        settings.php
- Logout:          logout.php
- Public Tracking: track.php (tracking number daal kar status dekho)

Sidebar se sab pages accessible hain.

---------------------------------------------------------------
6. IMPORTANT NOTES
---------------------------------------------------------------
- Password direct text mein save hai (learning ke liye simple rakha)
- OTP testing ke liye screen par dikhta hai (real SMS ke liye Twilio add kar sakte hain)
- CSV export reports page par fully working hai
- Sab pages responsive hain (mobile par bhi achay se chalte hain)

---------------------------------------------------------------
7. FUTURE IMPROVEMENTS (agar chaho to add kar sakte ho)
---------------------------------------------------------------
- Real SMS/Email notifications
- Multiple branches/staff
- Customer portal
- Driver mobile app
- Invoice & label printing
- Payment integration
- Dark mode

===============================================================
Mubarak ho bhai! Tera poora courier system ready hai.
Koi issue aaye to bata dena – turant fix kar dunga!
Farooq Murad
+923078113098
if you have any query please contact me
Enjoy! 🚚📦✨
===============================================================
