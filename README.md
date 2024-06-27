# Bookshelf API

Bookshelf API adalah sebuah aplikasi backend yang menggunakan framework Hapi.js untuk mengelola koleksi buku.

## Deskripsi

API ini menyediakan endpoint-endpoint untuk menambah, mengambil, memperbarui, dan menghapus informasi buku dalam koleksi.

## Persyaratan

Pastikan Anda telah menginstal Node.js (versi 12 atau lebih baru) dan npm untuk menjalankan proyek ini.


## Menjalankan Server

Untuk menjalankan server dalam mode produksi:

```sh
npm start
```

Untuk menjalankan server dalam mode pengembangan dengan nodemon:

```sh
npm run start-dev
```

## Endpoint yang Tersedia

### POST /books

Menambahkan buku baru ke dalam koleksi.

#### Contoh Permintaan

```json
{
  "name": "Harry Potter and the Philosopher's Stone",
  "year": 1997,
  "author": "J.K. Rowling",
  "summary": "The novel follows Harry Potter, a young wizard who discovers his magical heritage on his eleventh birthday, when he receives a letter of acceptance to Hogwarts School of Witchcraft and Wizardry.",
  "publisher": "Bloomsbury Publishing",
  "pageCount": 223,
  "readPage": 150,
  "reading": true
}
```

### GET /books

Mengambil daftar buku yang tersedia.

#### Parameter Query yang Tersedia

- `name`: Filter berdasarkan nama buku (case insensitive).
- `reading`: Filter buku sedang dibaca (`0` untuk tidak sedang dibaca, `1` untuk sedang dibaca).
- `finished`: Filter buku sudah selesai (`0` untuk belum selesai, `1` untuk sudah selesai).

### GET /books/{bookId}

Mengambil detail buku berdasarkan ID.

### PUT /books/{bookId}

Memperbarui informasi buku berdasarkan ID.

#### Contoh Permintaan

```json
{
  "name": "Harry Potter and the Philosopher's Stone (Updated)",
  "year": 1997,
  "author": "J.K. Rowling",
  "summary": "The novel follows Harry Potter, a young wizard who discovers his magical heritage on his eleventh birthday, when he receives a letter of acceptance to Hogwarts School of Witchcraft and Wizardry.",
  "publisher": "Bloomsbury Publishing",
  "pageCount": 223,
  "readPage": 150,
  "reading": true
}
```

### DELETE /books/{bookId}

Menghapus buku berdasarkan ID.

## Pengujian

Gunakan alat seperti Postman atau curl untuk menguji setiap endpoint API yang telah diimplementasikan.

### Contoh Penggunaan curl

#### Menambah Buku Baru

```sh
curl -X POST http://localhost:3000/books -H "Content-Type: application/json" -d '{
  "name": "Harry Potter and the Philosopher's Stone",
  "year": 1997,
  "author": "J.K. Rowling",
  "summary": "The novel follows Harry Potter, a young wizard who discovers his magical heritage on his eleventh birthday, when he receives a letter of acceptance to Hogwarts School of Witchcraft and Wizardry.",
  "publisher": "Bloomsbury Publishing",
  "pageCount": 223,
  "readPage": 150,
  "reading": true
}'
```

Pastikan untuk menyesuaikan informasi seperti port yang digunakan untuk server, alamat URL API, dan detail lainnya sesuai dengan konfigurasi Anda.
