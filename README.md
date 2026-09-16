## Key Insights

Analisis dilakukan terhadap 1.409 pelanggan (test set, 20% dari total 7.043 data) menggunakan model Random Forest Classifier untuk memprediksi churn pelanggan telekomunikasi.

### Model Performance
- **Accuracy:** 80%
- **Recall (Churn class):** 47% — model berhasil mendeteksi 175 dari 373 pelanggan yang benar-benar churn
- **Precision (Churn class):** 67%
- Karena data churn imbalanced (26.5% churn vs 73.5% tidak churn), akurasi saja tidak cukup merepresentasikan performa model — recall menjadi metrik penting untuk kasus ini, dan masih ada ruang perbaikan (±53% kasus churn aktual belum tertangkap model).

### Churn Drivers
- **Jenis kontrak** adalah faktor paling dominan: pelanggan dengan kontrak *month-to-month* memiliki churn rate **42.9%**, jauh lebih tinggi dibanding kontrak *one year* (8.8%) dan *two year* (2.8%).
- **Metode pembayaran** *electronic check* memiliki churn rate tertinggi (**46.4%**), lebih dari 2x lipat dibanding metode otomatis seperti bank transfer (13.7%) atau credit card (15.3%).
- **Layanan internet fiber optic** berkorelasi dengan churn rate lebih tinggi (**43.3%**) dibanding DSL (18.0%) — kemungkinan terkait harga layanan yang lebih mahal atau ekspektasi kualitas yang tidak terpenuhi.
- **Lama berlangganan (tenure)** berbanding terbalik dengan churn: pelanggan baru (0-12 bulan) memiliki churn rate **47.3%**, turun signifikan menjadi 7.4% pada pelanggan dengan tenure 60-72 bulan. Periode awal berlangganan adalah fase paling kritis untuk retensi.

### Risk Segmentation
Dari 1.409 pelanggan pada test set, model mengklasifikasikan:
- **1.017 pelanggan** — Low Risk
- **258 pelanggan** — Medium Risk
- **134 pelanggan** — High Risk (kandidat prioritas untuk intervensi retensi)

### Business Recommendation
Berdasarkan temuan di atas, strategi retensi sebaiknya difokuskan pada pelanggan baru (tenure rendah) dengan kontrak month-to-month dan metode pembayaran electronic check — kombinasi ini menunjukkan profil risiko churn tertinggi dan bisa menjadi target program retensi (misalnya insentif migrasi ke kontrak tahunan atau metode pembayaran otomatis).
