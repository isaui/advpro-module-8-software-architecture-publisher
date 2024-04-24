Nama: Isa Citra Buana
NPM: 2206081465

a. How many data your publisher program will send to the message broker in one run?

Jawab:

Dalam program tersebut, publisher mengirim lima pesan dengan konten yang berbeda ke antrian "user_created".

b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?

Jawab:

Ya, URL "amqp://guest:guest@localhost:5672" yang digunakan dalam program publisher adalah sama dengan yang digunakan dalam program subscriber. Ini berarti bahwa publisher dan subscriber keduanya terhubung ke server AMQP yang sama, yang berjalan di localhost pada port 5672. Pengguna dan kata sandi yang digunakan dalam URL (guest:guest) adalah nilai default yang sering digunakan dalam konfigurasi lokal atau pengembangan. Jadi, ini menunjukkan bahwa publisher dan subscriber bekerja dalam konteks pengembangan lokal yang sama dan terhubung ke server AMQP yang sama untuk berkomunikasi.

![Alt teks](docs/screenshot-layar-rabbitmq.png)
