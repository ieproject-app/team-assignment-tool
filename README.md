# 🎲 Team Randomizer

Alat pembagi tim otomatis yang modern dan responsif dengan dukungan ekspor Excel. Aplikasi web client-side yang dapat langsung digunakan tanpa instalasi backend.

## ✨ Fitur Utama

**🔄 Pembagian Tim Otomatis**
- Distribusi peserta secara acak dan seimbang
- Penanganan overflow otomatis (membuat tim tambahan jika diperlukan)
- Algoritma round-robin untuk distribusi yang adil

**📱 Desain Responsif Modern**
- Interface bersih dengan gradien dan animasi halus
- Optimized untuk desktop, tablet, dan mobile
- CSS Grid layout yang fleksibel

**📊 Integrasi Excel**
- Format output tab-separated untuk Excel
- Tombol copy-to-clipboard satu klik
- Instruksi lengkap untuk import ke Excel

**⚡ Performa Tinggi**
- Aplikasi client-side murni (no backend required)
- Dapat dijalankan offline setelah dimuat
- Ready untuk deploy di GitHub Pages

## 🚀 Demo Langsung

[**🔗 Coba Team Randomizer**](https://your-username.github.io/team-randomizer)

*Ganti `your-username` dengan username GitHub Anda*

## 🛠️ Cara Penggunaan

### Langkah Dasar
1. **Masukkan Konfigurasi Tim**
   - Tentukan jumlah tim yang diinginkan
   - Atur jumlah anggota per tim

2. **Input Nama Peserta**
   - Ketik atau paste nama peserta (satu nama per baris)
   - Aplikasi sudah menyediakan data contoh untuk testing

3. **Generate Tim**
   - Klik tombol "Generate Teams"
   - Sistem akan secara otomatis membuat tim tambahan jika peserta melebihi kapasitas

4. **Export ke Excel**
   - Klik "Copy to Clipboard" pada bagian Excel-Ready Format
   - Paste ke Excel
   - Gunakan Data → Text to Columns → Delimited → Tab

### Contoh Skenario
- **Input**: 20 peserta, 3 tim, 6 anggota per tim
- **Output**: 4 tim (3 tim utama + 1 tim tambahan untuk 2 peserta sisanya)

## 🏗️ Instalasi dan Deploy

### GitHub Pages (Recommended)
```bash
# Fork atau clone repository ini
git clone https://github.com/your-username/team-randomizer.git
cd team-randomizer

# Push ke GitHub repository Anda
git add .
git commit -m "Initial commit"
git push origin main

# Aktifkan GitHub Pages di repository settings
# Pilih source: Deploy from branch → main → / (root)
```

### Local Development
```bash
# Clone repository
git clone https://github.com/your-username/team-randomizer.git
cd team-randomizer

# Buka dengan web server lokal (contoh dengan Python)
python -m http.server 8000

# Atau buka langsung file index.html di browser
open index.html
```

### Hosting Alternatives
- **Netlify**: Drag & drop folder ke netlify.com
- **Vercel**: Import dari GitHub repository
- **Surge.sh**: `npm install -g surge && surge`

## 🏗️ Arsitektur Teknis

### Teknologi yang Digunakan
- **HTML5**: Struktur semantik dan accessibility
- **CSS3**: Grid layout, Flexbox, gradients, animations
- **Vanilla JavaScript**: ES6+ features, modern APIs
- **Google Fonts**: Typography (Inter font family)

### Algoritma Pembagian Tim
```javascript
// Pseudocode untuk algoritma round-robin
shuffledParticipants.forEach((participant, index) => {
    const teamIndex = index % totalTeams;
    teams[teamIndex].members.push(participant);
});
```

Algoritma ini memastikan distribusi yang seimbang dengan cara:
- Mengacak urutan peserta menggunakan Fisher-Yates shuffle
- Mendistribusikan peserta secara bergiliran ke setiap tim
- Otomatis menambah tim baru jika peserta melebihi kapasitas

### Struktur File
```
team-randomizer/
├── index.html          # File utama (self-contained)
├── README.md           # Dokumentasi ini
├── LICENSE             # MIT License
└── assets/             # Optional: screenshot dan demo files
    ├── screenshot.png
    └── demo.gif
```

## 🎨 Kustomisasi

### Mengubah Tema Warna
Edit variabel CSS di bagian `:root` atau ubah gradient values:
```css
/* Gradient utama */
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);

/* Warna tombol */
background: linear-gradient(135deg, #10b981 0%, #059669 100%);
```

### Menambah Validasi Input
Tambahkan validasi khusus di function `generateTeams()`:
```javascript
if (participants.length < numTeamsInput) {
    alert('Jumlah peserta harus lebih besar dari jumlah tim!');
    return;
}
```

### Mengubah Format Output
Modifikasi function `generateTextOutput()` untuk mengubah format ekspor:
```javascript
// Contoh: CSV format instead of TSV
output += `${team.name},"${member}"\n`;
```

## 🔧 Troubleshooting

### Masalah Umum dan Solusi

**❌ Tim tidak terbagi rata**
- **Penyebab**: Jumlah peserta tidak habis dibagi jumlah tim
- **Solusi**: Sistem otomatis membuat tim tambahan untuk peserta sisanya

**❌ Copy to clipboard tidak berfungsi**
- **Penyebab**: Browser tidak mendukung Clipboard API
- **Solusi**: Aplikasi otomatis fallback ke method lama

**❌ Layout rusak di mobile**
- **Penyebab**: Browser lama atau zoom level tidak standar
- **Solusi**: Reset zoom browser atau update browser

**❌ Excel tidak memisahkan kolom**
- **Penyebab**: Delimiter tidak terdeteksi otomatis
- **Solusi**: Manual pilih Tab sebagai delimiter di Text to Columns

## 🤝 Kontribusi

Kami sangat welcome kontribusi dari komunitas! Berikut cara berkontribusi:

### Reporting Issues
- Gunakan GitHub Issues untuk melaporkan bug
- Sertakan screenshot dan langkah reproduksi
- Sebutkan browser dan device yang digunakan

### Pull Requests
1. Fork repository ini
2. Buat branch baru: `git checkout -b feature-amazing-feature`
3. Commit changes: `git commit -m 'Add amazing feature'`
4. Push ke branch: `git push origin feature-amazing-feature`
5. Submit Pull Request dengan deskripsi lengkap

### Development Guidelines
- Gunakan semantic commit messages
- Test di minimal 3 browser berbeda
- Pastikan responsive design tetap berfungsi
- Tambahkan comments untuk logic kompleks

### Ideas untuk Enhancement
- Export ke format CSV/JSON
- Import dari file Excel/CSV
- Preset konfigurasi tim (olahraga, akademik, dll)
- History/undo functionality
- Team balancing berdasarkan kriteria tertentu
- Print-friendly layout
- Dark mode theme
- Internationalization (i18n)

## 📄 License

Proyek ini menggunakan [MIT License](LICENSE) - lihat file LICENSE untuk detail lengkap.

```
MIT License - Bebas digunakan untuk proyek personal maupun komersial
```

## 🙏 Acknowledgments

- **Fisher-Yates Algorithm**: Untuk random shuffling yang unbiased
- **CSS Grid**: Untuk layout responsif yang fleksibel
- **Inter Font**: Typography yang modern dan readable
- **Community**: Untuk feedback dan kontribusi

## 📞 Support

Jika Anda mengalami masalah atau memiliki pertanyaan:

- **GitHub Issues**: [Create new issue](https://github.com/your-username/team-randomizer/issues)
- **Email**: your-email@example.com
- **Discussion**: Gunakan GitHub Discussions untuk pertanyaan umum

---

**⭐ Jika proyek ini berguna, jangan lupa berikan star di repository ini!**

Made with ❤️ by [Your Name] | [Website](https://your-website.com) | [LinkedIn](https://linkedin.com/in/yourprofile)
