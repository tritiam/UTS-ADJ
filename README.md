# UTS-ADJ
Tugas UTS ADJ

Nama	: Tritia Mutiara
Nim	: 191402048
Kom	: C

•	Menghubungkan GNS3 ke Internet (Lokas Server)

1.	Kita perlu mendownload Open vSwitch with management dan Cisco 3725 appliance di marketplace GNS3 terlebih dahulu.
 
![1](https://user-images.githubusercontent.com/61776791/138494842-324ea18a-f99f-401e-9fb2-ac8d447c79da.png)
![2](https://user-images.githubusercontent.com/61776791/138494865-87c6711e-3b9d-4390-ba6c-8e0e55c3e8f3.png)
![3](https://user-images.githubusercontent.com/61776791/138494868-fc452ea6-1a43-4840-af71-d0b0173b8a2c.png)

2.	Setelah itu kita mendownload cisco ios image 3725 seperti berikut.

![4](https://user-images.githubusercontent.com/61776791/138494873-389212bc-dd98-48fb-b384-6ff358b474ff.png)

3.	Di GNS3 kita membuat project baru seperti berikut

![5](https://user-images.githubusercontent.com/61776791/138494881-044029e2-2885-446e-8b04-ce1dfee19ac3.png)

4.	Kita import appliance dan cisco ios image 3725 yang sudah kita download ke GNS3

![6](https://user-images.githubusercontent.com/61776791/138494885-f684444d-7d01-4b41-8d26-4957ac04af2e.png)
![7](https://user-images.githubusercontent.com/61776791/138494889-0639617e-f786-4c9d-946d-a0e052765795.png)
![8](https://user-images.githubusercontent.com/61776791/138494891-0eaac887-25aa-47f3-831c-7ed413d7c798.png) 

5.	Kemudian kita tambahkan router cisco 3725 R1 dan R2 pada bagian toolbar yang sudah kita import tadi

![9](https://user-images.githubusercontent.com/61776791/138494892-11c1dd88-2494-482b-9eb8-7420547bc171.png)

6.	Kita tambahkan juga cloud pada bagian end devices yang mana kita memilih desktop untuk servernya

![10](https://user-images.githubusercontent.com/61776791/138494896-427cc708-981f-4ab6-abea-7347a81d1d69.png)

7.	Kita konfigurasikan cloudnya dengan mengklik kanan pada cloud seperti berikut

![11](https://user-images.githubusercontent.com/61776791/138494897-394e484e-081d-4a6f-8273-f6f4fb4c86cf.png)
![12](https://user-images.githubusercontent.com/61776791/138494900-de47e1ee-4f45-470d-8ea9-e5ea7bca9e47.png)

8.	Ketika sudah kita tambahkan link dari router R1 (FastEthernet0/0) ke cloud (Ethernet)

![13](https://user-images.githubusercontent.com/61776791/138494901-719cf4f9-f1ed-42a7-8ba4-cfcf60f1a277.png)
![14](https://user-images.githubusercontent.com/61776791/138494903-ee72b53d-4967-439b-a114-5ef0612161e2.png)

9.	Kita tambahkan juga link dari router R1 (FastEthernet0/0) ke R2 (FastEthernet0/1)

![15](https://user-images.githubusercontent.com/61776791/138494905-8f92f758-3fc2-406f-add1-000d752524da.png)
![16](https://user-images.githubusercontent.com/61776791/138494909-19e90034-8ad3-4303-bf19-c2ff869dc8e5.png)

10.	Jika link sudah ditambahkan kita dapat menekan show/hidden interface labels untuk menampilkan label interface pada topologi jaringan yang sudah kita buat

![17](https://user-images.githubusercontent.com/61776791/138494914-df230375-50e0-4149-9b18-38c2d927acdb.png)

11.	Sekarang kita dapat menyalakan perangkat jaringannya dengan mengklik tombol start/resume all nodes seperti berikut

![18](https://user-images.githubusercontent.com/61776791/138494918-b9a5c9ab-a57f-4a45-9c9c-dff794f1d905.png)
![19](https://user-images.githubusercontent.com/61776791/138494922-bf8822be-550b-4996-8d44-cca88cbf3313.png)

12.	Untuk mengonfigurasi perangkat jaringannya kita klik tombol console connect to all devices untuk membuka koneksi ke setiap perangkat di topologi

![20](https://user-images.githubusercontent.com/61776791/138494926-c1186530-aef1-47a3-b1e5-aecb6dfcf663.png)

13.	Selanjutnya kita akan mengkonfigurasikan alamat IP Addressnya

R1# configure terminal 
R1(config)# interface FastEthernet 0/0 
R1(config-if)# ip address 192.168.1.123 255.255.255.0 
R1(config-if)# no shutdown 
R1(config-if)# exit 

• Konfigurasikan gateway default:

R1(config)# ip route 0.0.0.0 0.0.0.0 192.168.1.249 R1(config)# end 
• Ping gateway default router:

R1# ping 192.168.1.249

![21](https://user-images.githubusercontent.com/61776791/138494931-820cba52-be1c-4e42-9166-a7d758e72144.png)

Ping berhasil


•	The NAT node

Node ini memungkinkan Anda untuk menghubungkan topologi ke internet melalui NAT. Node Internet tidak digunakan lagi untuk node ini, dan node Cloud.

1.	Kita pilih dan seret NAT seperti berikut dengan memilih GNS3 VM sebagai server
![1](https://user-images.githubusercontent.com/61776791/138599029-b8e50eb5-4500-4152-8332-5e82fa0eac06.png)
![2](https://user-images.githubusercontent.com/61776791/138599043-d5e381eb-f8fe-48a3-b2b8-315f95daa60c.png)

2.	Kemudian kita pilih dan seret webterm seperti berikut
![3](https://user-images.githubusercontent.com/61776791/138599061-fc883320-9ee8-4da5-b2af-9732f09a8f8f.png) 

3.	Kita pilih dan seret switch dengan memilih GNS3 VM sebagai server
![4](https://user-images.githubusercontent.com/61776791/138599082-04b6fe37-9aa1-47c5-9483-58ed2e247aa1.png)
![5](https://user-images.githubusercontent.com/61776791/138599092-1267ef56-8928-46eb-8a97-1a1642afcba3.png)

4.	Hubungkan switch1 (Ethernet0) ke NAT1 (nat0) dan Switch1 ke webterm-1 (eth0)
![6](https://user-images.githubusercontent.com/61776791/138599103-0f72dd92-a3a8-4d10-be2b-1714babd2809.png)
![7](https://user-images.githubusercontent.com/61776791/138599116-92634eef-dfa8-4277-ba7f-a3d04a8ac7da.png)
![8](https://user-images.githubusercontent.com/61776791/138599129-714d8ab5-773d-4989-92ab-7c8c5d130de9.png)
![9](https://user-images.githubusercontent.com/61776791/138599144-502c43fe-5978-4537-9db4-47d27c242a09.png)
![10](https://user-images.githubusercontent.com/61776791/138599163-6ecb83a1-f0f0-459f-8916-604caf28211a.png)

5.	Kita edit config webterm-1 seperti berikut
![11](https://user-images.githubusercontent.com/61776791/138599172-a9c3d5eb-277e-4fe5-ba95-39db5ac77a64.png)

6.	Untuk mengkonfigurasi wadah ini untuk menggunakan DHCP, batalkan komentar pada dua baris yang ditunjukkan pada gambar di bawah ini, dan klik Simpan
![12](https://user-images.githubusercontent.com/61776791/138599179-6336c6da-d560-4541-b192-05f9b75b89d3.png)

7.	Kemudian kita klik start
![13](https://user-images.githubusercontent.com/61776791/138599197-dd06e154-5109-40a4-8c04-3c26be0346a9.png) 

8.	Menggunakan perintah 'ifconfig' di terminal akan menunjukkan bahwa DHCP yang berjalan pada node NAT memberi wadah ini alamat 192.168.122.200 dari kumpulannya
![14](https://user-images.githubusercontent.com/61776791/138599233-81160862-cd95-4ce6-ab46-660fe2c51133.png) 

9.	Hentikan wadah Webterm, klik kanan, dan pilih "Edit konfigurasi" lagi. Kali ini, Anda akan mengomentari dua baris untuk DHCP, dan menghapus komentar pada baris di bagian Static IP dari file /etc/network/interfaces
![15](https://user-images.githubusercontent.com/61776791/138599257-d0193578-443b-4867-b207-f85a7ab75f28.png) 

10.	Membuka terminal dan menjalankan "ifconfig" akan menunjukkan bahwa wadah menggunakan alamat IP yang ditetapkan secara statis
![16](https://user-images.githubusercontent.com/61776791/138599284-6beea009-38da-4500-a60b-9ac1dff51007.png)

11.	Memasukkan URL di bilah alamat Firefox akan membuka situs web
![17](https://user-images.githubusercontent.com/61776791/138599292-177f53b5-48df-43eb-b0f1-8273862d2565.png)
