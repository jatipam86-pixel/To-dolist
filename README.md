# To-Do List (Jetpack Compose)

Tugas Kelompok Pengembangan Aplikasi Bergerak: UI/UX, MVVM, dan UI State.

## Anggota Kelompok
| Nama | NIM | Kontribusi |
|------|-----|-----------|
| (isi) | (isi) | (isi) |
| (isi) | (isi) | (isi) |
| (isi) | (isi) | (isi) |

## Masalah, Pengguna, dan Solusi
- **Pengguna:** mahasiswa yang memiliki banyak tugas kuliah.
- **Masalah:** tugas mudah terlupa dan sulit dipantau mana yang sudah selesai.
- **Solusi:** aplikasi pencatat tugas sederhana dengan penanda selesai.

## Fitur Inti
1. Tambah tugas (dengan validasi input kosong dan batas 100 karakter).
2. Tandai tugas selesai / belum selesai.
3. Hapus tugas.

## Struktur MVVM
```
data/Task.kt            -> Model
ui/TodoUiState.kt       -> UiState (data class)
ui/TodoViewModel.kt     -> ViewModel (MutableStateFlow privat, StateFlow publik)
ui/TodoScreen.kt        -> Composable (collectAsStateWithLifecycle)
```

## Adaptive Layout
- Lebar < 600dp: form di atas, daftar di bawah (bertumpuk).
- Lebar >= 600dp: form dan daftar berdampingan.

## Contoh Alur UDF (Tambah Tugas)
1. Pengguna mengetik -> `onValueChange` memanggil `viewModel.onInputChange(text)`.
2. ViewModel memperbarui `_uiState` (`input` berubah).
3. UI menerima state baru lewat `collectAsStateWithLifecycle()` dan menampilkan teks.
4. Pengguna menekan "Tambah Tugas" -> `viewModel.addTask()`.
5. Jika kosong, ViewModel mengisi `errorMessage`; jika valid, tugas ditambahkan dan `input` dikosongkan.
6. UI otomatis menampilkan pesan validasi atau daftar tugas terbaru.

## Cara Menjalankan
1. Buka folder proyek di Android Studio (Ladybug atau lebih baru).
2. Tunggu Gradle sync selesai.
3. Jalankan di emulator ponsel (layar sempit) dan tablet/foldable (layar lebar).

## Screenshot
(Tambahkan screenshot layar sempit dan layar lebar di sini.)
