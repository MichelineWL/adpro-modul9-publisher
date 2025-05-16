### a. How much data will your publisher program send to the message broker in one run?

Jumlah data yang dikirim oleh program publisher ke message broker dalam satu kali run **tergantung pada isi pesan (message)** dan **berapa banyak pesan yang dikirim**.  

Contoh:
- Jika publisher mengirim **1 pesan berukuran 100 byte**, maka data yang dikirim sekitar **100 byte**.
- Jika mengirim **10 pesan berukuran 100 byte**, maka totalnya sekitar **1000 byte (1 KB)**.

**Jumlah data tergantung pada:**
1. Jumlah pesan yang dikirim
2. Ukuran setiap pesan

---

### b. The URL “amqp://guest:guest@localhost:5672” is the same as in the subscriber program — what does it mean?

Iya. URL `amqp://guest:guest@localhost:5672` digunakan baik oleh **publisher** maupun **subscriber** karena:

- **`amqp://`** → Menunjukkan bahwa koneksi menggunakan protokol AMQP
- **`guest:guest`** → Otentikasi dengan username dan password
- **`localhost:5672`** → Alamat dan port dari message broker (RabbitMQ) yang berjalan secara lokal

**Artinya:**
> Publisher dan subscriber **terhubung ke broker yang sama**, menggunakan kredensial yang sama, dan bertukar pesan melalui broker tersebut.

Ini penting karena dalam arsitektur *publisher-subscriber*, kedua pihak tidak berkomunikasi langsung, tapi melalui **message broker** (seperti RabbitMQ).

---

### c. Running Rabbit MQ
![image](https://github.com/user-attachments/assets/8b6a41ab-3405-474c-892a-f735394e6750)

### d. Console Subscriber
![image](https://github.com/user-attachments/assets/ec092f39-c801-4a3c-9a15-85dcaa44ca81)
![image](https://github.com/user-attachments/assets/44e68165-85fd-4966-a4a8-71ffcae36585)
Publisher kirim 5 event ke message broker
Subscriber memprosesnya (terlihat  pada console ada 5 event)
Pada RabbitMQ terpampang pada bagian connections, channels, queues, dan consumers

### e. Spike 
![image](https://github.com/user-attachments/assets/9fb58d27-7ca4-44f6-9cbc-df822d0358c3)
Ketika publisher dijalankan dengan intensitas berbeda, hasilnya akan terlihat pada kurva 
Ketika intensitas publisher meningkat dalam mengirim pesan ke message broker, akan terjadi lonjakan message rates
