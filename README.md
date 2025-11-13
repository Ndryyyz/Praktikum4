# Praktikum 4
# Laporan Praktikum
# Penjelasan Program Input Data Mahasiswa

# Deskripsi Singkat
Program Python untuk mengelola data nilai mahasiswa dengan fitur input berulang, perhitungan otomatis nilai akhir, dan menampilkan seluruh data yang telah diinput.

---

# Cara Kerja Program

### 1. **Inisialisasi Data**
```python
data_mahasiswa = []
```
Membuat list kosong untuk menyimpan semua data mahasiswa.

### 2. **Input Data (Looping)**
```python
while True:
    nama = input("Nama Mahasiswa: ")
    tugas = float(input("Nilai Tugas: "))
    uts = float(input("Nilai UTS: "))
    uas = float(input("Nilai UAS: "))
```
- Program meminta input nama dan tiga nilai
- Loop `while True` memungkinkan input data berulang kali

### 3. **Perhitungan Nilai Akhir**
```python
nilai_akhir = (tugas * 0.30) + (uts * 0.35) + (uas * 0.35)
```
**Formula:**
- Nilai Tugas = 30%
- Nilai UTS = 35%
- Nilai UAS = 35%

**Contoh:** Tugas=80, UTS=85, UAS=90 → Nilai Akhir = 85.25

### 4. **Penyimpanan ke List**
```python
mahasiswa = {'nama': nama, 'tugas': tugas, 'uts': uts, 
             'uas': uas, 'nilai_akhir': nilai_akhir}
data_mahasiswa.append(mahasiswa)
```
Data disimpan dalam bentuk dictionary, lalu ditambahkan ke list.

### 5. **Validasi Input**
```python
try:
    # kode input
except ValueError:
    print("Error: Masukkan nilai berupa angka!")
    continue
```
Mencegah program error jika user memasukkan nilai non-angka.

### 6. **Kontrol Perulangan**
```python
tambah = input("Tambah data lagi? (y/t): ").lower()
if tambah != 'y':
    break
```
- Jika user input **'y'** → lanjut input data baru
- Jika user input **'t'** → keluar dari loop

### 7. **Menampilkan Data**
```python
for i, mhs in enumerate(data_mahasiswa, 1):
    print(f"Data ke-{i}")
    print(f"  Nama: {mhs['nama']}")
    print(f"  Nilai Akhir: {mhs['nilai_akhir']:.2f}")
```
Menampilkan semua data yang tersimpan dengan format rapi.

---

# Alur Program

```
START
  ↓
Buat List Kosong
  ↓
Input Nama & Nilai (Tugas, UTS, UAS)
  ↓
Validasi Input → Jika Error, Input Ulang
  ↓
Hitung Nilai Akhir (30% + 35% + 35%)
  ↓
Simpan ke List
  ↓
Tambah Data Lagi? (y/t)
  ↓ y          ↓ t
  └──────→  Tampilkan Semua Data
              ↓
            END
```

---

# Fitur Program

| Fitur | Keterangan |
|-------|------------|
| ✅ Input Berulang | Bisa input banyak data sekaligus |
| ✅ Perhitungan Otomatis | Nilai akhir dihitung sesuai bobot |
| ✅ Validasi Error | Mencegah crash saat input salah |
| ✅ Penyimpanan Terstruktur | Menggunakan list of dictionaries |
| ✅ Tampilan Rapi | Output terformat dengan jelas |

---

# Konsep Pemrograman

1. **List** - Menyimpan koleksi data
2. **Dictionary** - Struktur data key-value
3. **Loop (while)** - Perulangan dengan kondisi
4. **Try-Except** - Error handling
5. **Function** - Modularitas kode (`def tambah_data()`)

---

# Contoh Output

```
==================================================
PROGRAM INPUT DATA MAHASISWA
==================================================

--- Input Data Baru ---
Nama Mahasiswa: Andry
Nilai Tugas (0-100): 80
Nilai UTS (0-100): 85
Nilai UAS (0-100): 90

✓ Data berhasil ditambahkan!
  Nilai Akhir: 85.25

Tambah data lagi? (y/t): t

==================================================
DAFTAR DATA MAHASISWA
==================================================

Data ke-1
  Nama        : Andry
  Nilai Tugas : 80.0
  Nilai UTS   : 85.0
  Nilai UAS   : 90.0
  Nilai Akhir : 85.25

==================================================
Total data: 1
==================================================
```

---

# Catatan

⚠️ **Bobot Nilai:** Tugas 30%, UTS 35%, UAS 35%

⚠️ **Data Sementara:** Data hanya tersimpan selama program berjalan

⚠️ **Range Nilai:** Disarankan input 0-100
