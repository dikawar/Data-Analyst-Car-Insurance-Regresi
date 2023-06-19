# Data-Analyst-Car-Insurance-Regresi

Link Persentasi Video https://drive.google.com/file/d/19IO4K4OQI-pC6NBSs-pQy0j0Wq8h1Suc/view?usp=sharing

## **1. Business Problem Understanding**
---
**1.1. Context**

Sebuah perusahaan yang bergerak di bidang car insurance ingin meningkatkan income dan profitnya.
Dari data customernya perusahaan ingin melakukan evalusi mengenai aspek apa saja yang dapat memberikan pengaruh dalam peningkatan profit perusahaan.

Target yang akan digunakan untuk evalusai customer adalah dengan menggunakan nilai customer lifetime value (CLV). CLV adalah ukuran yang digunakan oleh perusahaan untuk menentukan nilai finansial yang dapat dihasilkan dari sebuah pelanggan selama periode waktu tertentu, biasanya sepanjang hubungan bisnis mereka.

Secara sederhana, CLV adalah prediksi atas nilai total pendapatan yang bisa perusahaan dapatkan dari customernya. Semakin besar CLV maka semakin besar juga profit perusahaan

**1.2. Problem Statement**
 
Permasalahan perusahaan car insurance ini adalah bagaimana perusahaan membuat strategi baru untuk meningkatkan income dan profit perusahaan sehingga dapat mengembangkan bisnisnya lebih besar ?

**1.3. Goals**

Perusahaan car insurance ini perlu memiliki model ML yang dapat memprediksi CLV, sehingga dapat membantu untuk membuat startegi yang tepat dalam memberikan income dan profit kepada perusahaan.

**1.4. Analytic Approach**

Jadi, yang perlu kita lakukan adalah menganalisis data untuk dapat menemukan pola dari fitur-fitur yang ada, yang dapat membedakan satu customer dengan yang lainnya.

Selanjutnya, kita akan membangun suatu model ML regresi yang akan membantu perusahaan untuk dapat memprediksi CLV dari setiap customer, sehingga akan berguna untuk menentukan aspek apa saja yang berpengaruh dalam memberikan profit kepada perusahaan dan perusahaan bisa mengambil keputusan bisnis yang tepat dari nilai CLV yang diprediksi model.

**1.5. Metric Evaluation**

Evaluasi metrik yang akan digunakan yaitu:
- RMSE adalah nilai rataan akar kuadrat dari error 
- MAE adalah rataan nilai absolut dari error
- MAPE adalah rataan nilai persentase error yang dihasilkan oleh model regresi
- R-squared adalah nilai seberapa baik model dapat merepresentasikan varians keseluruhan data

Semakin kecil nilai RMSE, MAE, dan MAPE yang dihasilkan, berarti model semakin akurat dalam memprediksi sesuai dengan limitasi fitur yang digunakan. 

Semakin mendekati 1 nilai R-squared yang dihasilkan, berarti semakin fit pula modelnya terhadap data observasi.

- Dataset yang digunakan berisi informasi customer dan informasi polis asuransi mereka dari sejak awal menggunakan asuransi perusahaan car insurance.
- Setiap baris data merepresentasikan informasi terkait keterangan seorang customer dengan polis asuransi kendaraan miliknya.

**Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| Vehicle Class             | Object    | Tipe kendaraan |
| Coverage                  | Object    | Jenis pertanggungan polis asuransi customer |
| Renew Offer Type          | Object    | Penawaran untuk pembaruan polis |
| EmploymentStatus          | Object    | Status pekerjaan cutomer |
| Marital Status            | Object    | Status pernikahan cutomer |
| Education                 | Object    | Tingkat pendidikan customer |
| Number of Policies        | Float     | Jumlah polis yang dimiliki customer |
| Monthly Premium Auto      | Float     | Premi customer perbulan (USD) |
| Total Claim Amount        | Float     | Jumlah claim customer (USD) |
| Income                    | Float     | Pendapatan cutomer (USD) |
| Customer Lifetime Value   | Float     | Customer Lifetime Value (Target) |


# **7 Conclusion**
---
Dari model yang sudah dibuat, model terbaik yang dipilih untuk memprediksi CLV adalah XGBoost. Metrik evaluasi yang digunakan pada model adalah nilai RMSE, MAE, MAPE, dan R-squared. Jika dilihat dari nilai MAPE yang dihasilkan oleh model setelah dilakukan hyperparameter tuning, yaitu sekitar 3.9%, bisa disimpulkan bahwa jika nanti model yang kita buat ini digunakan untuk memprediksi Customer Lifetime Value pada rentang nilai seperti yang dilatih terhadap model, maka hasil prediksi CLVnya rata-rata dapat meleset kurang lebih sekitar 3.9% dari CLV yang seharusnya.

Tapi, tidak menutup kemungkinan juga prediksinya meleset jauh karena bias yang dihasilkan model masih cukup tinggi. Bila dilihat dari visualisasi antara CLV aktual dan prediksi serta residual performa prediksi model mulai menurun ketika CLV sekitar 8.000 keatas. Bias yang dihasilkan oleh model ini dikarenakan oleh terbatasnya fitur pada dataset dan model butuh lebih banyak data customer lagi untuk model di maintance kedepannya menjadi lebih baik dan agar bias yang dihasilkan tidak teralu jauh dari hasil prediksi.

Dari pemodelan yang sudah dilakukan, perusahaan memiliki model untuk memprediksi nilai Customer Lifetime Value, maka model ini dapat membantu bussiness problem mengenai perhitungan biaya maksimal untuk akuisisi customer. Perusahaan dapat mengatur agar biaya akuisisi tidak sampai melebihi CLV atau sebisa mungkin jauh lebih rendah dibanding CLV agar perusahaan mendapat profit maksimal.

# **8. Recommendation Model**
---
Hal-hal yang dapat dilakukan untuk mengembangkan model agar lebih baik lagi yaitu:

- Eksperimen dalam manipulasi data 
- Eksperimen menggunakan model machine learning lainnya
- Eksperimen hyperparameter tuning lainnya
- Penambahan fitur lain yang behubungan dengan informasi polis customer, seperti informasi berapa bulan lamanya customer sudah menggunakan asuransi dari perusahaan ini.
- Mengecek prediksi data mana saja yang menghasilkan nilai error tinggi. lalu melakukan analisa hubungan antara error tersebut dengan setiap variable independen dengan tujuan untuk mengetahui sebenarnya variable mana saja yang menyebabkan prediksi model menghasilkan error yang tinggi.



**Recommandation Business :**

1. Segmentasi Pelanggan: perusahaan dapat melakukan segmentasi pelanggan yang lebih efektif berdasarkan nilai CLV pelanggan, sehingga dapat menyusun strategi pemasaran yang tepat untuk setiap segmen. Misalnya, segmen dengan CLV 20000 ke atas mungkin menjadi target penawaran khusus atau program loyalitas yang eksklusif.

2. Melakukan Cross-Selling dan Up-Selling, perusahaan dapat menargetkan pelanggan dengan Segmentasi CLV untuk penawaran cross-selling atau up-selling. Bisa dengan perusahaan menawarkan paket asuransi tambahan dengan diskon yang menarik atau meningkatkan perlindungan asuransi kepada pelanggan yang memiliki potensi untuk meningkatkan nilai polis mereka, bisa lebih difokuskan kepada segmentasi pelanggan dengan CLV 20000 ke bawah agar CLV populasi customer kedepannya  meningkat dari 20000 ke bawah menjadi 20000-60000. dengan ini jumblah polis customer dengan CLV 20000 ke atas akan meningkat. Dengan meningkatnya CLV Customer maka pembayaran Premi perbulannya juga akan meningkat sesuai dengan EDA, ini akan meningkatkan profit dan income perusahaan. 

3. Pengembangan Produk dan Layanan: Perusahaan dapat menggunakan informasi prediksi CLV untuk mengembangkan produk dan layanan baru yang sesuai dengan kebutuhan pelanggan yang berharga, meningkatkan kepuasan pelanggan, dan memperkuat loyalitas mereka. perusahaan dapat meluncurkan polis asuransi khusus untuk segmen pelanggan dengan CLV 20000 ke atas dengan manfaat tambahan seperti perlindungan hukum atau asuransi penyewaan mobil. 

4. Pengelolaan Biaya Akuisisi Pelanggan dan mengoptimalkan pengeluaran pemasaran yang lebih tertarget, biasanya biaya akuisisi pelanggan cukup tinggi. Dengan mengetahui CLV, perusahaan dapat menghitung kembali keseimbangan antara biaya akuisisi dan nilai jangka panjang yang diharapkan dari pelanggan. Ini dapat membantu perusahaan dalam mengoptimalkan pengeluaran pemasaran dan mengalokasikan sumber daya dengan lebih efisien. 

5. Retensi Pelanggan, Perusahaan dapat memfokuskan upaya retensi pada pelanggan dengan CLV 20000 ke atas atau tinggi. Ini bisa dilakukan dengan memberikan pelayanan pelanggan yang baik, penawaran khusus, atau program loyalitas yang dirancang untuk mempertahankan pelanggan berharga.


Secara keseluruhan, dengan kemampuan memprediksi CLV, perusahaan asuransi mobil dapat mengoptimalkan strategi pemasaran, meningkatkan retensi pelanggan, meningkatkan penjualan produk, mengelola biaya akuisisi pelanggan, dan mengembangkan produk dan layanan yang lebih baik. Hal ini dapat berdampak positif pada keuntungan jangka panjang perusahaan, meningkatkan pertumbuhan bisnis, dan memperkuat posisi persaingan di industri asuransi mobil.
