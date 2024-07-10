# wahyunabila-215610067-ResponsiNabila

# Membuat website sederhana 

## 1. Persiapan 
### Membuat dua direktori: website-utama dan website-profil.:
```sh
mkdir website-utama
cd website-utama
mkdir website-profil
cd website-profil
```
### Didalam website-utama:
#### a. Buat file index.html 
```sh
nano index.html
```
lalu masukkan script pada file index.html

### 3.	Di dalam website-profil, letakkan file gambar profil
```sh
wget -O ~/website-profil/foto.jpg "https://drive.google.com/uc?export=download&id=1hMtATs0I1kzLsYF8g0DsB24ri1dICtUW"
```
Setelah itu buat index.html pada website profil

## 2. Buat jaringan Docker dengan nama my-nama-mahasiswa-network
```sh
$ docker network create my-wahyu-network
```

## 3. Membuat Dockerfile untuk website-utama dan website-profil(dockerfile pada masing masing direktori
```sh
nano Dockerfile
```

## 4. Bangun dua image Docker dari Dockerfile yang sudah dibuat. Berikan nama yang jelas untuk setiap image 
pada website-utama :
```sh
docker build -t website-utama .
```
pada website-profil :
```sh
docker build -t website-profil .
```

## 5. Buat volume bernama profile-images
```sh
docker volume create profil-images
```
## 6. Menjalankan container website-utama dan website-profil
website-utama :
```sh
docker run -d –name website-utama –network my-wahyu-network -p 8080:80 website-utama
```
website-profil :
```sh
docker run -d –name website-profil –network my-wahyu-network -p 8080:80 website-profil
```

