### Deploy Custom Model using Tensorflow Serving on Cloud

Sebelum mulai kerjaan kita, ada baiknya membaca **BISMILLAH** terlebih dahulu

##### Prerequisites
`tensorflow` <br>
`matplotlib` <br>
`numpy`


###DEPLOY DI LOKAL

1. Download Tensorflow Serving Docker Repository <br>
    `docker pull tensorflow/serving`
2. Buat folder models isinya 
   <br>`Dockerfile`
   <br> `models (Model tensorflow)` <br>
   contoh : <br>
    - models/sawit/1( isinya /variable dan saved_model.pb)
3. Copy Dockerfile dalam 1 directory yang sama dengan folder `models`
4. Ganti variable yang ada di dalam `Dockerfile` <br>
    -> line #35 `MODEL_NAME=sawit` menjadi nama folder model <br>
    -> line #37 ganti path model menjadi nama folder model kalian (contoh `models/sawit`) <br>
5. run command untuk membuat image docker <br>
    -> `docker build -t {NAMA DOCKER IMAGE} .`


###DEPLOY DI HEROKU

1. Download Tensorflow Serving Docker Repository <br>
    `docker pull tensorflow/serving`
2. Buat folder models isinya 
   <br>`Dockerfile`
   <br> `models (Model tensorflow)` <br>
   contoh : <br>
    - models/sawit/1( isinya /variable dan saved_model.pb)
3. Copy Dockerfile dalam 1 directory yang sama dengan folder `models`
4. Ganti variable yang ada di dalam `Dockerfile` <br>
    -> line #35 `MODEL_NAME=sawit` menjadi nama folder model <br>
    -> line #37 ganti path model menjadi nama folder model kalian (contoh `models/sawit`) <br>
5. Login heroku <br>
    `heroku container:login`
6. Buat Project baru di heroku <br>
    `heroku create {NAMA PROJECT}`
7. Prepare Docker image on LOCAL <br>
    `heroku container:push web -a {NAMA PROJECT}`
8. Upload docker image ke heroku <br>
    `heroku container:release web -a {NAMA PROJECT}`
    
Sekian dan Terimakasih