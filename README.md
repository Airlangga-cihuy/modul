# Modul AIR dan Yoga
**TAG**= *Tutorial membuat s3 bucket, Database, Dan 3 instance*

---

![ftoo gambar](https://github.com/Airlangga-cihuy/modul/blob/main/topologi.jpg?raw=true)

---

## MEMBUAT S3 BUCKET

1. Ketik s3 di dashboard
![ftoo gambar](https://github.com/Airlangga-cihuy/modul/blob/main/s3.png)
3. Kemudian *KLIK CREATE BUCKET*
4. Masukan nama bucket
5. Matikan block all access
6. Ceklis kotak kuning dibawahnya
7. Kemudian *create bucket*

---

## UPLOAD FILE DI S3 BUCKET
![ftto gambar](https://github.com/Airlangga-cihuy/modul/blob/main/S3bucket.png)
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

## Membuat security group
1. Kemenu ec2
2. Cari security group
3. Create security group
![ftto gambar](https://github.com/Airlangga-cihuy/modul/blob/main/sg.png)
5. NAMA: *SGLATIHANUPRAKNAMAKAMU*
6. Decription:bebas
7. VPC: Default
8. Inbound rules:->SSH->HTTP->HTTPS->POSTGRESQL
9. Destination:*ANYWHERE-IPV4
10. Create security group

---

 ## CREATE RDS
**TAG**= Sebelum membuat rds harap membuat security group terlebih dahulu di ec2
 1. Ketik *RDS* di dashboard
![ftto gambar](https://github.com/Airlangga-cihuy/modul/blob/main/RDS.jpg)
 3. Klik *RDS*
 4. Pilih *STANDART CREATE*
 5. Engine options =*POSGRESQL*
 6. Engine version = bebas
 7. Template = free tier
 8. DB INSTANCE IDENTIFIER = nama database yang dibuat
 9. Master username =*POSTGRES*
 10. Master pasword = *BEBAS*
 11. Confirm pasword = Seperti master pasword
 12. Instance configuration = db.t3.micro
 13. STORAGE = 20GB
 14. Public access = yes
 15. Vpc security group =yang kalian buat tadi
 16. KLIK *CREATE RDS*

---

## Cara remote dengan aplikasi *pgadmin*
**NOTE**=*SEBELUM MASUK KE LANGKAH INI HARAP DOWNLOAD DULU PGADMIN DIGOOGLLE*

---

1. Buka aplikasi *PGADMIN*
2. Klik *ADD SERVER*
![ftto gambar](https://github.com/Airlangga-cihuy/modul/blob/main/pgadmin.jpg)
4. Nama: sesuai nama database kalian
5. Klik menu *CONNECTION*
6. Hostname/address: isi endpoint database server yang dibuat di aws
7. Port:5342
8. Username:*POSTGRES*
9. Pasword:*LATIHAN123*
10. Save

 ---

 ## Cara melihat endpoint
 1. Ketik *RDS*
![ftto gambar](https://github.com/Airlangga-cihuy/modul/blob/main/RDS%201.jpg)
 3. Klik database yang sudah kalian buat
 4. Cari menu *CONNECTIVITY & SECURITY*
 5. Scrool kebawah dan cari *ENDPOINT & PORT*
 6. Cari *ENDPOINT*
![ftto gambar](https://github.com/Airlangga-cihuy/modul/blob/main/RDS%202.jpg)
 8. Kemudian copy

---

## Membuat load balancer

---
## Membuat instance
1. Pergi ke menu *EC2*
![ftto gambar](https://github.com/Airlangga-cihuy/modul/blob/main/EC2.jpg)
3. Klik *INSTANCES*
4. Klik *LAUNCH INSTANCES*
5. Name:bebas
6. Number of instance:3
7. OS:UBUNTU
8. Keypair:vockey
9. Allow SSH traffic from: *CENTANG*
10. Allow HTTPS traffic from the internet: *CENTANG*
11. Allow HTTP traffic from the internet: *CENTANG*
12. *LAUNCH INSTANCE*
13. Kemudian namai ke tiga instance tadi
14. Untuk yang pertama berikan nama *LB* dan sisanya berikan nama *WEB 1 DAN WEB 2*

---

## Elastic IP addresses
1. Cari ec2
2. Cari elastic ip addresses
![ftto gambar](https://github.com/Airlangga-cihuy/modul/blob/main/elastic%20ip%201.jpg)
4. Allocate elastis ip addreses
5. Allocate
6. Klik Associate Elastic IP address
![ftto gambar](https://github.com/Airlangga-cihuy/modul/blob/main/elastic%20ip%202.jpg)
8. Instance: Pilih *INSTANCE LB*
9. Private IP address: Pilih yang tersedia
10. Klik asociate


##

---

## Setting LB
1. Klik instance *LB*
2. Connect
3. Kemudian Klik file bernama *LB* digithub saya atau masuk ke web modul.studentsakti.web.id dan cari *MODUL LOAD BALANCER DI NGINX*
4. Dikonfigurasi cari *IP PUBliC 1 & 2*
![ftto gambar](https://github.com/Airlangga-cihuy/modul/blob/main/LB%201.jpg)
6. Hapus kalimat *IP PUBLIC 1 & 2*
7. Kemudian ganti dengan ip private dari instance web 1 & 2

---

## Setting web 1 & 2
1. Klik web 1
2. Connect
3. Kemudian ke web dan cari modul.studentsakti.web.id dan cari *INTALASI EC2 DIAWS
4. Ikuti langkah-langkah dimodul tersebut
5. Ketika sudah masuk kedalam konfigurasinya perhatikan!
![ftto gambar](https://github.com/Airlangga-cihuy/modul/blob/main/WEB%201.jpg)
7. "Alamat endpoint dari rds"."nama database yang dibuat dipgadmin."username rds"."pasword rds"
8. Isi sesuai dengan konfigurasi di rds
9. Kemudian lakukan hal sama pada web ke 2

---

## DUCKDNS
1. Ketik digoogle dan cari *DUCKDNS*
2. Kemudian login dengan akun google
3. Kemudian di*sub domain* dan ketik *LATIHANUPRAKNAMAKAMU*
4. Klik *ADD DOMAIN*
5. Pada domain dinama memasukan nama kemudian masukkan ip public dari instance lb
![ftto gambar](https://github.com/Airlangga-cihuy/modul/blob/main/DUCKDNS.jpg)
7. Klik update ip
8. Kemudian copy
9. Masuk lagi kedalam konfigurasi lb
10. kemudian cari kalimat *HOSTNAME*
11. Laku ganti dengan copy an dari duckdns tadi
12. Kemudian restart lb dan test diinternet






