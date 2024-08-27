# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
2. Apa yang anda ketahui tentang Infrastructure?
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
6. Mengapa teknology container saat ini sangat populer?
7. Apa yang anda ketahui tentang Orchestration Container System?

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini

1. DevOps merupakan singkatan dari dua kata yaitu Development dan Operation. Di mana kedua kata tersebut bermakna menggabungkan proses development/pengembangan dari sebuah sistem/aplikasi dengan operation/operasional.
2. Arsitektur infrastruktur dan aplikasi merujuk pada struktur, komponen, dan desain yang mendasari suatu sistem komputer atau perangkat lunak. Ini mencakup dua aspek penting, yaitu arsitek infrastruktur dan arsitek aplikasi.
3. Suatu sistem komputer yang mempunyai layanan khusus sebagai penyimpanan data. Contohnya adalah web server, mail server, dan database server.
4. Dalam deployment, semua hasil coding yang telah dibuat oleh programmer disimpan atau dipindahkan ke dalam satu tempat (server).
5. Container adalah paket kode perangkat lunak yang berisi kode aplikasi, pustaka aplikasi, dan dependensi lainnya. sedangkan virtualisasi adalah salinan digital dari mesin fisik.
6. Salah satu keunggulan utama teknologi container adalah portabilitasnya yang tinggi. Container dapat dijalankan di berbagai platform dan lingkungan, mulai dari komputer lokal hingga server Cloud.
7. Orkestrasi kontainer adalah proses mengotomatiskan jaringan dan pengelolaan kontainer sehingga Anda dapat menerapkan aplikasi dalam skala besar. Kontainerisasi menggabungkan kode aplikasi dengan semua berkas dan pustaka yang dibutuhkan untuk dijalankan pada infrastruktur apa pun.
   
## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy
  
(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container
  - image: `dimmaryanto93/udemy-springboot-app:latest`
  - port: `8080`
  - env: 
    - `DATABASE_HOST`: `<ip-domain-db>`
    - `DATABASE_PORT`: `5432` 
    - `DATABASE_NAME`: `<db-name>`
    - `DATABASE_PASSWORD`: `<db-password>`
    - `APPLICATION_PORT`: `8080`
  need:
    - Database PostgreSQL v14.2
2. Frontend container
  - image: `dimmaryanto93/udemy-angular-app:latest`
  - port: `80`
  - env:
    - `APPLICATION_PORT`: `80`
    - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
    - `BACKEND_HOST`: `<ip-backend-apps>`
    - `BACKEND_PORT`: `<port-backend-apps>`
    - `BACKEND_CONTEXT_PATH`: `/`
  - need:
    - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`

