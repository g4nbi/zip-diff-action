# Zip Diff Action

GitHub Action sederhana untuk **membandingkan isi dua file ZIP** dan menampilkan file mana saja yang isinya berbeda.

## Cara Pakai

1. Upload / commit dua file ZIP ke repository ini, misalnya:
   - `zip1.zip`
   - `zip2.zip`

2. Buka tab **Actions** → pilih workflow **Compare Two ZIPs** → klik **Run workflow**

3. Isi path file ZIP-nya (default sudah `zip1.zip` dan `zip2.zip`)

4. Setelah selesai, buka run tersebut. Hasil perbandingan akan muncul di **Summary** (bagian paling atas).

## Apa yang ditampilkan?

- File yang **hanya ada di ZIP 1**
- File yang **hanya ada di ZIP 2**
- File yang **ada di keduanya tapi isinya berbeda** (dibandingkan lewat SHA-256)
- Ringkasan jumlah file

## Contoh Output

```
### 📊 Hasil Perbandingan ZIP

| Kategori              | Jumlah |
|-----------------------|--------|
| Hanya di ZIP 1        | 3      |
| Hanya di ZIP 2        | 1      |
| Isi berbeda           | 5      |
| Sama                  | 42     |

### 🔴 File dengan isi berbeda
- `src/main.js`
- `assets/icon.png`
...
```

## Catatan

- Support nested folder di dalam ZIP.
- File dibandingkan secara binary (hash SHA-256), jadi aman untuk semua jenis file.
- Bisa dipakai berulang kali, tinggal ganti ZIP-nya lalu jalankan ulang workflow.
