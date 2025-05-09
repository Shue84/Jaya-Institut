# **Proyek Akhir: Menyelesaikan Permasalahan di Jaya Jaya Institut**


*   Nama : Suyanti Witono
*   Email: suyanti.witono@bpkpenaburjakarta.or.id
*   ID Dicoding: suyanti_witono_tFDe

## **1. Project Overview**

> *Dropout* adalah kondisi di mana seseorang diharuskan berhenti dari institusi pendidikan atau tempat kerja sebelum menyelesaikan masa studinya atau kontrak kerjanya. (Dealls, 2025)

Menurut Kemendikbudristek, jumlah mahasiswa dan pelajar di Indonesia yang mengalami *dropout* pada tahun 2021 mencapai 480.449 orang. Angka tersebut cukup tinggi dan memprihatinkan. Apalagi pendidikan adalah hal penting dan merupakan kebutuhan dasar manusia. Pendidikan tinggi yang berkualitas juga merupakan hak bagi seluruh warga negara.

Beberapa faktor yang mempengaruhi tingkat putus sekolah/pendidikan ini antara lain faktor ekonomi (penghasilan, pendidikan kepala rumah tangga) serta akses ke fasilitas pendidikan (daerah tempat tinggal) (Hakim, 2020). Untuk pendidikan tinggi, kurangnya motivasi mahasiswa dan hasil akademik/performa mahasiswa juga mempengaruhi tingkat *dropout*. '

Dengan data yang lengkap, angka *dropout* dapat diprediksi menggunakan model *Machine Learning* (Hidayat et al, 2013). Hal ini akan memberikan gambaran kepada pihak penyelenggara pendidikan untuk dapat melakukan langkah-langkah pencegahan dropout yang tepat.

## **2. Business Understanding**

Jaya Jaya Institut merupakan salah satu institusi pendidikan perguruan yang telah berdiri sejak tahun 2000 dan telah mencetak banyak lulusan dengan reputasi yang sangat baik. Akan tetapi, banyak siswa yang tidak menyelesaikan pendidikannya (*drop out*). Jaya Jaya Institut mau memperoleh gambaran mengenai siswa yang berpotensi untuk *drop out* sehingga dapat dilakukan pendekatan khusus agar mereka menyelesaikan pendidikannya.

### *Permasalahan Bisnis*

Mari kita mengevaluasi beberapa faktor yang mungkin menyebabkan *dropout* tersebut.
1. Bagaimana demografi siswa (status pernikahan, usia, gender), serta kehadiran di kelas pagi/sore mempengaruhi *dropout*?
2. Bagaimana hubungan antara tingkat pendidikan orangtua dan pekerjaan orangtua terhadap *dropout*?
3. Apa hubungan antara tingkat pendidikan siswa dan nilai sebelumnya terhadap hasil siswa (*dropout* atau lulus)?
4. Bagaimana perbandingan *trend curricular units* semester 1 dan semester 2 yang dikreditkan, didaftarkan, dievaluasi dan disetujui oleh siswa?
5. Bagaimana tingkat *dropout* berdasarkan *course* yang diambil siswa?
6. Apa pengaruh beasiswa terhadap siswa *dropout*?

### *Cakupan Proyek:*
Melakukan analisa data untuk menentukan faktor-faktor yang menyebabkan tingginya *dropout* sehingga dapat dilakukan tindakan/program pendekatan untuk mencegah siswa *dropout*: 
- Analisa data termasuk menyiapkan *dashboard* untuk visualisasi data siswa sehingga dapat terlihat faktor-faktor yang menyebabkan siswa *dropout*. 
- Mencari korelasi antar data, seperti data demografi siswa, tingkat pendidikan dan pekerjaan orangtua, tingkat pendidikan siswa dan nilai siswa sebelumnya dengan tingkat *dropout* dengan metode EDA (Exploratory Data Analysis). Melalui EDA, kita akan mengevaluasi tingkat *dropout* berdasarkan *course* dan pengaruh beasiswa terhadap siswa *dropout*
- Output akhir dari proyek ini adalah membangun prototype sistem prediksi sederhana untuk memprediksi status siswa berdasarkan beberapa faktor. 
- Berdasarkan hasil analisa, beberapa rekomendasi tindakan/program dapat dilakukan agar tingkat *dropout* siswa bisa menurun. 

## **3. Persiapan**
### Sumber data
File CSV: raw.githubusercontent.com/dicodingacademy/dicoding_dataset/main/students_performance/data.csv

### Langkah-langkah persiapan
1. Memastikan instalasi python di atas 3.7
2. Pembuatan virtual environment: untuk mengisolasi dependensi proyek ini dari proyek Python lainnya pada sistem. 
3. Menyiapkan library yang dibutuhkan: 
    - numpy==1.24.3
    - pandas==1.5.3
    - matplotlib==3.8.0
    - seaborn==0.13.2
    - scikit-learn==1.1.3
    - joblib==1.2.0
4. PostgreSQL sebagai DBMS dari database yang akan digunakan yang dijalankan melalui Supabase. Supabase dihubungkan dengan akun GitHub. Setelah itu kita dapat melakukan Project Setting dan menuju halaman Database untuk mendapatkan informasi untuk menyambungkan Postgres database dengan metabase ataupun sqlalchemy.
5. Mengirim dataset yang sebelumnya telah kita unduh ke dalam database menggunakan library sqlalchemy dengan menggunakan DATABASE_URL dari supabase. 
6. Menghubungkan metabase dengan supabase dengan cara menginput informasi ke setting Metabase dengan informasi dari Dashboard Setting yang ada pada supabase. Parameter yang digunakan adalah dari *transaction pooler*. 
7. Menyesuaikan data scheme dengan cara setting Data Model dan menyesuaikan tipe kolom. 
8. Membuat model pada metabase dengan menjalankan perintah Query. Periksa kembali tipe data dari setiap kolom dengan cara mengklik bagian Metadata dari hasil Query. 
9. Membuat visualisasi untuk metrik yang akan digunakan untuk menjawab pertanyaan-pertanyaan dalam permasalahan bisnis. Sesuaikan tipe visualisasi yang digunakan. 
10. Membuat bisnis dashboard dari visualisasi yang sudah kita buat dan simpan sebelumnya. 

## **4. Business Dashboard**

- Link: http://localhost:3000/public/dashboard/7d5a86f7-afff-470b-b9a0-d292b4cffe34
- Email: root@mail.com
- Password: root123

### **Insight**

1. Demografi siswa:
  
  ![demografi siswa](/Suyanti%20Witono%20tFDe-Dashboard/Suyanti%20Witono%20tFDe-Dashboard1.png)
  ![demografi siswa dropout](/Suyanti%20Witono%20tFDe-Dashboard/Suyanti%20Witono%20tFDe-Dashboard2.png)
  - Total siswa: 4424, jumlah siswa *dropout*: 1421. Maka tingkat *dropout*: (1421/4424) x 100% = 32.12%.
  - Kategori usia siswa terbesar pada rentang 17-22.5 tahun (68.87%), kedua terbesar pada rentang 22.5-30 tahun (15.05%). Data siswa *dropout* terbesar pada rentang 17-22.5 tahun (48.77%), kedua terbesar pada rentang 22.5-30 tahun (24.14%). Karena data siswa terbanyak pada rentang usia tersebut, maka data siswa *dropout* juga proporsional. Jika dilihat pada rentang 22.5-30 tahun terjadi lebih banyak siswa *dropout* kemungkinan karena faktor keluarga dan ekonomi.
  -  Jumlah siswa perempuan (64.8%) lebih tinggi dari siswa laki-laki (35.2%). Pada data siswa *dropout*, hampir sama antara siswa perempuan dan siswa laki-laki. Dapat disimpulkan bahwa siswa laki-laki beresiko lebih tinggi untuk *dropout*.
  - Jumlah siswa yang belum menikah mencapai 88.58%. Tren yang sama terlihat pada jumlah siswa yang *dropout* dimana yang belum menikah 83.32%.
  - 89.1% siswa mengambil kelas pagi. Karena data yang besar ini maka pada data siswa *dropout* juga siswa kelas pagi mencapai 85.4%.

2. *Course*:
![Course](/Suyanti%20Witono%20tFDe-Dashboard/Suyanti%20Witono%20tFDe-Dashboard3.png)
  - *Course* yang paling banyak diambil siswa adalah *nursing* (17.31%), kemudian diikuti dengan *management, social service, veterinary nursing, journalism & communication, advertising & marketing management*, kelas sore *management, tourism, communication design, animation & multimedia design*, kelas sore *social service, agronomy, basic education, informatics engineering, equinculture*, dan lain-lain.
  - Pada data siswa *dropout*, kebanyakan berasal dari *course management* (kelas sore 9.57% dan kelas pagi 9.43%). Urutan terbesar selanjutnya adalah *course nursing, journalism & communication*, dan *tourism*. Hal ini menunjukkan bahwa angka *dropout* terbesar pada kelas *management*, terutama kelas sore *management* dimana 136 siswa dari total 268 siswa yang terdaftar.

3. Tingkat pendidikan dan pekerjaan orangtua
![parent](/Suyanti%20Witono%20tFDe-Dashboard/Suyanti%20Witono%20tFDe-Dashboard4.png)
  - Data siswa *dropout* berdasarkan tingkat pendidikan hampir sama pada tingkat pendidikan ayah dan ibu. Kategori paling besar adalah dari tingkat pendidikan *Basic education 1st cycle (4th/5th year) or equiv.*. Kategori selanjutnya adalah *Secondary Education (12th), basic education 3rd cycle (9th/10th/11th year) or equiv, basic education 2nd cycle (6th/7th/8th year) or equiv.*. Hal ini menunjukkan latar belakang pendidikan orangtua yang hanya sampai pendidikan dasar (di bawah 12 tahun) sangat menentukan dan mempengaruhi tingkat *dropout* siswa.
  - Data siswa *dropout* berdasarkan pekerjaan juga hampir sama pada ayah dan ibu. Kategori paling besar adalah pekerja non ahli (22.73% ayah, 34.48% ibu). Hal ini menunjukkan bahwa tingkat kesadaran siswa untuk melanjutkan pendidikan sangat dipengaruhi oleh latar belakang pekerjaan orangtua. Ada kemungkinan bahwa siswa *dropout* karena tingkat sosial ekonomi orangtua dan ketidak mampuan secara ekonomi untuk melanjutkan pendidikan.

4. Tingkat pendidikan siswa dan nilai pada pendidikan yang lalu
![previous qualification](/Suyanti%20Witono%20tFDe-Dashboard/Suyanti%20Witono%20tFDe-Dashboard5.png)
  - Lebih dari 3/4 siswa *dropout* (75.86%) berasal dari kelompok dengan latar pendidikan SMA atau sederajat.
  - Untuk profil siswa *dropout*, meningkat pada siswa dengan nilai 90, tertinggi pada nilai 130 pada tingkat pendidikan yang lalu, kemudian menurun sampai pada nilai 190.

5. Nilai Semester 1 dan Semester 2
![1st and 2nd Sem](/Suyanti%20Witono%20tFDe-Dashboard/Suyanti%20Witono%20tFDe-Dashboard6.png)
  - Siswa *dropout* memiliki rata-rata *curricular units approved* pada semester 1 adalah 3.59 dan 2.74 pada semester 2.
  - Siswa *dropout* tertinggi pada nilai rata-rata semester 1 di bawah 7 dan 11. Pada data nilai semester 2, jumlah siswa *dropout* tertinggi pada nilai di bawah 10.

6. Beasiswa
![Scholarship](/Suyanti%20Witono%20tFDe-Dashboard/Suyanti%20Witono%20tFDe-Dashboard7.png)
  - Jumlah penerima beasiswa adalah 1099 siswa dari 4244 total siswa (24.8%).
  - Dari seluruh penerima beasiswa tersebut, ada 134 siswa yang *dropout*.
  - Persentase siswa penerima beasiswa yang *dropout* adalah (134/1099)x100% = 12.19%. Persentase ini sebenarnya cukup rendah, menunjukkan bahwa beasiswa membantu siswa untuk terus dapat melanjutkan pendidikannya. Akan tetapi, perlu dilakukan telaah lebih lanjut dengan mewawancarai siswa yang menerima beasiswa namun *dropout* untuk mengetahui alasan melakukan *dropout*.

## **5. Menjalankan Sistem Machine Learning**
Streamlit model prediksi: 
https://jaya-jaya-qrbm6i9w9xnujdgphdp6uy.streamlit.app/#students-dropout-prediction-prototype 

Pada sistem prediksi (prototype), terdapat beberapa kolom yang perlu diisi/dipilih. 
1. Age_at_enrollment: diisikan dengan usia siswa saat masuk di Jaya Jaya Institut. Cara mengisi dapat dengan mengklik tanda '+' atau '-' untuk memilih angka yang sesuai atau dapat dengan menuliskan angka lalu menekan tombol enter. 
2. Gender: jenis kelamin - ada 2 pilihan: 0 - perempuan, 1 - laki-laki.
3. Marital_status: status pernikahan dipilih dari pilihan yang ada (Single, Married, Widower, Divorced, Facto Union, atau Legally Separated).
4. Course: Jurusan yang diambil siswa: 33-Biofuel Production Technologies, 171-Animation and Multimedia Design, 8014-Social Service (evening attendance), 9003-Agronomy, 9070-Communication Design, 9085-Veterinary Nursing, 9119-Informatics Engineering, 9130-Equinculture, 9147-Management, 9238-Social Service, 9254-Tourism, 9500-Nursing, 9556-Oral Hygiene, 9670-Advertising and Marketing Management, 9773-Journalism and Communication, 9853-Basic Education, 9991-Management (evening attendance).
5. Daytime_evening_attendance: apakah siswa mengambil kelas pagi atau sore: 0 - sore, 1 - pagi. 
6. Scholarship_holder: apakah siswa mendapatkan beasiswa? 0 - tidak, 1 - ya. 
7. Fathers_qualification: tingkat pendidikan terakhir ayah. Diisikan berdasarkan pilihan, yakni 1-Secondary Education - 12th Year of Schooling or Eq., 2-Higher Education-Bachelor's Degree, 3-Higher Education-Degree, 4-Higher Education-Master's, 5-Higher Education-Doctorate, 6-Frequency of Higher Education, 9-12th Year of Schooling-Not Completed, 10-11th Year of Schooling-Not Completed, 11-7th Year (Old), 12-Other-11th Year of Schooling, 14-10th Year of Schooling, 18-General commerce course, 19-Basic Education 3rd Cycle (9th/10th/11th Year) or Equiv., 22-Technical-professional course, 26-7th year of schooling, 27-2nd cycle of the general high school course, 29-9th Year of Schooling-Not Completed, 30-8th year of schooling, 34-Unknown, 35-Can't read or write, 36-Can read without having a 4th year of schooling, 37-Basic education 1st cycle (4th/5th year) or equiv., 38-Basic Education 2nd Cycle (6th/7th/8th Year) or Equiv., 39-Technological specialization course, 40-Higher education-degree (1st cycle), 41-Specialized higher studies course, 42-Professional higher technical course, 43-Higher Education-Master (2nd cycle), 44-Higher Education-Doctorate (3rd cycle).
8. Mothers_qualification: tingkat pendidikan terakhir ibu. Diisikan berdasarkan pilihan, yakni 1-Secondary Education - 12th Year of Schooling or Eq., 2-Higher Education-Bachelor's Degree, 3-Higher Education-Degree, 4-Higher Education-Master's, 5-Higher Education-Doctorate, 6-Frequency of Higher Education, 9-12th Year of Schooling-Not Completed, 10-11th Year of Schooling-Not Completed, 11-7th Year (Old), 12-Other-11th Year of Schooling, 14-10th Year of Schooling, 18-General commerce course, 19-Basic Education 3rd Cycle (9th/10th/11th Year) or Equiv., 22-Technical-professional course, 26-7th year of schooling, 27-2nd cycle of the general high school course, 29-9th Year of Schooling-Not Completed, 30-8th year of schooling, 34-Unknown, 35-Can't read or write, 36-Can read without having a 4th year of schooling, 37-Basic education 1st cycle (4th/5th year) or equiv., 38-Basic Education 2nd Cycle (6th/7th/8th Year) or Equiv., 39-Technological specialization course, 40-Higher education-degree (1st cycle), 41-Specialized higher studies course, 42-Professional higher technical course, 43-Higher Education-Master (2nd cycle), 44-Higher Education-Doctorate (3rd cycle).
9. Fathers_occupation: pekerjaan ayah, diisikan berdasarkan pilihan, yakni 0-Siswa, 1-Perwakilan dari badan legislatif dan/atau eksekutif, direktur, dan manajer eksekutif, 2-Spesialis dalam kegiatan Intelektual dan Saintifik, 3-Teknisi dan Profesi Level Menengah, 4-Staf Admin, 5-Personal Services, Security and Safety Workers and Penjual, 6-Petani dan Pekerja Ahli di bidang agrikultur, perikanan and perhutanan, 7-Pekerja Ahli di industri, konstruksi, pengrajin, 8-Pekerja dan operator instalasi dan mesin, 9-Pekerja (non ahli), 10-Tentara, 90-Situasi lain, 99-(kosong/tidak ada keterangan), 122-tenaga medis/kesehatan, 123-guru, 125-Spesialis dalam Information and communication technologies (ICT), 131-Teknisi dan Staf Ahli Level menengah dalam science and engineering, 132-Teknisi atau Staf Ahli level menengah dalam bidang kesehatan, 134-Teknisi atau Staf Ahli level menengah dalam hukum, sosial, olahraga, kebudayaan dan sejenisnya, 141-Pekerja kantor, sekretaris, dan operator data, 143-Operator dalam bidang accounting, statistical, financial services, 144-Staf admin pendukung, 151-Pekerja jasa personal, 152-pedagang, 153-Personal care workers, 171-Staf Ahli konstruksi dan sejenisnya, kecuali electricians, 173-pelukis, penghasil instrumen presisi, pembuat perhiasan, artisans dan sejenisnya, 175-Pekerja dalam pembuatan makanan, pembuat kayu, pakaian, dan industri lainnya, 191-petugas kebersihan, 192-Tenaga kerja kasar dalam pertanian, perikanan, peternakan, dan kehutanan, 193-Tenaga kerja kasar dalam pertambangan, produksi, dan transportasi, 194-Asisten juru masak. 
10. Mothers_occupation: pekerjaan ibu, diisikan berdasarkan pilihan, yakni 0-Siswa, 1-Perwakilan dari badan legislatif dan/atau eksekutif, direktur, dan manajer eksekutif, 2-Spesialis dalam kegiatan Intelektual dan Saintifik, 3-Teknisi dan Profesi Level Menengah, 4-Staf Admin, 5-Personal Services, Security and Safety Workers and Penjual, 6-Petani dan Pekerja Ahli di bidang agrikultur, perikanan and perhutanan, 7-Pekerja Ahli di industri, konstruksi, pengrajin, 8-Pekerja dan operator instalasi dan mesin, 9-Pekerja (non ahli), 10-Tentara, 90-Situasi lain, 99-(kosong/tidak ada keterangan), 122-tenaga medis/kesehatan, 123-guru, 125-Spesialis dalam Information and communication technologies (ICT), 131-Teknisi dan Staf Ahli Level menengah dalam science and engineering, 132-Teknisi atau Staf Ahli level menengah dalam bidang kesehatan, 134-Teknisi atau Staf Ahli level menengah dalam hukum, sosial, olahraga, kebudayaan dan sejenisnya, 141-Pekerja kantor, sekretaris, dan operator data, 143-Operator dalam bidang accounting, statistical, financial services, 144-Staf admin pendukung, 151-Pekerja jasa personal, 152-pedagang, 153-Personal care workers, 171-Staf Ahli konstruksi dan sejenisnya, kecuali electricians, 173-pelukis, penghasil instrumen presisi, pembuat perhiasan, artisans dan sejenisnya, 175-Pekerja dalam pembuatan makanan, pembuat kayu, pakaian, dan industri lainnya, 191-petugas kebersihan, 192-Tenaga kerja kasar dalam pertanian, perikanan, peternakan, dan kehutanan, 193-Tenaga kerja kasar dalam pertambangan, produksi, dan transportasi, 194-Asisten juru masak. 
11. Previous_qualifications: tingkat pendidikan siswa sebelumnya, diisikan berdasarkan pilihan yakni 1-SMA atau setingkat, 2-S1, 3-diploma, 4-S2, 5-S3, 6-setara pendidikan tinggi, 9-tidak menyelesaikan 12 tahun sekolah, 10-tidak menyelesaikan 11 tahun sekolah, 12-Lain-lain-11 tahun sekolah, 14-10 tahun sekolah, 15-tidak menyelesaikan 10 tahun sekolah, 19-Basic education 3rd cycle (9th/10th/11th year) atau setara, 38-Basic education 2nd cycle (6th/7th/8th year) atau setara, 39-spesialis teknologi (SMK), 40-Higher education - degree (1st cycle), 42-Professional higher technical course, 43-Higher education - master (2nd cycle). 
12. Previous_qualifications_grade: nilai siswa pada tingkat pendidikan sebelumnya. Diisikan dengan angka antara 0-200. 
13. Curricular_units_1st_sem_approved: jumlah unit kurikulum semester 1 yang disetujui. Diisikan dengan angka. 
14. Curricular_units_2nd_sem_approved: jumlah unit kurikulum semester 2 yang disetujui. Diisikan dengan angka.
15. Curricular_units_1st_sem_grade: nilai siswa pada semester 1. Diisikan dengan angka antara 0-20. 
16. Curricular_units_2nd_sem_grade: nilai siswa pada semester 2. Diisikan dengan angka antara 0-20. 

Setelah semua kolom diisikan, klik tombol 'predict'. 

Ada 3 kemungkinan hasil: 
Status: 0 - enrolled, 1 - graduate, 2 - dropout


## **6. Kesimpulan**
1. Demografi siswa mempengaruhi tingkat *dropout*.
  - tingkat *dropout* tertinggi pada rentang usia 17-30 tahun.
  - tingkat *dropout* hampir sama antara laki-laki dan perempuan. Akan tetapi jumlah siswa perempuan jauh lebih banyak sehingga dapat disimpulkan bahwa laki-laki lebih beresiko *droput*.
  - tingkat *dropout* tertinggi pada siswa yang belum menikah karena memang sebagian besar demografi siswa adalah belum menikah.
  - tingkat *dropout* sesuai kelas pagi/sore berbanding lurus dengan jumlah siswa pada kelas pagi/sore.

2. Tingkat *dropout* berdasarkan *course*.
  - Jumlah *course* yang paling banyak diambil oleh siswa adalah *nursing*.
  - Tingkat *dropout* ada pada *course management* baik pada kelas pagi maupun sore.
  - Kelas sore *management* memiliki tingkat *dropout* sebesar: (136/268)x100% = 50.75%.

3. Tingkat pendidikan dan pekerjaan orangtua mempengaruhi *dropout*.
  - Rata-rata siswa yang *dropout*, data pendidikan orangtua adalah di tingkat *basic education* yakni lulusan SD, SMP, atau SMA.
  - Pekerjaan orangtua juga mempengaruhi tingkat *dropout*, didapatkan pada data bahwa kebanyakan siswa *dropout* memiliki orangtua dengan latar belakang pekerja non-ahli.
  - Rendahnya tingkat pendidikan orangtua dan pekerjaan orangtua membuat permasalahan sosial ekonomi sehingga siswa kesulitan melanjutkan ke tingkat pendidikan yang lebih tinggi.

4. Profil siswa *dropout* berdasarkan nilai dan tingkat pendidikan yang lalu
  - Kebanyakan siswa *dropout* memiliki latar belakang pendidikan dari SMA atau setingkat.
  - Tingkat *dropout* meningkat dari nilai siswa 90-130, kemudian menurun kembali sampai nilai 190.

5. Profil siswa *dropout* berdasarkan nilai di semester satu dan dua
  - Pada semester 1 dan semester 2, kebanyakan siswa *dropout* pada nilai di bawah 12.5

6. Pengaruh beasiswa dengan tingkat *dropout*
  - Persentase siswa penerima beasiswa yang *dropout* adalah (134/1099)x100% = 12.19%. Persentase ini sebenarnya cukup rendah, menunjukkan bahwa beasiswa membantu siswa untuk terus dapat melanjutkan pendidikannya. Akan tetapi, perlu dilakukan telaah lebih lanjut dengan mewawancarai siswa yang menerima beasiswa namun *dropout* untuk mengetahui alasan melakukan *dropout*.

## **7. Rekomendasi Action Items**
**1. Academic Support**
  - Program intervensi dini: Mengidentifikasi siswa yang beresiko *dropout* sedini mungkin (misal: berdasarkan usia dan/atau nilai pada semester lalu) serta membuat program seperti *tutoring, mentoring, and counseling*.
  - Meningkatkan performa akademik: membuat program seperti *workshops* atau menyediakan *resources* untuk meningkatkan cara belajar, manajemen waktu, atau strategi menghadapi ujian.
  - *Flexible Curriculum*: Menyediakan program yang lebih fleksibel seperti kelas online, akselerasi, dan lain sebagainya. Selain itu, dapat juga dibangun sistem belajar personal yang sesuai dengan kebutuhan masing-masing siswa sehingga mereka dapat belajar sesuai kecepatan mereka masing-masing.
  - Dukungan bagi siswa bermasalah: Mengimplementasikan program dukungan bagi siswa yang sering absen atau yang memiliki nilai yang rendah.

**2. Financial Support**
  - Bantuan finansial: menyediakan informasi dan bantuan untuk siswa dapat mendapatkan beasiswa atau bantuan keuangan lainnya.
  - Mengetahui halangan finansial: menawarkan program bantuan keuangan untuk siswa yang mengalami masalah finansial sementara.
  - Program belajar sambil bekerja: menciptakan peluang melalui program siswa bekerja melalui kerjasama dengan dunia usaha sehingga siswa dapat memperoleh pengalaman sambil mendapatkan uang untuk biaya kuliah/hidup lainnya.

**3. Social and Emotional Support**
  - Meningkatkan rasa kepemilikan: membangun dan memelihara suasana belajar yang kondusif dan suportif dimana siswa merasa dihargai dan didukung.
  - *Peer mentoring*: melibatkan siswa untuk membentuk grup belajar.
  - *Counseling service*: memberikan layanan konseling bagi siswa untuk memenuhi kebutuhan personal, sosial dan emosional siswa.

**4. Institutional Actions**
  - Meningkatkan *data tracking*: mengimplementasikan sistem untuk melacak progres siswa serta memprediksi *dropout* siswa.
  - *Regular Check-In*: melakukan pendekatan secara rutin kepada siswa beresiko.
  - *Exit Interview*: melakukan tanya jawab dengan siswa yang memutuskan *dropout* untuk menggali alasan serta mendapatkan data.

## **Referensi (APA Style)**
1. Dealls (2025). Drop Out: Arti, Faktor Penyebab & Dampaknya! | Dealls. [online] Dealls. Available at: https://dealls.com/pengembangan-karir/drop-out-artinya.
2. Hakim, A. (2020). FAKTOR PENYEBAB ANAK PUTUS SEKOLAH. Jurnal Pendidikan, 21(2), pp.122–132. doi:https://doi.org/10.33830/jp.v21i2.907.2020.
3. Hidayat, M. Mahaputra & Purwitasari, Diana & Ginardi, R.V.Hari. (2013). ANALISIS PREDIKSI DROP OUT BERDASARKAN PERILAKU SOSIAL MAHASISWA DALAM EDUCATIONAL DATA MINING MENGGUNAKAN JARINGAN SYARAF TIRUAN. IPTEK ITATS.