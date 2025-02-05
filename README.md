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

##

