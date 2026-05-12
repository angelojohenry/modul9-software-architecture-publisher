a. Program publisher mengirim 5 data/event ke message broker dalam satu kali run. Hal ini karena pada kode publisher terdapat 5 kali pemanggilan p.publish_event(...)
b. URL yang sama pada publisher dan subscriber berarti kedua program terhubung ke message broker RabbitMQ yang sama. Publisher menggunakan URL tersebut untuk mengirim event ke RabbitMQ, sedangkan subscriber menggunakan URL yang sama untuk mendengarkan dan mengambil event dari RabbitMQ.
<img width="1918" height="982" alt="image" src="https://github.com/user-attachments/assets/b7608b12-2fd3-4614-a476-bca2a66e4bb6" />
Ketika saya cargo run, publisher mengirim 5 event ke message broker. Event-event tersebut kemudian diproses oleh subscriber.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/18f6ebc4-f9fe-45df-b922-c59c91b3263a" />
