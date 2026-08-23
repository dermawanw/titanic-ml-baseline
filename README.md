# Titanic ML Baseline

Baseline klasifikasi untuk kompetisi [Titanic: Machine Learning from Disaster](https://www.kaggle.com/competitions/titanic). Repo ini sedang dikerjakan; belum ada skor atau klaim hasil sampai submission valid tercatat.

## Ringkasan

- **Apa:** memprediksi apakah seorang penumpang selamat berdasarkan data penumpang.
- **Tujuan:** menghasilkan baseline yang dapat dijalankan ulang dan satu submission Kaggle yang valid.
- **Mengapa:** proyek kecil ini menguji alur kerja ML lengkap—data, validasi, model, prediksi, dan evaluasi.
- **Cara kerja:** data latih dibersihkan, fitur diproses, model dilatih, lalu prediksi untuk data uji disimpan dalam format submission.

## Target tujuh hari

1. Memahami kolom, missing values, dan target `Survived`.
2. Menentukan validation split serta metrik accuracy.
3. Membuat baseline sederhana dengan pipeline scikit-learn.
4. Mengirim satu submission valid dan mencatat skornya.
5. Mencoba satu perbaikan yang terukur terhadap baseline.

## Struktur

```text
data/       petunjuk data; file kompetisi tidak disimpan di Git
notebooks/  eksplorasi dan eksperimen
src/        kode final yang dapat digunakan ulang
reports/    hasil, skor, dan keterbatasan
```

## Menyiapkan environment

```powershell
conda env create -f environment.yml
conda activate titanic-ml
jupyter lab
```

Unduh data mengikuti [petunjuk di folder data](data/README.md). Jangan commit atau membagikan ulang file kompetisi.

## Bukti hasil

Bagian ini akan diperbarui setelah tersedia:

- Skor validasi: belum tersedia.
- Skor Kaggle: belum tersedia.
- Commit eksperimen terbaik: belum tersedia.

## Lisensi

Kode tersedia dengan [MIT License](LICENSE). Dataset tetap mengikuti aturan dan lisensi Kaggle.
