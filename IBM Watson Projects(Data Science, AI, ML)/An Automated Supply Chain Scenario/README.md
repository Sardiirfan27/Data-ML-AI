# An Automated Supply Chain Scenario
Aktivitas rantai pasokan mencakup mengubah sumber daya alam (dan lainnya), bahan mentah, dan komponen menjadi produk jadi yang kemudian dikirim ke pelanggan akhir saat pelanggan membutuhkan atau menginginkannya. Jadi, tidak hanya mengurus inventaris dan pengiriman produk. Rantai pasokan jauh lebih terlibat dan kompleks.

Dalam project ini kami akan berfokus pada analisis seberapa efektif rantai pasokan/supply chain untuk department store ritel. Skenario rantai pasokan otomatis ini akan memberikan wawasan ke dalam data dan proses dari organisasi rantai pasokan, dalam upaya untuk mengisolasi penyebab kinerja pengiriman yang buruk.

## Permasalah
Aktivitas rantai pasokan yang berkaitan dengan tahap bahan baku dikenal sebagai aktivitas hulu (upstream activities) dan aktivitas antara produsen dan konsumen akhir adalah aktivitas hilir (downstream activities). Biasanya, rantai pasokan terdiri dari banyak organisasi yang mengoordinasikan aktivitas dengan tujuan memisahkan diri dari persaingan.
Dalam dunia bisnis saat ini, tidak ada kebutuhan yang terlewat dalam upaya untuk menjadi pelarut dan lebih baik lagi, menjadi dan tetap menguntungkan. Perusahaan yang cerdas menyadari bahwa manajemen rantai pasokan yang efektif adalah bagian penting dari model bisnis mereka.

Untuk kasus dalam project ini, anggaplah ada organisasi bernama Folly Surf yang berlokasi di Carolina Selatan di AS, yang mendistribusikan papan selancar. Grup rantai pasokan mereka bertanggung jawab atas pengadaan komponen dasar produk (berbagai jenis papan selancar) serta perakitan (yang mencakup proses yang dikenal sebagai pembentukan), dan akhirnya pengiriman ke pelanggan, yang dalam hal ini bermacam-macam toko selancar independen yang telah memesan papan selancar.
Bertahun-tahun sejak didirikan, lahir di garasi beberapa peselancar, produk perusahaan semakin populer, didorong oleh reputasi peselancar dan tingkat kepuasan yang tinggi (papan bekerja seperti yang diiklankan). Hal ini telah meningkatkan permintaan di luar kemampuan perusahaan untuk menyediakan produk dan tidak hanya mengancam profitabilitas jangka pendek tetapi juga rencana masa depan perusahaan untuk memperluas lokasi tokonya.
Misalnya, ketika pengiriman semuanya tepat waktu, kualitas produk secara keseluruhan menurun, yang mengakibatkan konsumen dan pengembalian yang tidak bahagia. Ketika dipastikan bahwa tingkat kualitas terpenuhi atau terlampaui, pengiriman terlambat, sekali lagi mengakibatkan pelanggan tidak senang dan penjualan hilang. Akhirnya, ketika tim perakitan diperluas, memastikan kualitas serta kemampuan untuk mengirimkan tepat waktu, tim perakitan akan kehabisan bahan dan suku cadang.
Sebelum segala sesuatunya menjadi terlalu jauh di luar kendali atau di luar situasi yang dapat diperbaiki, grup Folly Surf tertarik untuk melihat wawasan apa yang dapat diidentifikasi dengan data mereka dan Watson Analytics. 

## IBM Watson Analytics
IBM Watson merupakan salah satu bagian dari cloud (IBM Cloud). Lingkungan cloud membuatnya relatif mudah untuk memulai karena sebenarnya ada sangat sedikit prasyarat yang Anda perlukan untuk mengakses IBM Watson Analytics (dan platform IBM Cloud secara keseluruhan).

IBM Watson Analytics menghadirkan analisis dan visualisasi data cerdas, penemuan data terpandu, analitik prediktif otomatis , dan kemampuan kognitif kepada Anda sebagai layanan.

Beberapa penerapan Kemampuan platform IBM Watson Analytics di bidang bisnis seperti mempercepat analitik prediktif untuk wawasan bisnis yang lebih baik, membangun interaksi yang disesuaikan untuk pengalaman pelanggan yang lebih baik, mengidentifikasi tren, menyelidiki potensi masalah, dan sebagainya

## Detecting Parkinson’s Disease with XGBoost – Objective
To build a model to accurately detect the presence of Parkinson’s disease in an individual. you can see the process at [Parkinson’s disease](https://github.com/Sardiirfan27/Data-ML-AI/blob/main/Detecting%20Parkinson%E2%80%99s%20Disease/Detecting_Parkinson's_Disease_with_XGBoost.ipynb)

## Dataset and Library
In this Python machine learning project, using the Python libraries scikit-learn, numpy, pandas, and xgboost, we will build a model using an XGBClassifier. We’ll load the data, get the features and labels, scale the features, then split the dataset, build an XGBClassifier, and then calculate the accuracy of our model.

We'll use the data from UC Irvine's amazing dataset repository, specifically the [Parkinsons ML database](https://archive.ics.uci.edu/ml/machine-learning-databases/parkinsons/).

There are two datasets within this. The first is in the root folder (`parkinsons.data` which is included here too) and can be used to detect Parkinsons. The second is within the `telemonitoring/` directory and contains UDPR scores for us to predict.

## Approach

Parkinsons detection islikely best done with an XGBoost since outputs are 0 or 1 and it seems mostly linear.

The UDPR is very hard to fine tune with XGBoost. With an NN in Keras, we can fit much better. There are still some very bad apples in our data/predictions bur the performance is overall/on average much better.
You can find more info on the datasets in UCI's database. ([info for Parkinsons detection](https://archive.ics.uci.edu/ml/machine-learning-databases/parkinsons/parkinsons.names)) ([info for UDPR](https://archive.ics.uci.edu/ml/machine-learning-databases/parkinsons/telemonitoring/parkinsons_updrs.names))

## Credits

Citations for the datasets used:

```
'Exploiting Nonlinear Recurrence and Fractal Scaling Properties for Voice Disorder Detection', 
Little MA, McSharry PE, Roberts SJ, Costello DAE, Moroz IM. 
BioMedical Engineering OnLine 2007, 6:23 (26 June 2007)
```

```
A Tsanas, MA Little, PE McSharry, LO Ramig (2009)
'Accurate telemonitoring of Parkinson.s disease progression by non-invasive speech tests',
IEEE Transactions on Biomedical Engineering (to appear).
```

## Reference

'Exploiting Nonlinear Recurrence and Fractal Scaling Properties for Voice Disorder Detection', Little MA, McSharry PE, Roberts SJ, Costello DAE, Moroz IM. BioMedical Engineering OnLine 2007, 6:23 (26 June 2007)  
[Display full dataframe](https://stackoverflow.com/questions/11707586/how-do-i-expand-the-output-display-to-see-more-columns-of-a-pandas-dataframe)  
[Move column in dataframe](https://stackoverflow.com/questions/25122099/move-column-by-name-to-front-of-table-in-pandas)  
[Xgboost in Python](https://www.datacamp.com/community/tutorials/xgboost-in-python)  
[detecting-parkinson-disease](https://data-flair.training/blogs/python-machine-learning-project-detecting-parkinson-disease/)
