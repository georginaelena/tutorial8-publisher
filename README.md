# Tutorial 8
*Nama   : Georgina Elena Shinta Dewi Achti* <br>
*NPM    : 2206810995*<br>
*Kelas  : AdvProg-B*

# Refleksi

#### 1. How many data will your publisher program send to the message broker in one run?

Publisher program akan mengirim total 5 pesan data ke broker pesan dalam satu kali eksekusi. Setiap panggilan ke fungsi `publish_event()` akan mengirim satu pesan ke broker, dan dalam program utama terdapat 5 pemanggilan ke fungsi tersebut.

#### 2. The URL of: "amqp://guest:guest@localhost:5672" is the same as in the subscriber program, what does it mean?

Kedua program subscriber dan publisher menggunakan URL yang sama, yaitu "amqp://guest:guest@localhost:5672". Ini menunjukkan bahwa keduanya terhubung ke infrastruktur pesan yang sama yang disediakan oleh broker AMQP dan dapat bertukar pesan secara efektif. Dengan menggunakan URL yang sama, keduanya dapat berkomunikasi dengan broker yang sama di mesin lokal (localhost) dengan menggunakan kredensial default "guest:guest" untuk autentikasi. Hal ini memastikan bahwa baik pengirim (publisher) maupun penerima (subscriber) terhubung ke lingkungan yang serupa dan dapat berinteraksi dengan sistem pesan dengan benar.

# Running RabbitMQ as message broker

![](https://i.imgur.com/Vl1MwQE.png)

# Sending and processing event

Setelah menjalankan cargo run di publisher dan subscriber, maka Publisher akan mengirimkan data berupa 5 event ke broker yang diterima oleh Subscriber.

![](https://i.imgur.com/fjaa80l.png)

# Monitoring chart based on publisher

Spike dalam message rate terjadi karena program publisher dieksekusi berulang kali secara berurutan, mengirimkan sejumlah besar pesan ke broker pesan dalam waktu singkat. Seiring dengan bertambahnya jumlah pesan dalam queue, terjadi lonjakan tajam dalam message rate yang diterima oleh broker.

![](https://i.imgur.com/XFbPmWY.png)