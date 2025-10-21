````markdown
# 🧾 LAPORAN PRAKTIKUM 5 – JAVASCRIPT

Nama: Surya Putra Darma Jaya  
Mata Kuliah: Pemrograman Web  
Dosen Pengampu: Agung Nugroho, S.Kom., M.Kom  
Universitas: Pelita Bangsa  
Praktikum ke: 5  

---

## 🧩 Tujuan Praktikum
1. Memahami sintaks dasar JavaScript.  
2. Mengetahui cara penggunaan JavaScript dalam dokumen HTML.  
3. Dapat menulis kode JavaScript sederhana.  
4. Dapat melakukan manipulasi elemen HTML menggunakan JavaScript.  

---

## 📘 Dasar Teori Singkat

JavaScript adalah bahasa pemrograman yang berjalan di browser dan dapat memanipulasi elemen-elemen HTML serta gaya CSS.  
Kode JavaScript dapat ditulis di dalam tag `<script>` pada bagian `<head>` atau `<body>`, atau dipisahkan ke file eksternal `.js`.  

Fungsi umum JavaScript:
- Mengubah konten HTML  
- Menyembunyikan/menampilkan elemen  
- Melakukan validasi input  
- Membuat interaksi dinamis dengan pengguna  

---

## 🧪 Langkah Praktikum dan Hasil

---

````

### 🔹 1. JavaScript di dalam `<head>`

```html
<script type="text/javascript">
    alert("Javascript pada tag head.");
</script>
````

**Hasil:**
Muncul pop-up “Javascript pada tag head.”

**Kesimpulan:**
Script di dalam `<head>` dijalankan sebelum halaman ditampilkan.

---

### 🔹 2. JavaScript di dalam `<body>`

```html
<script>
    document.write("Hello World");
</script>
```

**Hasil:**
Menampilkan teks “Hello World” di halaman browser.

**Kesimpulan:**
`document.write()` digunakan untuk menulis langsung ke halaman HTML.

---

### 🔹 3. JavaScript Eksternal

**File:** `eksternal.js`

```javascript
document.write("Hello World dari file eksternal.");
```

**File HTML:**

```html
<script src="eksternal.js"></script>
```

**Hasil:**
Menampilkan teks dari file eksternal.

**Kesimpulan:**
File eksternal memudahkan pemeliharaan kode JavaScript.

---

### 🔹 4. Pemakaian Alert

```html
<script>
    window.alert("Ini adalah contoh penggunaan alert!");
</script>
```

**Hasil:**
Muncul jendela pop-up dengan pesan.

**Kesimpulan:**
`alert()` digunakan untuk menampilkan notifikasi kepada pengguna.

---

### 🔹 5. Pemakaian Method dalam Objek

```html
<script>
var person = {
    firstName: "Surya",
    lastName: "Putra Darma Jaya",
    fullName: function() {
        return this.firstName + " " + this.lastName;
    }
};
document.write("Nama Lengkap: " + person.fullName());
</script>
```

**Hasil:**
Menampilkan “Nama Lengkap: Surya Putra Darma Jaya”.

**Kesimpulan:**
`this` digunakan untuk mengakses properti dalam objek yang sama.

---

### 🔹 6. Pemakaian Prompt

```html
<script>
var nama = prompt("Masukkan nama Anda:");
document.write("Halo, " + nama + "!");
</script>
```

**Hasil:**
Menampilkan jendela input lalu teks sapaan.

**Kesimpulan:**
`prompt()` digunakan untuk mengambil input dari pengguna.

---

### 🔹 7. Pembuatan Fungsi

```html
<script>
function salam() {
    document.write("Selamat datang di Praktikum JavaScript!");
}
salam();
</script>
```

**Hasil:**
Menampilkan “Selamat datang di Praktikum JavaScript!”.

**Kesimpulan:**
Fungsi mempermudah pengelompokan dan pemanggilan kode berulang.

---

### 🔹 8. Operasi Aritmatika

```html
<script>
var a = 10, b = 5;
document.write("Hasil Penjumlahan: " + (a + b));
</script>
```

**Hasil:**
Menampilkan hasil operasi aritmatika.

**Kesimpulan:**
JavaScript dapat melakukan operasi matematika seperti `+`, `-`, `*`, `/`.

---

### 🔹 9. Seleksi Kondisi If…Else

```html
<script>
var nilai = prompt("Masukkan nilai Anda:");
if (nilai >= 75) {
    document.write("Selamat, Anda Lulus!");
} else {
    document.write("Maaf, Anda Belum Lulus.");
}
</script>
```

**Hasil:**
Menampilkan pesan kelulusan berdasarkan nilai.

**Kesimpulan:**
`if...else` digunakan untuk pengambilan keputusan.

---

### 🔹 10. Seleksi Kondisi Switch

```html
<script>
var grade = prompt("Masukkan nilai huruf (A/B/C):");
switch (grade) {
    case "A": document.write("Sangat Baik"); break;
    case "B": document.write("Baik"); break;
    case "C": document.write("Cukup"); break;
    default: document.write("Nilai tidak valid");
}
</script>
```

**Hasil:**
Menampilkan keterangan nilai huruf.

**Kesimpulan:**
`switch` digunakan untuk kondisi tetap dengan pilihan banyak.

---

### 🔹 11. Form Input

```html
<form name="formInput">
Nama: <input type="text" name="nama"><br>
Email: <input type="text" name="email"><br>
<input type="button" value="Tampil" onclick="tampilData()">
</form>

<script>
function tampilData() {
    var nama = document.forms["formInput"]["nama"].value;
    var email = document.forms["formInput"]["email"].value;
    document.write("Nama: " + nama + "<br>Email: " + email);
}
</script>
```

**Hasil:**
Menampilkan data yang diinput ke layar.

**Kesimpulan:**
JavaScript dapat membaca dan menampilkan nilai dari form HTML.

---

### 🔹 12. Validasi Form (Tugas)

```html
<form name="formValid" onsubmit="return validasi()">
Nama: <input type="text" name="nama"><br>
Email: <input type="text" name="email"><br>
<input type="submit" value="Kirim">
</form>

<script>
function validasi() {
    let nama = document.forms["formValid"]["nama"].value;
    let email = document.forms["formValid"]["email"].value;
    if (nama == "" || email == "") {
        alert("Nama dan Email wajib diisi!");
        return false;
    }
    alert("Data berhasil dikirim!");
    return true;
}
</script>
```

**Hasil:**
Akan muncul alert jika field kosong.

**Kesimpulan:**
Validasi form mencegah pengiriman data kosong.

---

### 🔹 13. Checkbox dengan Perhitungan Otomatis

```html
<form>
<input type="checkbox" id="html" onclick="hitungTotal()"> HTML (Rp 50.000)<br>
<input type="checkbox" id="css" onclick="hitungTotal()"> CSS (Rp 40.000)<br>
<input type="checkbox" id="js" onclick="hitungTotal()"> JavaScript (Rp 70.000)<br>
Total: <input type="text" id="total" readonly>
</form>

<script>
function hitungTotal() {
    let total = 0;
    if (document.getElementById("html").checked) total += 50000;
    if (document.getElementById("css").checked) total += 40000;
    if (document.getElementById("js").checked) total += 70000;
    document.getElementById("total").value = total;
}
</script>
```

**Hasil:**
Nilai total berubah otomatis saat checkbox dipilih.

**Kesimpulan:**
JavaScript dapat memproses interaksi dinamis secara real-time.

---

## 🧠 Kesimpulan Akhir

1. JavaScript dapat berjalan di berbagai posisi dokumen HTML (`head`, `body`, atau eksternal).
2. Dapat digunakan untuk interaksi pengguna seperti alert, prompt, validasi form, dan perhitungan otomatis.
3. Setiap latihan memperkuat pemahaman dasar logika pemrograman di JavaScript.

---

