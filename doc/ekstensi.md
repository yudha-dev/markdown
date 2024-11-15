# Markdown Preview Enhanced

[Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced) adalah ekstensi untuk Visual Studio Code yang memperkaya pengalaman dalam membaca dan menulis file Markdown. Ekstensi ini menyediakan berbagai fitur tambahan yang memudahkan pengguna dalam membuat dokumentasi, termasuk fitur visualisasi dan rendering canggih untuk konten Markdown.

## Fitur Utama

- **Preview Real-Time**: Menampilkan preview Markdown secara real-time saat Anda mengetik.
- **Rendering Table of Contents (ToC)**: Membuat daftar isi otomatis berdasarkan header Markdown.
- **Diagram dan Chart**: Mendukung berbagai diagram seperti mermaid, chart.js, plantUML, dan lainnya.
- **Export**: Mendukung ekspor ke berbagai format seperti PDF, HTML, pandoc, dan lainnya.
- **Code Block Rendering**: Mendukung rendering untuk berbagai bahasa pemrograman dan menyorot sintaks secara otomatis.
- **Math Support**: Mendukung persamaan matematika dengan syntax LaTeX dan KaTeX.

## Instalasi

1. Buka Visual Studio Code.
2. Pergi ke Extensions (dengan shortcut `Ctrl+Shift+X`).
3. Cari "Markdown Preview Enhanced" dan pilih ekstensi yang dibuat oleh `shd101wyy`.
4. Klik `Install` untuk menginstal ekstensi ini.

## Cara Menggunakan

1. **Membuka Preview**:
   - Buka file Markdown (.md) yang ingin Anda lihat.
   - Tekan `Ctrl+Shift+V` untuk membuka preview di samping editor.
   - Anda juga dapat menggunakan perintah **Markdown Preview Enhanced: Open Preview** dari Command Palette (`Ctrl+Shift+P`).

2. **Menyisipkan Diagram**:
   - Markdown Preview Enhanced mendukung diagram menggunakan sintaks seperti berikut:
     ```markdown
     mermaid
     graph TD;
         A-->B;
         A-->C;
         B-->D;
         C-->D;
     ```
   - Ekstensi ini akan secara otomatis merender diagram saat Anda menyimpannya.

3. **Ekspor File**:
   - Gunakan Command Palette (`Ctrl+Shift+P`) dan pilih **Markdown Preview Enhanced: Export**. Pilih format seperti PDF, HTML, atau PNG.

## Shortcut Penting

- `Ctrl+Shift+V`: Membuka preview di jendela terpisah.
- `Ctrl+K V`: Membuka preview di samping editor.
- `Ctrl+Shift+P`: Membuka Command Palette untuk mengakses semua perintah Markdown Preview Enhanced.

## Konfigurasi

Anda dapat mengonfigurasi ekstensi ini dengan membuka Settings (File > Preferences > Settings) dan mencari "Markdown Preview Enhanced". Di sini Anda dapat mengatur berbagai preferensi seperti tema tampilan, format ekspor, dan pilihan rendering.