# ResponsiCloud

Buatlah docker image yang di dalamnya terdapat web statis yang ketika ditampilkan akan menunjukkan web dengan informasi detil anda seperti nama, nim, hobi, dsb. Docker image ini sudah tersimpan di docker hub, dan ketika dijalankan menggunakan command docker run, berjalan dengan baik.

Langkah – Langkah Sebagai berikut :

1.	Buat repositori baru pada Github
2.	Lakukan Cloning Repositori dengan menggunakan perintah 
            
            git clone https://github.com/dadangwidayanto/ResponsiCloud.git

3.	Cek  folder repository yang di cloning dengan menggunakan perintah 

            ls
          
4.	Kemudian masuk ke folder repository dengan perintah 

            cd ResponsiCloud/

5.	Kemudian buat file dengan nama dockerfile perintah yang digunakan yaitu 

            nano Dockerfile

Isikan tulisan dibawah pada folder tersebut

        FROM nginx:alpine             -> mengambil image docker
        Copy . /us/share/nginx/html	  -> mengcopy file local dari container

6.	Membuat file index.html dengan perintah :

              nano index.html 
              
 yang nantinya isi file ini akan dtampilkan pada website statis, Didalam file html ini berisi coding sebagai website statis yang nantinya ditampilkan, disini saya membuat biodata diri saya pribadi didalam website, isi file index.html ada pada github.
 
 7.	Membangun images dengan perintah 
 
               docker build –t webserver:v1

8.	Kemudian cek images nantinya images akan terlihat dengan perintah 
              
              docker images

9.	Lalu jalankan proses dalam container dengan perintah 

              docker run –d –p 80:80 webserver:v1

10.	kemudian jalankan Container dengan perintah docker run –d –p 80:80 webserver:v1 setelah berhasil dijalankan lalu tekan tanda (+) pada tools bar katacoda dan pilih View HTTP      port 80 on Host 1, Setelah masuk ke  View HTTP port 80 on Host 1 maka website statis dari file index.html tadi ditampilkan

11.	Menambahkan file baru pada repository yang dipilih dengan menggunakan perintah 

              git add .

12.	Kemudian login akun google anda yang sudah terdaftar dalam github dengan perintah 
      
              git confiq –global user.email “dadangwidayanto@gmail.com”

    Login pula username yang ada didalam github dengan perintah 
          
              git confiq –global user.name “dadangwidayanto”

13.	Untuk menyimpan perubahan yang dilakukan, tetapi tidak ada perubahan pada remote repository maka dilakukan dengan perintah 

              git commit –m “test”

14.	kemudian cek  status dari repository lokal dengan perintah 

              git status.
              
15.	lalu untuk mengirimkan perubahan file setelah di commit ke remote repository, menggunakan perintah 

              git push -u origin main          

16.	Lakukan pengecekan pada github apakah file local berhasil di push kedalam github, jika sudah ada index.html yang dibuat tadi maka file berhasil di push ke github.

17.	Dan sekarang saatnya push file kedalam dockerhub, yang pertama buat repository didalam akun dockerhub, dalam push ke docker hub ini saya lakukan di hari yang berbeda  sehingga langkah langkah saya lakukan dari awal sama hamper sama seperti push ke github.

18.	Lakukan cloning repository seperti langkah awal dengan perintah 

              git clone https://github.com/dadangwidayanto/ResponsiCloud.git

19.	Cek file cloningan, jika sudah ada masuk saja ke file tersebut dengan perintah 

              cd ResponsiCloud/
              
20.	Membangun images dengan perintah 

              docker build –t Responsicloud:v1

21.	Cek kembali docker images dengan perintah 
              
              docker images

22.	Kemudian login kedalam docker, sama halnya login dalam github hanya saja perintah yang digunakan yaitu 

              docker login

  Disini kita memasukkan username dan pasword dari docker hub yang sudah kita buat.

23.    Set tag untuk push ke docker hub dengan perintah 

              docker tag 7ce8ae9c4f88 dadangwidayanto/dadangwidyt:responsicloud

24.	Melakukan push images yang kita miliki ke repository kita, dengan perintah 

              docker push dadangwidayanto/dadangwidyt

25.	Setelah di push lakukan pengecekan pada docker hub apakah sudah ada file yang dipush, jika sudah perintah push berhasil dilakukan.


