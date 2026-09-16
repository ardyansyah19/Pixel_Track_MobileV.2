# Block Star Tetris
By Ahmad Riko Dyansyah

Game Tetris mobile berwarna-warni, dibuat dengan **Flutter (Dart)**.
Target pemain: anak-anak & remaja.

## Fitur
- 3 level kesulitan: **Easy, Medium, Hard** (mempengaruhi kecepatan jatuh & kenaikan level)
- **High score otomatis tersimpan** per level (pakai `shared_preferences`, tetap ada walau app ditutup)
- Next piece & Hold piece preview
- Kontrol swipe (geser kiri/kanan, geser bawah = hard drop, tap = rotate) + tombol on-screen
- Tampilan gradasi ungu + starfield + blok warna-warni bergaya "candy/neon" yang ramah anak

## Struktur Proyek
```
lib/
  main.dart                  -> entry point & tema
  models/
    tetromino.dart            -> 7 bentuk balok (I,O,T,S,Z,J,L) + warna
    difficulty.dart            -> pengaturan Easy/Medium/Hard
  game/
    board.dart                -> papan 10x20, validasi posisi, clear baris
    game_logic.dart            -> loop permainan, skor, level, hold
  widgets/
    board_widget.dart          -> render papan & balok
    mini_piece_preview.dart    -> panel NEXT / HOLD
    star_background.dart       -> background starfield dekoratif
  screens/
    home_screen.dart           -> menu utama + pilih level + high score
    game_screen.dart           -> layar permainan + kontrol + overlay game over
```

## Cara Menjalankan
1. Install Flutter SDK: https://docs.flutter.dev/get-started/install
2. Buat project baru sebagai wadah platform (Android/iOS/Web), lalu timpa `lib/` dan `pubspec.yaml` dengan isi dari zip ini:
   ```bash
   flutter create block_star_tetris
   cd block_star_tetris
   # copy folder lib/ dan file pubspec.yaml dari zip ini ke sini (replace)
   flutter pub get
   flutter run
   ```
   *(Alternatif: jika kamu sudah punya project Flutter kosong, cukup timpa isi `lib/` dan `pubspec.yaml`-nya dengan yang ada di zip ini.)*
3. Untuk build APK Android:
   ```bash
   flutter build apk --release
   ```

## Kustomisasi Lanjutan (opsional)
- Ganti warna tema di `main.dart` / `star_background.dart`.
- Tambah efek suara saat baris hilang (pakai package `audioplayers`).
- Tambah ikon aplikasi custom lewat package `flutter_launcher_icons`.
- Tambah animasi flash saat baris penuh dihapus di `board_widget.dart`.

Selamat bermain & selamat coding, Riko! 🎮
