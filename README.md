a. Program publisher mengirim 5 data/event ke message broker dalam satu kali run. Hal ini karena pada kode publisher terdapat 5 kali pemanggilan p.publish_event(...)
b. URL yang sama pada publisher dan subscriber berarti kedua program terhubung ke message broker RabbitMQ yang sama. Publisher menggunakan URL tersebut untuk mengirim event ke RabbitMQ, sedangkan subscriber menggunakan URL yang sama untuk mendengarkan dan mengambil event dari RabbitMQ.
<img width="1918" height="982" alt="image" src="https://github.com/user-attachments/assets/b7608b12-2fd3-4614-a476-bca2a66e4bb6" />
Ketika saya cargo run, publisher mengirim 5 event ke message broker. Event-event tersebut kemudian diproses oleh subscriber.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/18f6ebc4-f9fe-45df-b922-c59c91b3263a" />
Lonjakan atau spike pada chart menunjukkan adanya peningkatan aktivitas message rate, seperti proses publish dari publisher, deliver dari RabbitMQ, dan acknowledge dari subscriber. Semakin sering publisher dijalankan, semakin banyak message yang masuk ke RabbitMQ, sehingga spike pada chart akan terlihat lebih tinggi atau muncul berulang:
<img width="1918" height="912" alt="Screenshot 2026-05-12 201050" src="https://github.com/user-attachments/assets/161c715f-b508-44d0-bd8c-f7790e9d56e0" />

