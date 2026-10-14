# Timer Presentasi

Timer hitung mundur dengan latar transparan, dibuat untuk **Browser Source di OBS**.

- Bunyi peringatan otomatis saat **3 detik terakhir**
- Alarm saat waktu habis
- **Atur waktu** langsung dari halaman (menit & detik), atau lewat parameter URL
- Tombol Jeda, Reset, dan Suara On/Off
- Format tampilan otomatis berubah: `HH:MM:SS` → `MM:SS` → `detik.desi` (di bawah 20 detik)

## Link untuk OBS (tinggal salin)

Klik ikon salin di pojok kanan kode di bawah, lalu tempel ke kolom **URL** pada Browser Source di OBS.

Timer 5 menit:

```
https://saskiananditaputri.github.io/timer-presentasi/timer.html?m=5
```

Timer 10 menit:

```
https://saskiananditaputri.github.io/timer-presentasi/timer.html?m=10
```

Timer 90 detik, teks putih:

```
https://saskiananditaputri.github.io/timer-presentasi/timer.html?s=90&c=FFFFFF
```

Tanpa tombol kontrol (tampilan bersih untuk stream), volume 50%:

```
https://saskiananditaputri.github.io/timer-presentasi/timer.html?m=5&ui=0&v=50
```

Semua parameter dengan nilai bawaan:

```
https://saskiananditaputri.github.io/timer-presentasi/timer.html?m=5&s=0&c=FFF788&a=1&w=1&v=20&ui=1
```

## Cara pakai di OBS

1. Di OBS, klik **+** pada **Sources** → **Browser**.
2. Tempel salah satu link di atas ke kolom **URL**.
3. Atur **Width** `400` dan **Height** `150` (lebih tinggi sedikit jika ingin panel atur waktu terlihat).
4. Centang **Shutdown source when not visible**. Dengan begitu timer mulai ulang setiap sumber disembunyikan lalu ditampilkan lagi.
5. Klik **OK**.

### Mengatur waktu saat live

Klik kanan sumber timer di OBS → **Interact**. Di jendela yang muncul:

1. Klik **Atur Waktu**.
2. Isi menit dan detik, lalu klik **Mulai** (atau tekan Enter).

Waktu yang diatur ikut tersimpan di URL halaman, jadi tidak hilang saat halaman dimuat ulang. Untuk menyimpan waktu itu secara permanen di OBS, ubah juga parameter `m` atau `s` pada kolom URL Browser Source.

## Parameter URL

| Parameter | Fungsi | Nilai | Bawaan |
|-----------|--------|-------|--------|
| `m` | Durasi dalam menit | angka ≥ 0 | - |
| `s` | Durasi dalam detik (bisa digabung dengan `m`, misalnya `m=1&s=30` = 1:30) | angka ≥ 0 | - |
| `c` | Warna teks, hex 6 digit tanpa `#` | contoh `FF0000` | `FFF788` |
| `w` | Bunyi peringatan 3 detik terakhir | `1` aktif, `0` mati | `1` |
| `a` | Alarm saat waktu habis | `1` aktif, `0` mati | `1` |
| `v` | Volume suara | `0` - `100` | `20` |
| `ui` | Tampilkan tombol kontrol | `1` tampil, `0` sembunyi | `1` |

Jika `m` dan `s` tidak diisi, timer memakai **5 menit**.

## File suara

| File | Dipakai untuk |
|------|---------------|
| `sounds/3.mp3` | Peringatan saat sisa waktu 3 detik (diputar sekali). Jika file ini gagal dimuat, diganti bunyi "bip". |
| `sounds/1.mp3` | Alarm saat waktu habis |

Untuk mengganti suara, timpa file di atas dengan file mp3 Anda (nama file tetap sama).

## Catatan

- Di browser biasa (Chrome, Edge, dll.), suara baru boleh bunyi setelah halaman diklik sekali. OBS tidak mewajibkan ini, tetapi sebaiknya tetap diuji.
- Agar link di atas berfungsi, aktifkan GitHub Pages: **Settings → Pages → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**. Tunggu satu sampai dua menit hingga situs aktif.

## Lisensi

Proyek ini berasal dari [nakomaru/obs-browser-timer](https://github.com/nakomaru/obs-browser-timer) (CC0). Pastikan Anda memiliki hak pakai untuk file suara yang ada di folder `sounds/`.
