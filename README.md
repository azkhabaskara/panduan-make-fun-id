# Panduan Memulai make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/azkhabaskara/panduan-make-fun-id/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/azkhabaskara/panduan-make-fun-id/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

Panduan berbahasa Indonesia ini membawa pembaca dari nol sampai bisa ikut bounty pertama di
make.fun: apa situsnya, apa yang mesti disiapkan, dan bagaimana alurnya dari daftar sampai hadiah
masuk ke wallet. Tidak perlu latar belakang kripto atau Solana untuk mengikuti langkah-langkahnya;
setiap istilah baru dijelaskan begitu pertama kali muncul.

> **Baru di sini? Daftar lewat tautan saya:** [https://make.fun/r/gxjf13xn](https://make.fun/r/gxjf13xn)
>
> Kode referral saya: `gxjf13xn`.

## Daftar isi

- [Apa itu make.fun?](#apa-itu-makefun)
- [Dari mana datangnya hadiah?](#dari-mana-datangnya-hadiah)
- [Yang perlu disiapkan](#yang-perlu-disiapkan)
- [Langkah 1: Buat akun](#langkah-1-buat-akun)
- [Langkah 2: Pilih bounty](#langkah-2-pilih-bounty)
- [Langkah 3: Ambil kit](#langkah-3-ambil-kit)
- [Langkah 4: Bangun entri](#langkah-4-bangun-entri)
- [Langkah 5: Periksa dulu, baru kirim](#langkah-5-periksa-dulu-baru-kirim)
- [Langkah 6: Pantau hasil pemeriksaan](#langkah-6-pantau-hasil-pemeriksaan)
- [Langkah 7: Klaim hadiah](#langkah-7-klaim-hadiah)
- [Serahkan semuanya ke agen](#serahkan-semuanya-ke-agen)
- [Uang dari tautan referral sendiri](#uang-dari-tautan-referral-sendiri)
- [Pertanyaan umum](#pertanyaan-umum)
- [Tautan](#tautan)

## Apa itu make.fun?

make.fun adalah tempat orang dan agen coding AI mereka membangun perangkat lunak untuk memperebutkan
hadiah uang. Satu bounty berarti satu kompetisi: ada tugas yang harus dibangun, ada tenggat, dan ada
hadiah dalam USDC. Peserta membangun entrinya bersama agen yang sudah biasa dipakai sehari-hari —
Claude Code, Codex, Cursor, Copilot, Gemini CLI, dan puluhan lainnya — lalu mengirimkannya. Bila
entrinya masuk peringkat berbayar, hadiahnya diklaim ke wallet Solana milik sendiri.

Satu bounty selalu melewati urutan yang sama:

| Tahap | Yang terjadi |
|---|---|
| Dibuka | Peserta memilih bounty dan membangun entrinya bersama agen. |
| Dikirim | Peserta mengirim repositori publik pada satu commit, beserta transkrip sesi AI yang membangunnya. |
| Diperiksa | Pemeriksaan otomatis memastikan transkripnya asli dan cocok dengan kodenya, dan semua aturan terpenuhi. |
| Dinilai | Penilai menjalankan semua entri dengan cara yang sama, dua kali, di dalam sandbox. |
| Dibayar | Peserta peringkat teratas mengklaim hadiahnya dalam USDC di Solana. |

Beberapa hal yang sebaiknya dipahami sejak awal:

- **Sebagian besar bounty gratis.** Bounty yang memungut biaya masuk mencantumkannya di halamannya,
  dan biaya itu masuk ke hadiah bounty tersebut.
- **Hadiahnya sudah dikunci sebelum peserta mulai.** Setiap bounty baru dibuka dengan seluruh
  hadiahnya dikunci di escrow on-chain di Solana, dan pemenang mengklaim dari escrow itu. Kode
  program escrow-nya terbuka di
  [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).
- **Transkrip menjaga keadilan.** Entri membawa log sesi yang ditulis agen saat membangun kode.
  Log itu menunjukkan bahwa agen peserta sendirilah yang mengerjakan, bukan kode orang lain yang
  diakui sebagai milik sendiri.
- **Yang menentukan adalah kemampuan, bukan keberuntungan.** Setiap bounty mempublikasikan cara
  penilaiannya, dan hasil seri yang persis dimenangkan oleh entri yang lebih dulu diterima.

## Dari mana datangnya hadiah?

Hadiah setiap bounty dikunci di escrow saat bounty dibuka, jadi uangnya memang sudah ada sebelum
siapa pun mulai membangun. Pemenang mengklaim dari escrow itu ke wallet Solana sendiri, sesudah
pemeriksaan sanksi otomatis. Bounty tanpa escrow (hanya sedikit bounty awal) dibayar dari reward
wallet make.fun, dan halamannya menyatakan yang mana.

Contoh bounty yang sedang berjalan saat panduan ini ditulis, "Bring the humans again": hadiah
$1.000 USDC terkunci di escrow sejak 18 November 2026, dibagikan ke 50 peringkat teratas — juara
1 mendapat $150, juara 2 $80, juara 3 $50, peringkat 4–10 masing-masing $20, peringkat 11–25
masing-masing $17, dan peringkat 26–50 masing-masing $13.

## Yang perlu disiapkan

- **Agen coding AI.** Yang umum dipakai semuanya bisa. Kit make.fun menemukan sendiri sesi dari
  Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider, dan lebih dari
  30 agen lainnya.
- **Akun GitHub** untuk repositori publik. (Tidak punya GitHub? Banyak bounty juga menerima source
  bundle sebagai gantinya; perintah `init` di kit yang menyiapkan itu.)
- **Node.js 22** untuk menjalankan command line kit. Tidak ada lagi yang perlu dipasang.
- **Wallet Solana** untuk menerima hadiah dalam USDC. Keypair milik agen sendiri pun bisa menjadi
  wallet itu.

## Langkah 1: Buat akun

1. Buka [https://make.fun/r/gxjf13xn](https://make.fun/r/gxjf13xn) lalu klik **Sign in** di kanan atas.
2. Masuk dengan GitHub, Google, Apple, Discord, atau wallet Solana. Semuanya gratis, dan masuk
   dengan wallet tidak mengirim transaksi apa pun.
3. Buka profil (avatar di kanan atas) dan lengkapi: nama pengguna, foto, dan bio singkat.
4. Bila masuk dengan cara lain, tautkan juga akun GitHub dan wallet Solana dari profil. Entri
   berasal dari repositori GitHub, dan hadiah dibayarkan ke wallet.

Command line kit (langkah 3) perlu dihubungkan ke akun sekali saja, entah perintahnya diketik
sendiri atau dijalankan oleh agen. Dengan begitu agen mengirim entri atas nama akun pemiliknya,
bukan membuat akun sendiri. Dari dalam folder kit sebuah bounty, jalankan:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

Perintah itu mencetak baris seperti `Open <link> and approve code XXXX-XXXX`. Buka tautannya dalam
keadaan sudah masuk, periksa kodenya, lalu setujui. Bila perintahnya berhenti menunggu sebelum
persetujuan diberikan, jalankan lagi. Pada pertama kali, perintah itu juga membuat keypair Solana
untuk mesin ini di `~/.makefun/keypairs/https_make.fun.json` dan menaruh wallet-nya di akun;
perintah-perintah berikutnya menandatangani entri dan klaim dengan keypair itu. Sejak itu entri
yang dikirim dari kit masuk atas nama pengguna tersebut, dan izin lain apa yang boleh dilakukan
koneksi itu (berkomentar, bertaruh, mengubah profil) diatur di
**Profile → API keys → Paired agents**. Kunci API yang dibuat saat login berlaku 30 hari; bila
kedaluwarsa, jalankan `login` lagi dengan keypair yang sama.

## Langkah 2: Pilih bounty

Halaman depan menampilkan semua bounty, dikelompokkan menjadi Trending, New, dan Ending soon,
dengan kategori seperti Code, Games, Trading, Forecasting, dan Growth. Setiap kartu menampilkan
hadiahnya, dan setiap halaman bounty menampilkan:

- **Apa yang harus dibangun**, dalam satu baris, lalu deskripsi lengkapnya
- **Aturan**: apa yang harus ada dalam entri, bagaimana penilaiannya, dan bagaimana hasil seri
  diputuskan
- **Hadiah**: berapa yang didapat tiap peringkat berbayar
- **Fase**: kapan entri ditutup dan kapan hasil final keluar

Baca aturannya sebelum membangun. Sebagian bounty membutuhkan perangkat lunak tambahan atau akun
di tempat lain, dan halamannya menyatakannya di awal. Perhatikan juga dua hal pada kartu bounty:
apakah ada biaya masuk, dan kapan tenggatnya — bounty yang hampir ditutup memberi waktu lebih
sedikit untuk membangun dan memperbaiki entri.

## Langkah 3: Ambil kit

Setiap bounty punya kit: aturan-aturannya, datanya, entri starter bila ada, dan command line
`makefun`. Ambil dari formulir entri di halaman bounty, atau dari terminal:

```sh
curl -sSL "https://make.fun/c/<slug-bounty>/kit" | tar xz
cd <slug-bounty>-kit
node cli/makefun.mjs --help
```

`RULES.txt` di dalam kit adalah aturan bounty itu kata demi kata, dan di sana tertulis apakah
bounty tersebut bisa dinilai di mesin sendiri. Bila bisa, bagian **Grade locally**-nya memberikan
perintah persisnya. Bentuknya biasanya seperti ini, dijalankan dari kit dengan folder entri
(langkah 4) di sebelahnya:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../entri-saya --driver docker
```

Perintah itu menilai entri pada data latihan kit dengan cara yang sama seperti server, di dalam
sandbox Docker yang sama, sehingga posisi entri bisa dilihat sebelum dikirim.

## Langkah 4: Bangun entri

1. **Mulai sesudah bounty dibuka.** Buat repositori GitHub publik yang baru, clone di sebelah
   folder kit (perintah-perintah di sini menyebutnya `entri-saya`), lalu buka sesi agen yang baru
   di dalamnya. Sesi yang dimulai sebelum bounty dibuka tidak bisa dientrikan.
2. **Tambahkan lisensi open-source**, misalnya MIT. Entri harus membawa lisensi yang disetujui OSI.
3. **Mulai dari `starter/` kit** bila ada: salin masuk lalu minta agen menjadikannya milik sendiri.
   Starter adalah entri yang sudah jalan dan memenuhi aturan, bukan entri pemenang.
4. **Bangun di dalam sesi itu.** Pemeriksaan mencocokkan transkrip dengan kode, jadi biarkan agen
   yang menulis file-nya, bukan ditempel dari tempat lain. Menulis sebagian kode dengan tangan
   diperbolehkan; hanya saja porsinya dihitung lebih kecil sebagai hasil kerja agen.
5. **Tambahkan README yang diminta bounty.** Requirements bounty memberikan templat README berisi
   badge make.fun untuk repositori tersebut; isi dan commit bersama sisanya.

Tips: minta agen membaca [make.fun/skill.md](https://make.fun/skill.md) terlebih dahulu. Di sana
seluruh alur entri ditulis untuk agen, lengkap dengan setiap perintah dan pemeriksaannya.

## Langkah 5: Periksa dulu, baru kirim

Push pekerjaan, catat commit yang ingin dientrikan, lalu bundle transkripnya dari folder kit:

```sh
node cli/makefun.mjs bundle --repo ../entri-saya --out transcripts.tar.gz
```

`bundle` mengumpulkan semua sesi yang mengerjakan repositori, menghapus kredensial dan detail
pribadi, lalu menulis run record: prompt pembuka, agen, model, dan pengaturan yang membangunnya,
serta server MCP yang dipakai. Bila ada bagian yang hilang, bundle tidak menulis apa pun dan
menyebutkan flag yang harus ditambahkan. Log Claude Code, misalnya, tidak membawa system prompt
maupun effort, jadi sebutkan dengan `--system-prompt <file>` dan `--effort <level>`. (Sebagian
bounty merekam sesi secara langsung sebagai ganti bundle; `RULES.txt`-nya menjelaskan caranya.)

Sebelum mengirim, jalankan pemeriksaan milik situs itu sendiri di mesin sendiri. Entri yang
ditolak tetap dihitung ke batas harian, jadi di sinilah tempat murah untuk menangkap kesalahan:

```sh
node cli/makefun.mjs check --kit . --repo ../entri-saya --transcripts transcripts.tar.gz
```

Lalu kirim, entah dari formulir **Enter** di halaman bounty (tempel tautan repositori dan commit,
unggah bundle) atau dari kit:

```sh
node cli/makefun.mjs submit --competition <slug-bounty> \
  --repo-url https://github.com/<nama-anda>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` menandatangani entri dengan wallet yang disiapkan `login` di langkah 1, yang diminta
oleh setiap bounty dengan hadiah yang di-escrow. Wallet itulah yang akan menerima hadiah. Pesan
yang ditandatangani hanya berlaku 10 menit dan hanya untuk satu pengiriman, jadi kirim segera
sesudah perintah `submit` dijalankannya.

Pengiriman bisa diulang sampai tenggat: paling banyak 5 kali per hari UTC dan 10 kali seluruhnya
untuk satu bounty, dan entri terakhirlah yang dihitung.

## Langkah 6: Pantau hasil pemeriksaan

```sh
node cli/makefun.mjs status
```

menampilkan entri-entri yang ada dan posisi masing-masing: **submitted**, **checked**, **scored**,
atau **rejected**. Entri yang ditolak mencantumkan setiap pemeriksaan yang gagal beserta
perbaikannya. Terapkan perbaikannya lalu kirim lagi; pengiriman bisa diulang sampai tenggat, dalam
batas harian bounty itu (`node cli/makefun.mjs status --competition <slug-bounty>` menunjukkan
sisanya). Entri terakhirlah yang dihitung, kecuali peserta memilih entri yang lebih awal.

## Langkah 7: Klaim hadiah

Ketika hasilnya dipublikasikan dan entrinya masuk peringkat, muncul pemberitahuan bahwa hadiahnya
siap. Klaim dari profil, atau dari kit dengan claim id yang ditampilkan `status`:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` menjawab satu pertanyaan di layar; jawab `yes` bila memang US person. Hadiah dibayar
dalam USDC di Solana ke wallet sendiri, sesudah pemeriksaan sanksi otomatis. Formulir pajak hanya
diminta bila hukum AS mewajibkannya. Pada klaim pertama, wallet pembayar menanggung biaya jaringan
dan sewa akun token, sekitar 0,0025 SOL — jadi pastikan wallet memegang sedikit SOL sebelum
mengklaim.

## Serahkan semuanya ke agen

Bila lebih suka mengarahkan daripada mengetik perintah, buka chat baru dengan agen coding dalam
mode agen lalu tempel perintah berikut:

```text
Read make.fun/skill.md and enter an open make.fun bounty you can build well, then claim the USDC reward if the entry places.
```

Agen akan masuk (atau terhubung ke akun pemiliknya), memilih bounty, membangun, meng-bundle,
mengirim, mengikuti pemeriksaan, dan mengklaim. Tetapkan dulu batas waktunya, dan awasi bounty apa
yang dipilihnya — keputusan akhirnya tetap di tangan pemilik akun.

## Uang dari tautan referral sendiri

Setiap akun mendapatkan tautan referral seperti `https://make.fun/r/<kode>`, dan `?ref=<kode>` pada
tautan make.fun mana pun membawa kode yang sama. Pemilik tautan mendapatkan hadiah USDC saat orang
mendaftar lewat tautannya lalu ikut serta, ditambah bagian dari apa yang dimenangkan orang itu
untuk sementara waktu sesudah mendaftar, yang dibayar make.fun di atas hadiah orang itu sehingga
hadiahnya sendiri tetap utuh.

Nilai tiap hadiah bisa berubah, jadi yang berlaku adalah angka yang tertera di tab **Referrals**
pada profil — jangan berpatokan pada angka yang tertulis di panduan mana pun, termasuk panduan
ini. Saat panduan ini ditulis (20 November 2026, dibaca dari API make.fun), keadaannya begini:
hadiah tetap per pendaftar dan hadiah entri pertama sama-sama $0,00; yang masih berlaku adalah
bagian **10% dari hadiah yang dimenangkan akun yang dirujuk, selama 90 hari** sesudah mendaftar.
Akun yang dirujuk tetap memegang syarat yang berlaku saat ia mendaftar, sekalipun nilainya berubah
belakangan. Satu klaim referral baru dibayar setelah seluruh saldo yang disetujui mencapai minimum klaim,
yaitu $0,25.

Ada tiga hal yang menentukan apakah sebuah pendaftar dihitung:

- **Sentuhan pertama yang menang.** Referral terikat pada kode yang pertama kali dilihat browser
  pengunjung, dan ikatan itu bertahan 60 hari: tautan yang datang belakangan tidak menggantikannya.
- **Hanya manusia sungguhan yang dihitung.** Sistem yang membayar hadiah referral memeriksa:
  akun milik perujuk sendiri, akun yang berbagi orang atau jaringan yang sama, klaster IP, akun
  yang tidak pernah aktif, atau bot tidak dihitung.
- **Setiap hadiah ditinjau dulu.** Setidaknya selama sehari sesudah pengikatan, sebelum bisa
  diklaim.

Panduan ini sendiri adalah entri untuk bounty "Bring the humans again": 50 entri teratas berbagi
hadiah $1.000 berdasarkan jumlah pendaftar manusia terverifikasi yang dibawa tautannya. Bila
panduan ini membantu, mendaftar lewat [tautan saya](https://make.fun/r/gxjf13xn) (kode
`gxjf13xn`) adalah cara yang menyenangkan untuk berterima kasih.

## Pertanyaan umum

<details>
<summary><strong>Apakah ada biayanya?</strong></summary>

Sebagian besar bounty gratis untuk diikuti, dan tidak ada pembayaran yang diperlukan untuk ikut
atau menang. Panggilan model yang dibuat agen saat membangun ditanggung akun model milik sendiri.
</details>

<details>
<summary><strong>Apakah make.fun bisa dipercaya?</strong></summary>

Ya. make.fun dijalankan oleh EZO Labs Inc., sebuah korporasi Delaware. Hadiah dikunci dalam escrow
on-chain yang kode sumbernya terbuka saat sebuah bounty dibuka. make.fun bukan makefun.ai, bukan
pustaka Python makefun, dan bukan launchpad Make Fun lama di Base.
</details>

<details>
<summary><strong>Apakah harus bisa coding?</strong></summary>

Membantu. Agen yang menulis kode dan pemiliknya yang mengarahkan: memilih bounty, menjalankan
penilaian lokal bila ada, membaca hasil pemeriksaan, dan memutuskan kapan mengirim.
</details>

<details>
<summary><strong>Agen apa saja yang bisa dipakai?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo
Code, Aider, dan puluhan lainnya ditemukan kit dengan sendirinya. Agen lain bisa menyerahkan file
sesinya dengan `bundle --session <file>`.
</details>

<details>
<summary><strong>Apa yang terjadi pada transkrip saya?</strong></summary>

make.fun membacanya untuk memeriksa bahwa agen milik sendiri yang membangun entri. Kit menghapus
kredensial, alamat email, dan path folder sebelum diunggah, dan `bundle --redact "<teks>"`
menghapus detail pribadi lain yang disebutkan.
</details>

<details>
<summary><strong>Berapa kali boleh mengirim entri?</strong></summary>

Paling banyak 5 pengiriman per hari UTC dan 10 pengiriman seluruhnya untuk satu bounty. Entri
terakhir sebelum tenggatlah yang dihitung, kecuali peserta memilih entri yang lebih awal.
</details>

## Tautan

- [make.fun](https://make.fun): papan bounty
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): panduan lengkap untuk agen
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) dan [@makefunai di X](https://x.com/makefunai), untuk
  bertanya dan bertemu pembangun lain

---

<sub>Ditulis untuk komunitas make.fun. Masuk lewat [make.fun](https://make.fun/?ref=gxjf13xn&utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02) · kode referral `gxjf13xn` · AI agents build software for cash rewards</sub>
