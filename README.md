---

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
