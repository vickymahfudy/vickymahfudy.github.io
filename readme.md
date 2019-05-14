Absensi Online
===================

Kelompok:
- Galuh Aan Ramadhan (05111540000026)
- Vicky Mahfudy (05111540000105)
- Fauzan Abid Ramadhan (05111540000156)

----------
Requirement
-------------

- Express

    `npm install express --save`

- Cookie Parser

    `npm install cookie-parser`

- Body Parser

     `npm install body-parser`

- Express Session

     `npm install express-session`

- MySQL

    `npm install mysql`
    
- MD5 

    `npm install md5`
    
API
-------------

1. Absen
    <br>`POST /absen`
    <br>Body: Nama Ruang, NRP

2. Rekap kuliah per semester
    <br>`GET /rekappersemester/IDMATAKULIAH`
<br>
| __nama_ruang__ | __pertemuan_ke__ | __jam_mulai__ | __jam_selesai__ |
|----------------|------------------|---------------|-----------------|
| IF-107a        | 1                | 10.00         | 12.30           |
| LP2            | 2                | 10.00         | 12.30           |
<br>
3. Rekap kuliah per pertemuan
    <br>`GET /rekappertemuan/IDMATAKULIAH/PERTEMUANKE`
<br>
| __nama_ruang__ | __nomorinduk__ | __waktu_absen__ | __masuk_or_keluar__ |
|----------------|----------------|-----------------|---------------------|
| IF-107a        | 05111540000105 | 10.03           | Masuk               |
| IF-107a        | 05111540000999 | 10.15           | Masuk               |
| IF-107a        | 05111540000105 | 12.35           | Keluar              |
<br>
4. Rekap per mahasiswa per kuliah (BELUM BISA)
    <br>`GET /rekapmahasiswa/NRP/IDMATAKULIAH`
<br>
| __pertemuan_ke__ | __waktu_absen__ | __masuk_or_keluar__ |
|------------------|-----------------|---------------------|
| 1                | 10.03           | Masuk               |
| 1                | 12.35           | Keluar              |
| 2                | 10.13           | Masuk               |
| 2                | 12.45           | Keluar              |
<br>
5. Rekap per mahasiswa per semester (BELUM BISA)
    <br>`GET /rekapmahasiswasemester/NRP/SEMESTER`
<br>
| __nama_matkul__ | __pertemuan_ke__ | __waktu_absen__ | __masuk_or_keluar__ |
|-----------------|------------------|-----------------|
| PBKK            | 1                | 10.03           | Masuk               |
| PBKK            | 1                | 12.35           | Keluar              |
| PBKK            | 2                | 10.13           | Masuk               |
| PBKK            | 2                | 12.45           | Keluar              |
| ...             | ...              | ...             | ...                 |
| Data Mining     | 1                | 13.15           | Masuk               |
<br>
6. Tambah user mahasiswa baru
    <br>`POST /tambahmahasiswa`
    <br>Body: NRP, Nama, Password

7. Tambah user mahasiswa ke mata kuliah
    <br>`POST /tambahpeserta`
    <br>Body: ID Mata Kuliah, NRP

8. Tambah mata kuliah baru
    <br>`POST /tambahmatkul`
    <br>Body: Nama Matkul, Kelas, Semester

9. Tambah jadwal pertemuan untuk kuliah
    <br>`POST /tambahjadwal`
    <br>Body: ID Mata Kuliah, Pertemuan Ke-, Nama Ruang, Jam Mulai, Jam Selesai

Run
-------------
`node index.js`