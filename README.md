# Pipeline
Sitti khairunnisak

Username dicoding:

| | Deskripsi |
| ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Dataset | [_Taxi Trips_ dataset] (https://raw.githubusercontent.com/tensorflow/tfx/master/tfx/examples/chicago_taxi_pipeline/data/simple/data.csv)) |
| Masalah | Permasalahan dengan adanya solusi _taxi trip_ di Chicago adalah adanya masyarakat penyandang disabilitas yang tidak dapat menggunakan transportasi umum sehingga taksi menjadi solusi menyediakan alternatif transportasi penting bagi penyandang disabilitas. Adanya kemacetan lalu lintas dan dengan taksi dapat memberikan layanan transportasi yang efisien, terutama untuk perjalanan jarak pendek, sehingga mengurangi kemacetan lalu lintas dan meningkatkan efisiensi transportasi secara keseluruhan. Industri taksi juga dapat menjadi solusi menyediakan lapangan kerja bagi pengemudi dan berkontribusi terhadap perekonomian lokal. Analisis data: Kumpulan data perjalanan taksi memberikan wawasan berharga mengenai permintaan transportasi taksi dan dapat digunakan untuk mengoptimalkan layanan taksi, meningkatkan keselamatan, dan meningkatkan pengalaman pelanggan secara keseluruhan. Pengawasan peraturan: Kota Chicago mengatur industri taksi dan mengumpulkan data perjalanan taksi untuk memastikan kepatuhan terhadap peraturan dan melindungi kepentingan penumpang.|
| Solusi machine learning |Pembelajaran mesin dapat digunakan untuk memprediksi berbagai aspek perjalanan taksi, seperti tarif perjalanan, waktu perjalanan, dan kebiasaan memberi tip kepada penumpang. beberapa solusi yang dapat diperoleh dari model pembelajaran mesin adalah : Prediksi tarif: Model pembelajaran mesin dapat dibuat untuk memprediksi tarif perjalanan taksi berdasarkan berbagai fitur seperti lokasi penjemputan, lokasi pengantaran, jarak, dan waktu. Tantangan Prediksi Tarif Perjalanan Taksi Kaggle menyediakan kumpulan data untuk membuat model tersebut. Prediksi waktu perjalanan: Model pembelajaran mesin dapat dibangun untuk memprediksi waktu tempuh perjalanan taksi berdasarkan berbagai fitur seperti lokasi penjemputan, lokasi pengantaran, jarak, dan waktu. Data Sistem telah membangun model seperti itu untuk memprediksi perkiraan waktu pengemudi akan tetap sibuk dengan taksi. Situs web ProjectPro juga menyediakan proyek untuk membangun model tersebut. Kebiasaan memberi tip penumpang: Model pembelajaran mesin dapat dibangun untuk memprediksi kebiasaan memberi tip penumpang berdasarkan berbagai fitur seperti tarif perjalanan, durasi perjalanan, dan lokasi penjemputan. Secara keseluruhan, pembelajaran mesin dapat digunakan untuk memprediksi berbagai aspek perjalanan taksi, yang dapat membantu perusahaan taksi mengoptimalkan layanannya, meningkatkan pengalaman pelanggan, dan meningkatkan pendapatan. |
| Metode pengolahan | metodenya Pengumpulan data: Kumpulan data perjalanan taksi dikumpulkan dari Kota Chicago dan diunduh untuk digunakan dalam _pipeline_. Pemrosesan awal data: Kumpulan data diproses terlebih dahulu untuk menghilangkan nilai yang hilang, outlier, dan fitur yang tidak relevan. Langkah ini melibatkan pembersihan data, rekayasa fitur, dan transformasi data. Pelatihan model: Model pembelajaran mesin dilatih pada kumpulan data yang telah diproses sebelumnya untuk memprediksi berbagai aspek perjalanan taksi, seperti tarif perjalanan dan waktu perjalanan. Langkah ini melibatkan pemilihan model yang sesuai, menyetel _hyperparameter_, dan mengevaluasi performa model.|
| Arsitektur model | komponen Pelatih dalam _pipeline_ pembelajaran mesin menggunakan _TFX_ dengan kumpulan data perjalanan taksi bertanggung jawab untuk melatih model pembelajaran mesin. Komponen Pelatih menerima modul pelatih, mentransformasikan contoh dari keluaran transformasi, grafik transformasi, skema, serta argumen pelatih untuk langkah-langkah pelatihan dan evaluasi. Komponen Pelatih melatih model pembelajaran mesin pada kumpulan data yang telah diproses sebelumnya untuk memprediksi berbagai aspek perjalanan taksi, seperti tarif perjalanan dan waktu perjalanan. Langkah ini melibatkan pemilihan model yang sesuai, menyetel _hyperparameter_, dan mengevaluasi performa model. Model yang dilatih dikeluarkan untuk ditayangkan, yang melibatkan pembuatan prediksi pada data baru. Langkah ini melibatkan penyiapan infrastruktur penyajian, seperti _REST API_ atau sistem pemrosesan batch. |
| Metrik evaluasi | Pipeline TFX mencakup beberapa komponen yang digunakan untuk mengevaluasi performa model pembelajaran mesin. Komponen ini dirancang untuk menganalisis hasil pelatihan model dan membantu memvalidasi model yang diekspor.Beberapa metrik yang umum digunakan untuk mengevaluasi performa model pembelajaran mesin adalah Akurasi : Proporsi prediksi benar yang dibuat oleh model. Presisi: Proporsi positif sebenarnya di antara jumlah total prediksi positif yang dibuat oleh model. Skor F1: Rata-rata harmonik antara presisi dan perolehan. _AUC-ROC_: Area di bawah kurva karakteristik pengoperasian penerima, yang mengukur kemampuan model untuk membedakan kelas positif dan negatif. Komponen Evaluator di TFX memanfaatkan pustaka Analisis Model TensorFlow untuk melakukan analisis, yang selanjutnya menggunakan _Apache Beam_ untuk pemrosesan yang dapat diskalakan Oleh karena itu, komponen Evaluator adalah bagian penting dari evaluasi performa model pembelajaran mesin di pipeline TFX.|
| Performa model |Melatih model pembelajaran mesin menggunakan Evaluator: Melakukan analisis mendalam terhadap hasil pelatihan model dan membantu memvalidasi model yang _diekspor. InfraValidator_: Memeriksa apakah model benar-benar dapat diservis dari infrastruktur dan mencegah penerapan model buruk. _Pusher_: Menerapkan model pada infrastruktur yang melayani. Komponen Evaluator digunakan untuk melakukan analisis mendalam terhadap hasil pelatihan model dan membantu memvalidasi model yang diekspor. Komponen InfraValidator memeriksa apakah model benar-benar dapat diservis dari infrastruktur dan mencegah model buruk didorong. Terakhir, komponen _Pusher_ menyebarkan model pada infrastruktur layanan. Oleh karena itu, komponen _Evaluator, InfraValidator, dan Pusher_ merupakan bagian dari model kinerja di _pipeline TFX_.|
