# minio-bigdata
ingestion big data

langkah-langkah berikut untuk menjalankan pipeline data:


### 1️⃣ Persiapan Environment

Pastikan:
- Docker Desktop sudah **running**
- Fitur **Virtualization** sudah aktif di BIOS

Install library Python yang dibutuhkan:


pip install pandas sqlalchemy psycopg2-binary openpyxl minio jupyter

### 2️⃣ Deployment Infrastruktur

Jalankan layanan PostgreSQL dan MinIO menggunakan Docker Compose:

docker compose up -d

Akses service:

PostgreSQL → localhost:5432
MinIO Console → http://localhost:9001
MinIO API → http://localhost:9000


### 3️⃣ Inisialisasi & Ingestion

Buka Jupyter Notebook, lalu jalankan script secara bertahap:

Inisialisasi Database
Membuat tabel dan insert data ke PostgreSQL
Generate Dataset Lokal
Membuat file:
products.csv
orders_source.xlsx
Proses Ingestion
Jalankan fungsi upload_to_minio untuk:
Mengambil data dari PostgreSQL
Upload file lokal
Menyimpan ke MinIO


### 4️⃣ Verifikasi

Buka browser:
http://localhost:9001

Login menggunakan kredensial dari docker-compose.yml, lalu pastikan file sudah masuk ke:

raw/
├── rdbms/
├── csv/
└── xlsx/
