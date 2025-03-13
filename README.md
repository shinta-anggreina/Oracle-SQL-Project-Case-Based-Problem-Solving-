# 🏛️ Oracle SQL Project: Case-Based Problem Solving

## 📌 Overview
Proyek ini berisi berbagai kasus dan penyelesaian berbasis **Oracle SQL**, mencakup fundamental hingga implementasi tingkat lanjut. Setiap kasus mencerminkan tantangan nyata dalam pengelolaan database, mulai dari **manipulasi data, pembuatan tabel, optimasi query**, hingga pemrosesan teks, angka, dan tanggal.

### 🔹 Tools & Technologies:
- 🗄️ **Oracle SQL** 
- 📊 **Database Management**
- 🚀 **Data Manipulation & Query Optimization**
- 🔠 **String Functions & Data Type Conversion**

---

## 📂 Project Structure

### 📌 1. Fundamental Oracle SQL
✅ Menampilkan & memfilter data dalam tabel  
✅ Manipulasi string dan angka  
✅ Konversi data antar tipe (string ↔️ number)  
✅ Pengelolaan tanggal & waktu  
✅ Penggunaan **GROUP BY**, **HAVING**, **ORDER BY**  

### 📌 2. Create Table & Import Data
✅ Pembuatan tabel untuk sistem transaksi  
✅ Input data dengan validasi tipe data  
✅ Query pencarian dengan filter dinamis  
✅ Implementasi pencarian case-insensitive  
✅ **Role-Based Data Access** dengan query bersyarat  

---

## 🚀 Implemented Case Studies & Solutions

### 🔹 1️⃣ Data Retrieval & Filtering
📌 **Menampilkan semua data dalam tabel tertentu**
```sql
SELECT * FROM COL$;
```
📌 **Menampilkan kolom dengan alias yang lebih deskriptif**
```sql
SELECT COL# AS "COLUMN", Name AS "NAME_COL$", Length AS "LENGTH_COL$"
FROM COL$;
```
📌 **Mencari subkategori produk yang mengandung kata "bike" (case-insensitive search)**
```sql
SELECT * FROM PTBL_SUBCATEGORY 
WHERE LOWER(SUBCATEGORY_NAME) LIKE '%bike%';
```

### 🔹 2️⃣ Data Aggregation & Filtering Conditions
📌 **Menghitung jumlah kemunculan data yang sama & mengurutkan hasilnya**
```sql
SELECT Name, COUNT(Name) AS Total_Name
FROM COL$
WHERE COL# = 10
GROUP BY Name
HAVING COUNT(Name) > 5
ORDER BY Total_Name DESC;
```
📌 **Filter berdasarkan ID kategori produk**
```sql
SELECT * FROM PTBL_CATEGORY WHERE PRODUCT_CATEGORY_ID <> 2;
SELECT * FROM PTBL_CATEGORY WHERE PRODUCT_CATEGORY_ID <= 2;
SELECT * FROM PTBL_CATEGORY WHERE PRODUCT_CATEGORY_ID BETWEEN 3 AND 5;
```

### 🔹 3️⃣ Database Management (DDL & DML)
📌 **Membuat tabel transaksi produk**
```sql
CREATE TABLE ptbl_Transaction (
    TRANSACTION_ID DECIMAL(6,0) NOT NULL,
    PRODUCT_ID DECIMAL(3,0) NOT NULL,
    REFERENCE_ORDER_ID DECIMAL(5,0) NOT NULL,
    TRANSACTION_DATE DATE NOT NULL,
    TRANSACTION_TYPE CHAR(1) NOT NULL,
    QUANTITY DECIMAL(4) NOT NULL,
    ACTUAL_COST DECIMAL(8,4)
);
```
📌 **Menambahkan data dummy untuk kategori produk**
```sql
INSERT INTO ptbl_Category (PRODUCT_CATEGORY_ID, CATEGORY_NAME)
VALUES (1, 'Bicycles'), (2, 'Accessories'), (3, 'Clothing'), (4, 'Components');
```
📌 **Menghapus data dalam tabel tanpa menghapus strukturnya**
```sql
TRUNCATE TABLE TBL_NUMERIC;
```
📌 **Menghapus tabel secara permanen**
```sql
DROP TABLE TBL_NUMERIC;
```

### 🔹 4️⃣ String Manipulation & Data Conversion
📌 **Mengubah teks "billionaire" menjadi "TRILLIONAIRE"**
```sql
SELECT REPLACE('Hello im a billionaire *****', 'billionaire', 'TRILLIONAIRE') AS Result
FROM DUAL;
```
📌 **Mengubah angka menjadi format mata uang lokal (Rupiah)**
```sql
SELECT 'The price of this laptop Rp.' || TO_CHAR(128450000, 'fm999,999,999.99') || '00' AS RESULT
FROM DUAL;
```

### 🔹 5️⃣ Date & Time Processing
📌 **Menampilkan tanggal saat ini dan minggu ke berapa dalam bulan ini**
```sql
SELECT SYSDATE AS Current_Date, 
       TO_NUMBER(TO_CHAR(SYSDATE, 'W')) AS Week_Of_Month
FROM DUAL;
```
📌 **Membuat tabel tanggal dan menampilkan hari pertama setiap bulan**
```sql
CREATE TABLE TBL_DATE (
    MYDATE DATE
);

INSERT INTO TBL_DATE VALUES (TO_DATE('20-MAR-2024', 'DD-MON-YYYY'));
INSERT INTO TBL_DATE VALUES (TO_DATE('2024-02-15', 'YYYY-MM-DD'));
INSERT INTO TBL_DATE VALUES (TO_DATE('12-Jun-2024', 'DD-MON-YYYY'));

SELECT MYDATE, TRUNC(MYDATE, 'MM') AS First_Day
FROM TBL_DATE;
```

---

## 🎯 Key Takeaways
✅ **Fundamental SQL Mastery** → Menggunakan query SQL untuk manipulasi data secara efisien  
✅ **Problem Solving** → Menganalisis dan menyelesaikan permasalahan database yang umum terjadi  
✅ **Case Sensitivity & Data Validation** → Mengoptimalkan pencarian data dengan filter yang tepat  
✅ **Date & String Processing** → Konversi dan manipulasi data numerik, teks, dan tanggal  
✅ **Data Security & Optimization** → Menerapkan query yang optimal untuk pengelolaan database skala besar  

---

## 📢 How to Use This Repository
1. Clone repo ini ke lokal:
   ```bash
   git clone https://github.com/shineko.art/oracle-sql-project.git
   ```
2. Jalankan query di **Oracle SQL Developer** atau **SQL Plus**
3. Eksperimen dengan berbagai skenario tambahan! 🚀

---

## 👩‍💻 About the Author
👋 **Shinta Anggreina**  
📌 Fresh Graduate | Data Enthusiast | Ex-Student Data Engineer at Metrodata Academy   
📧 **Email:** shintaanggreina@gmail.com  

✨ *Happy coding & keep learning!* 🚀
