NUMBER PLATE DETECTION

MYSQL CODE
CREATE DATABASE IF NOT EXISTS number_plate_db;
USE number_plate_db;

-- Vehicles table: stores dynamic plate records with toll info
CREATE TABLE IF NOT EXISTS vehicles (
    plate_number VARCHAR(20) PRIMARY KEY,
    balance DECIMAL(10,2) DEFAULT 100.00,   -- Default balance for new plates
    toll_amount DECIMAL(10,2) DEFAULT 30.00 -- Default toll for new plates
);

-- Detection logs (optional)
CREATE TABLE IF NOT EXISTS plates (
    id INT AUTO_INCREMENT PRIMARY KEY,
    plate_number VARCHAR(20),
    confidence INT,
    timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Toll deduction logs
CREATE TABLE IF NOT EXISTS transactions (
    id INT AUTO_INCREMENT PRIMARY KEY,
    plate_number VARCHAR(20),
    deducted_amount DECIMAL(10,2),
    remaining_balance DECIMAL(10,2),
    timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
SELECT * FROM transactions ORDER BY timestamp DESC;

<img width="1366" height="726" alt="Number Platee" src="https://github.com/user-attachments/assets/0c82b9cf-42c4-4994-b9e5-b64508e1a841" />
<img width="1366" height="722" alt="Number Plate" src="https://github.com/user-attachments/assets/9998feb5-2d40-4962-86ac-3a7b754d3ca3" />
