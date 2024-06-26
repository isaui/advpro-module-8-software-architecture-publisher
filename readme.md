Nama: Isa Citra Buana
NPM: 2206081465

a. How many data your publisher program will send to the message broker in one run?

Jawab:

Dalam program tersebut, publisher mengirim lima pesan dengan konten yang berbeda ke antrian "user_created".

b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?

Jawab:

Ya, URL "amqp://guest:guest@localhost:5672" yang digunakan dalam program publisher adalah sama dengan yang digunakan dalam program subscriber. Ini berarti bahwa publisher dan subscriber keduanya terhubung ke server AMQP yang sama, yang berjalan di localhost pada port 5672. Pengguna dan kata sandi yang digunakan dalam URL (guest:guest) adalah nilai default yang sering digunakan dalam konfigurasi lokal atau pengembangan. Jadi, ini menunjukkan bahwa publisher dan subscriber bekerja dalam konteks pengembangan lokal yang sama dan terhubung ke server AMQP yang sama untuk berkomunikasi.

![Alt teks](docs/screenshot-layar-rabbitmq.png)
![Alt teks](docs/screenshot-console-subscriber.png)
Subscriber listen ke message queue rabbitmq di port 15672, kemudian publisher mengirimkan event ke message queue tersebut dan event tersebut dikonsumsi oleh Subscriber.

![Alt teks](docs/monitoring.png)
Spike tersebut terjadi karena setiap kali menjalankan kode publisher, publisher mengirimkan event ke message queue rabbitmq pada port 15672 tersebut
![Alt teks](docs/simulating-slow-response.png)
Ada 10. Hal tersebut terjadi karena kecepatan pemrosesan subscriber lebih lambat daripada laju pesan masuk, maka akan terjadi penumpukan pesan dalam antrean
![Alt teks](docs/monitoring-three-subscriber.png)
![Alt teks](docs/three-terminal.png)
Jika jumlah subscriber ditambah, antrian pesan cenderung lebih sedikit karena pesan diproses lebih cepat, mengurangi penumpukan pesan dalam antrean. Untuk membuatnya lebih efisien lagi, kita hilangkan sleep pada thread yang terjadi di subscriber. Sementara itu, pada publisher, daripada kita kirim event satu satu, lebih baik kita kirim event dalam 1 batching.