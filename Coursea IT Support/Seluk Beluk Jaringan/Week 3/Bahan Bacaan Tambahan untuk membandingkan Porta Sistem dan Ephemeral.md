Protokol lapisan transportasi menggunakan konsep porta dan _multiplexing/demultiplexing_ untuk mengirim data ke layanan individu yang mendengarkan di simpul jaringan. Porta ini diwakili oleh nomor 16-bit tunggal, yang berarti bahwa mereka dapat mewakili nomor mulai 0-65535.

Rentang ini telah dibagi oleh [IANA](https://www.iana.org/) (**Internet Assigned Numbers Authority**) menjadi bagian independen:

Porta 0 tidak digunakan untuk lalu lintas jaringan, namun terkadang digunakan dalam komunikasi yang terjadi antara program yang berbeda pada komputer yang sama.

Porta 1-1023 disebut sebagai **porta sistem,** atau terkadang dikenal sebagai “ _**well-known port.**_ ”. Porta ini mewakili porta resmi untuk sebagian besar layanan jaringan yang sudah dikenal dengan baik. Pada video sebelumnya, kita membahas tentang bagaimana biasanya HTTP berkomunikasi melalui porta 80, sedangkan FTP biasanya berkomunikasi melalui porta 21. Pada sebagian besar sistem operasi, diperlukan akses setingkat administrator untuk memulai program yang menunggu koneksi masuk pada porta sistem.

Porta 1024-49151 dikenal sebagai _**registered ports**_. Porta ini banyak digunakan untuk layanan jaringan lain yang mungkin tidak biasanya terdapat di porta sistem. Contoh yang cocok untuk porta ini adalah 3306, yang merupakan porta yang didengarkan oleh banyak basis data. Tidak semua _registered ports_ terdaftar secara resmi dan diakui oleh IANA. Pada sebagian besar sistem operasi, setiap pengguna dengan tingkat akses apa pun dapat memulai program yang mendengar di porta itu.

Terakhir, kita memiliki porta 49152-65535. Ini dikenal sebagai _**private ports**_ atau _**ephemeral ports**_. Porta ini tidak dapat didaftarkan ke IANA dan umumnya digunakan untuk membuat koneksi keluar. Harus diingat bahwa semua lalu lintas TCP menggunakan porta sumber dan porta tujuan. Ketika klien ingin berkomunikasi dengan server, klien akan diberi _ephemeral port_ yang digunakan hanya untuk sekali koneksi itu, sementara server menunggu koneksi masuk pada porta sistem atau _registered port_ yang statis.

Tidak semua sistem operasi mengikuti rekomendasi _ephemeral port_ dari IANA. Dalam pelajaran ini, kita tetap mengasumsikan bahwa _ephemeral port_ yang digunakan untuk koneksi keluar terdiri dari porta 49152 hingga 65535. Tetapi penting untuk diketahui bahwa rentang yang tepat dapat bervariasi tergantung pada platform yang sedang Anda kerjakan. Terkadang sebagian rentang _registered ports_ sedang digunakan, tetapi tidak ada sistem operasi modern yang akan menggunakan porta sistem untuk komunikasi keluar

Untuk mempelajari lebih lanjut tentang porta, dan untuk melihat daftar porta apa yang telah ditetapkan untuk tiap layanan, lihat [Daftar Nama Layanan dan Nomor _Transport Protocol Port_](https://www.iana.org/assignments/service-names-port-numbers) yang ada di IANA. Daftar serupa yang tidak resmi juga ada di [Wikipedia](https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers), dan lebih mudah dibaca. Cobalah dilihat.

Read Before : [[Protokol Berorientasi Koneksi dan Tanpa Koneksi]]
Read Next : [[Firewall]]