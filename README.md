# Selamat Datang Di :
## Project UAS Pengantar Cloud Computing 2024

**Note:** 
*Bacalah instruksi dengan seksama sebelum mengerjakan :*
*Referensi Materi ini bisa anda baca di LMS ataupun sumber lain*

### Apa yang anda butuhkan :
- Akun github
- Akun dockerhub
- Text Editor (Visual Studio Code recommended)

### Instruksi:
Anda diminta untuk menjalankan suatu **halaman website** (boleh blog, portofolio, atau lainnya) yang dimodifikasi  dengan menambahkan beberapa atribut seperti :
- Nama.
- Nim.
- Deskiripsi singkat tentang pengalaman yang didapatkan dalam materi ini.

### Langkah mengerjakan :
- Buat repository dengan nama **"UAS-PCC-Nama_MHS-2024"**, misal **UAS-PCC-Ilham-2024**
- Clone repository ke local pc anda
  - `$ git clone [url-git-anda.git]`
- Buat branch baru dengan nama **"development"**
- Lakukan modifikasi halaman website yang anda persiapkan di branch **development**
- Jika perubahan dirasa sudah sesuai dengan instruksi diatas, lakukan *merge* ke branch **main**
- Nama docker image ketika build sama dengan nama repository **UAS-PCC-Nama_MHS-2024**

### Tips :
- Setting repository github, dan tambahkan secret yang berisi _dockerhub username_ dan _dockerhub Access Token_
  - `Settings -> Secrets -> Actions -> New Repository Secret`
- File github action berlokasi di folder **.github/workflows/actions-workflow.yml**
- Ubah dan sesuaikan _tag_, _repository_, _secrets_ pada file **actions-workflow.yml** sesuai repo masing-masing
  - `docker build -t dockerhub_username/image_name:latest -f Dockerfile .`
  - `docker login -u ${{secrets.[dockerhub_username]}} -p ${{secrets.[dockerhub_AccessToken]}} && docker push dockerhub_username/image_name:latest`
- Jika semua persiapan sudah selesai, silahkan push ke repository masing-masing
  - `git add .`
  - `git commit -m "commit message"`
  - `git push origin main`
- Cek menu Action pada Github anda, pastikan tidak ada error
- Jika github action berhasil, cek dockerhub anda seharusnya ada image baru yang anda buat
- Coba jalankan docker image yang anda buat di local docker machine ataupun docker playground
  - `docker run -itd -p8080:80 dockerhub_username/docker_image`
- dan buka web browser dengan port 8080, apakah muncul halaman web ?
- jika muncul halaman web berarti project anda berhasil.

### Bagaimana Penilaiannya :
Buat dokumentasi dan submit Pada Assignment Final Test (UAS) di LMS.
