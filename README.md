# Jobsheet2_Embedded-System
Protokol Komunikasi Dan Sensor

I. PENJELASAN SINGKAT

UART adalah protokol komunikasi yang umum digunakan dalam pengiriman data serial antara device satu dengan yang lainnya. Sebagai contoh komunikasi antara sesama mikrokontroler atau mikrokontroler ke PC. Dalam pengiriman data, clock antara pengirim dan penerima harus sama karena paket data dikirim tiap bit mengandalkan clock tersebut. Inilah salah satu keuntungan model asynchronous dalam pengiriman data karena dengan hanya satu kabel transmisi maka data dapat dikirimkan. Berbeda dengan model synchronous yang terdapat pada protokol SPI dan I2C, karena protokol membutuhkan minimal dua kabel dalam transmisi data, yaitu transmisi clock dan data.
SPI adalah protokol data serial sinkron digunakan oleh mikrokontroler untuk berkomunikasi dengan satu atau lebih perangkat periferal cepat jarak pendek. Hal ini juga dapat digunakan untuk komunikasi antara dua mikrokontroler. Dengan koneksi SPI selalu ada perangkat satu master (biasanya mikrokontroler) yang mengontrol perangkat periferal. Inter Integrated Circuit (I2C), I2C adalah sebuah protokol untuk komunikasi serial antar IC, dan sering disebut juga Two Wire Interface (TWI). Bus yang digunakan untuk komunikasi antara mikrokontroler dan device lainnya seperi sensor, dll.

II. ALAT DAN BAHAN 

    1) ESP32 
    2) Breadboard 
    3) Kabel jumper
    4) Sensor DHT 11, RFID 
    5) LED (5) dan Push Button (3) 
    6) Servo 
    7) Resistor 330,1K, 10K Ohm (@ 3)

III. LANGKAH PERCOBAAN 

     A.ESP32 Capacitive Touch Sensor 
       1. Hubungkan kabel jumper Male-to-Female pada Pin D4 ESP32. 
       2. Buka Arduino IDE dan upload script program berikut ke ESP32.
       3. Buka serial monitor untuk melihat raw data. Ubah tampilan serial monitor menjadi Serial Plotter pada menu Tools > Serial Plotter.
       4. Sentuh ujung kabel jumper dan amati yang terjadi, kemudian dokumentasikan hasilnya. 
       5. Buatlah rangkaian seperti gambar 1 di bawah ini
![1](https://user-images.githubusercontent.com/121161133/209558578-aa668ece-8a32-495a-92a7-1a90e53d1e42.png)

       6. Buatlah program agar LED menyala ketika sensor disentuh, dan LED akan mati ketika sensor tidak disentuh.
       7. Buatlah program agar ketika sensor disentuh, LED menyala Blink
       8. Buatlah program agar ketika LED menyala, maka pada Serial Monitor akan menampilkan angka yang akan bertambah setiap kali sensor disentuh. 
       9. Tambahkan 2 LED sehingga pada rangkaian terdapat 3 LED. Buatlah program agar ketika sensor disentuh, LED menyala menjadi running LED. Nyala running LED tersebut adalah bergerak dari kiri ke kanan, kemudian kanan ke kiri secara kontinyu.

     B.Mengakses Sensor DHT 11 (Single Wire / BUS) 
       1. Buatlah rangkaian seperti pada Gambar 2 di bawah ini
![2](https://user-images.githubusercontent.com/121161133/209558523-190af012-f44d-46e8-9f22-75393b5ab5d9.png)

       2. Install library sensor DHT 11 melalui Sketch > Include Library > Manage Libraries. Ketikkan DHT pada kolom pencarian, pilih library yang akan diinstall seperti pada Gambar berikut ini. Kemudian install juga Adafruit Unified Sensor menggunakan cara yang sama.
       3. Buatlah program seperti pada script di bawah ini untuk mengakses sensor DHT11. Kemudian upload program tersebut pada ESP32 dan dokumentasikan hasilnya.
       4. Buatlah program agar ketika suhu rungan mencapai 30 derajat celcius, maka ESP32 akan menyalakan LED Merah dan buzzer secara beep (blink). Apabila suhu dibawah 30 derajat, ESP32 akan mematikan buzzer dan menyalakan LED berbentuk running LED seperti pada Percobaan A. Kemudian dokumentasikan hasilnya.

     C. Mengakses Sensor RFID (SPI Communication) 
        1. Buatlah rangkaian seperti pada gambar 3 di bawah ini
![3](https://user-images.githubusercontent.com/121161133/209558486-8c43990d-9380-4491-b552-0a993fdd5d9a.png)

        2. Install Library MFRC522 dari Library Manager. 
        3. Kemudian buatlah program seperti pada script berikut ini.
        4. Dekatkan kartu atau Tag RFID ke RFID Reader. Amati dan analisis cara kerja programnya. 
        5. Buatlah program agar Tag RFID yang terbaca sebelumya dapat digunakan untuk hak akses. Apabila Tag RFID didekatkan pada Reader, maka LED Hijau akan menyala, servo akan bergerak ke kanan (lalu kembali ke posisi semula setelah 3 detik) dan di Serial Monitor akan tertampil pesan “Akses Diterima, Silahkan Masuk”. Apabila Tag RFID tidak dikenali, maka LED Merah akan menyala, servo tidak bergerak dan di Serial Monitor akan tertampil pesan “Akses Ditolak”. Gunakan Tag RFID lain untuk mencoba.
