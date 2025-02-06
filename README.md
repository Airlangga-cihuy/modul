# Modul AIR dan Yoga
**TAG**= *Tutorial membuat s3 bucket, Database, Dan 3 instance*

---

![ftoo gambar](https://github.com/Airlangga-cihuy/modul/blob/main/topologi.jpg?raw=true)

---

## MEMBUAT S3 BUCKET

1. Ketik s3 di dashboard
2. Kemudian *KLIK CREATE BUCKET*
3. Masukan nama bucket
4. Matikan block all access
5. Ceklis kotak kuning dibawahnya
6. Kemudian *create bucket*

---

## UPLOAD FILE DI S3 BUCKET
1. Cari minimal 2 gambar di google dan simpan di file JPG
2. Klik Add files
3. pilih file lalu, klik file yang akan di updoad
4. di browser ketik (bit.ly/latihan aws)
5. ke bucket, klick bucket police
6. permission police->edit->copy
7. Policy=paste
8. (Bucket_name) ganti dengan nama kalian
9. Save Change 
10. Object -> Gambar di copy dan paste ke Browser

    ---

 ## CREATE RDS
**TAG**= Sebelum membuat rds harap membuat security group terlebih dahulu di ec2
 1. Ketik *RDS* di dashboard
 2. Klik *RDS*
 3. Pilih *STANDART CREATE*
 4. Engine options =*POSGRESQL*
 5. Engine version = bebas
 6. Template = free tier
 7. DB INSTANCE IDENTIFIER = nama database yang dibuat
 8. Master username =*POSTGRES*
 9. Master pasword = *BEBAS*
 10. Confirm pasword = Seperti master pasword
 11. Instance configuration = db.t3.micro
 12. STORAGE = 20GB
 13. Public access = yes
 14. Vpc security group =yang kalian buat tadi
 15. KLIK *CREATE RDS*

---

## Cara remote dengan aplikasi *pgadmin*
**NOTE**=*SEBELUM MASUK KE LANGKAH INI HARAP DOWNLOAD DULU PGADMIN DIGOOGLLE*

---

1. Buka aplikasi *PGADMIN*
2. Klik *ADD SERVER*
3. Nama: sesuai nama database kalian
4. Klik menu *CONNECTION*
5. Hostname/address: isi endpoint database server yang dibuat di aws
6. Port:5342
7. Username:*POSTGRES*
8. Pasword:*LATIHAN123*
9. Save

 ---

 ## Cara melihat endpoint
 1. Ketik *RDS*
 2. Klik database yang sudah kalian buat
 3. Cari menu *CONNECTIVITY & SECURITY*
 4. Scrool kebawah dan cari *ENDPOINT & PORT*
 5. Cari *ENDPOINT*
 6. Kemudian copy

---

## Membuat load balancer

---
## Membuat instance
1. Pergi ke menu *EC2*
2. Klik *INSTANCES*
3. Klik *LAUNCH INSTANCES*
4. Name:bebas
5. Number of instance:3
6. OS:UBUNTU
7. Keypair:vockey
8. Allow SSH traffic from: *CENTANG*
9. Allow HTTPS traffic from the internet: *CENTANG*
10. Allow HTTP traffic from the internet: *CENTANG*
11. *LAUNCH INSTANCE*
12. Kemudian namai ke tiga instance tadi
13. Untuk yang pertama berikan nama *LB* dan sisanya berikan nama *WEB 1 DAN WEB 2*

---

## Setting
1. Klik instance *LB*
2. Connect
3. Kemudian






