# Lab5Web
Penjelasan serta urutan praktikum 5 (Lab5Web).

### Pertanyaan dan Tugas  
> 1. Buat script untuk melakukan validasi pada isian form.

### 1. Membuat judul dan header
```HTML
<!DOCTYPE html>
<html>
  <head>
    <title>Contoh Validasi Form</title>
  </head>
  <body>
    <h1>Formulir Validasi</h1>
  </body>
</html>
```
> ```<!DOCTYPE html>``` Ini adalah deklarasi tipe dokumen, yang mengindikasikan bahwa ini adalah dokumen HTML.  
> ``` <title> ``` Elemen ini menentukan judul halaman web, yang akan ditampilkan di tab browser saat halaman web dibuka.  
> ``` <h1> ``` Ini adalah elemen judul yang digunakan untuk menampilkan teks "Formulir Validasi" dalam ukuran besar.

### Hasil tampilan judul dan header
![00](https://github.com/RafiMlnf/Lab5Web/assets/115614668/3f3a6e0f-18aa-42b9-93c3-358b89565e86)

--------------------------------------

### 2. Membuat tabel form
> Membuat tabel form dengan input nama dan email
```HTML
<!DOCTYPE html>
<html>
  <head>
    <title>Contoh Validasi Form</title>
    <link rel="stylesheet" type="text/css" href="style.css" />
  </head>
  <body>
    <h1>Formulir Validasi</h1>
    
    <form id="Form1" onsubmit="return validateForm()">
      <label for="name">Nama:</label>
      <input type="text" id="name" name="name" />
      <br /><br />

      <label for="email">Email:</label>
      <input type="text" id="email" name="email" />
      <br /><br />

      <input type="submit" value="Kirim" />
    </form>
  </body>
</html>
```

### Tampilan tabel form
> Tampilan tabel form dengan input nama dan email, dan submit button (kirim) untuk mengirim inputan

![01](https://github.com/RafiMlnf/Lab5Web/assets/115614668/e762b78a-3093-4206-bfd9-6a6d6ab48237)

--------------------------------------

### 3. Menambah fungsi form

```HTML
<script>
      function validateForm() {
        var name = document.getElementById("name").value;
        var email = document.getElementById("email").value;

        // Validasi Nama
        if (name === "") {
          alert("Nama harus diisi");
          return false;
        }

        // Validasi Email
        var emailPattern = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/;
        if (!email.match(emailPattern)) {
          alert("Email tidak valid");
          return false;
        }

        // Jika semua validasi berhasil, izinkan pengiriman formulir
        return true;
      }
    </script>
```

>  Skrip kode ini digunakan untuk melakukan validasi data yang dimasukkan oleh pengguna melalui formulir pada halaman web. Validasi ini digunakan untuk memastikan bahwa data yang masuk sesuai dengan kriteria tertentu sebelum data tersebut dikirimkan.

### Penjelasan
> - ``` validateForm() ``` adalah sebuah fungsi JavaScript yang melakukan validasi formulir.  
> - Fungsi ini mengambil nilai dari dua input, yaitu "Nama" dan "Email," yang diperoleh melalui ``` document.getElementById() ```

### Validasi nama dan email
> - Validasi nama dilakukan dengan memeriksa apakah nilai dalam input "Nama" kosong atau tidak. Jika kosong, maka pesan kesalahan akan muncul dan formulir tidak akan dikirim.
> - Validasi email dilakukan dengan menggunakan ekspresi reguler (regular expression) yang memeriksa apakah alamat email yang dimasukkan sesuai dengan format email yang valid.
Jika format email tidak sesuai, pesan kesalahan akan muncul dan formulir tidak akan dikirim.

> Fungsi ``` validateForm() ``` dipanggil pada saat pengguna mencoba mengirimkan formulir (melalui ``` onsubmit="return validateForm()" ``` pada elemen ``` <form> ```). Jika semua validasi berhasil, formulir akan dikirim, tetapi jika ada kesalahan validasi, pengguna akan mendapatkan pesan kesalahan melalui alert() dan formulir tidak akan dikirim.

## Tampilan jika salah satu nama atau email pada form tidak diisi.
![03](https://github.com/RafiMlnf/Lab5Web/assets/115614668/a4bbfd95-f6c5-4ecb-a950-5599c1a16bd8)
![04](https://github.com/RafiMlnf/Lab5Web/assets/115614668/be44dcc7-104e-4c90-9b94-1756b7936152)

--------------------------------------

### 4. Melakukan styling tabel form dengan CSS

- Pertama menghubungkan html dengan css dengan pada ``` <head> ```
```HTML
<link rel="stylesheet" type="text/css" href="style.css" />
```

- Kedua, menambahkan logo Universitas Pelita Bangsa di atas teks header "Validasi Form".
```HTML
<img src="logoupb.png" alt="" class="imgupb" />
```
> Lokasi file logo/gambar harus satu folder dengan file HTML.

## Styling HTML dengan CSS
Kode CSS:

```CSS
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@800&display=swap");

body {
  background-color: #f0f0f0;
  font-family: "Montserrat", sans-serif;
  margin: 0;
  padding: 0;
}

#Form1 {
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  background-color: #ffffff;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: 0 0 10px #a8a8a8;
}

label {
  display: block;
  margin-bottom: 5px;
}

input[type="text"] {
  width: 94%;
  padding: 10px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  border-radius: 3px;
}

input[type="submit"] {
  background-color: #0077cc;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 3px;
  cursor: pointer;
}

input[type="submit"]:hover {
  background-color: #0055aa;
}

h1 {
  text-align: center;
  color: #3f3f3f;
}

.imgupb {
  width: 12%;
  display: block;
  margin: 0 auto;
  padding-top: 30px;
}

label[for="name"],
label[for="email"] {
  color: rgb(105, 105, 105);
}
```
### Tampilan akhir
> Tampilan akhir web HTML validasi form setelah dilakukan styling dengan CSS.

![02](https://github.com/RafiMlnf/Lab5Web/assets/115614668/98782500-a325-4ab7-bdc7-715c4ed70976)

