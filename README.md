# Praktikum 4 | Program Data Sederhana

Nama : Tiara Hayatul Khoir

Kelas : TI.24.A.5

Nim : 312410474

Mata Kuliah : Bahasa pemrograman

## List Kosong
```python
data_mahasiswa = []
```
Sebuah list kosong bernama `data_mahasiswa` dibuat. List ini akan digunakan untuk menyimpan semua data mahasiswa yang dimasukkan oleh pengguna.

## Perulangan untuk Memasukkan Data
```python
while True:
```
Program berjalan dalam perulangan `while` agar pengguna bisa memasukkan data sebanyak-banyaknya hingga memilih untuk berhenti `(t)`.

## Input Data Mahasiswa
Di dalam perulangan, pengguna diminta untuk memasukkan data berikut:

Nama mahasiswa: Input string.

NIM mahasiswa: Input string.

Nilai Tugas, UTS, dan UAS: Input berupa angka (float).
```python
nama = input("Nama       : ")
nim = input("NIM        : ")
tugas = float(input("Nilai Tugas: "))
uts = float(input("Nilai UTS  : "))
uas = float(input("Nilai UAS  : "))
```

## Menghitung Nilai Akhir
Nilai akhir dihitung berdasarkan formula:

Nilai Tugas: 30%

Nilai UTS: 35%

Nilai UAS: 35%
Rumusnya adalah:
```python
nilai_akhir = (0.3 * tugas) + (0.35 * uts) + (0.35 * uas)
```

## Menyimpan Data ke List
Semua data (nama, NIM, nilai tugas, UTS, UAS, dan nilai akhir) disimpan ke dalam dictionary, lalu dictionary tersebut ditambahkan ke list `data_mahasiswa`.
```python
data_mahasiswa.append({
    'nama': nama,
    'nim': nim,
    'tugas': tugas,
    'uts': uts,
    'uas': uas,
    'nilai_akhir': nilai_akhir
})
```

## Konfirmasi untuk Menambah Data Lagi
Setelah data selesai dimasukkan, program bertanya apakah pengguna ingin menambah data lagi:

Jika memilih `y`, program kembali ke awal perulangan untuk memasukkan data baru.
Jika memilih `t`, perulangan dihentikan dan program lanjut ke langkah berikutnya untuk menampilkan data.
```python
tambah = input("Tambah data lagi (y/t)? ").lower()
if tambah == 't':
    break
```

## Menampilkan Data dalam Bentuk Tabel
Setelah pengguna memilih untuk berhenti, program menampilkan semua data mahasiswa yang telah dimasukkan dalam format tabel yang rapi.

Header tabel disusun menggunakan `f-string` dan `print`.
Setiap baris data ditampilkan dalam format tabel yang sama menggunakan perulangan `for`.
```python
print("\nData Mahasiswa:")
print("="*73)
print(f"| {'No':^2} | {'Nama':^15} | {'NIM':^10} | {'Tugas':^6} | {'UTS':^6} | {'UAS':^6} | {'Akhir':^6} |")
print("="*73)
for i, mhs in enumerate(data_mahasiswa, start=1):
    print(f"| {i:^2} | {mhs['nama']:^15} | {mhs['nim']:^10} | {mhs['tugas']:^6.2f} | {mhs['uts']:^6.2f} | {mhs['uas']:^6.2f} | {mhs['nilai_akhir']:^6.2f} |")
print("="*73)
```

## Hasil Kode Pemrograman
