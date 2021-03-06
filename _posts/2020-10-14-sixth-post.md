--- 
layout: post
title: Breast Histopathology
author: Achmad Ridho
description: 
intro_image: /img/machine-learning-definition.jpeg
intro_image_ratio: is-16by9
---

Pada kesempatan kali ini, saya akan menjelaskan hasil pengujian saya terhadap gambar dataset Brest Histopathology Image merupakan dataset `CNN` yang telah saya lakukan 1 minggu belakangan ini.
Untuk dataset sendiri dapat dilihat pada [Dataset Breast Histopatology](https://www.kaggle.com/paultimothymooney/breast-histopathology-images/).

**Intro**

Kanker payudara merupakan salah satu penyakit ketika kondisi sel kanker terbentuk dijaringan payudara baik pria maupun wanita dan dapat mematikan. Invasive Ductal Carcinoma (IDC) merupakan bahasa kanker payudara pada bidang kesehatan, merupakan kanker yang sangat agresive dan menyerang tidak mengenal usia maupun kelamin tertentu.

**Content**

Pada pengujian kali ini, dataset memiliki gambar sejumlah 277,524 dengan ukuran 50 x 50 serta gambar tersebut merupakan gambar 279 pasien. dari jumlah gambar tersebut dapat dibagi menjadi 198,738 non-IDC (Negative) dan 78,786 IDC (Positif). Setiap penulisan nama dapat dilihat dari akhir nama yaitu Class_0 atau Class_1 yang berarti Class_0 merupakan non-IDC (Negatif) dan Class_1 merupakan IDC (Positif). 

**Result Report**
```yaml 
1. Jumlah data

Jumlah data yang saya gunakan dapat dilihat dari fungsi dibawah ini.
```
[![2bwT8X.md.png](https://iili.io/2bwT8X.md.png)](https://freeimage.host/i/2bwT8X)

```yaml 
2. Sample gambar (non-IDC)

Dibawah ini merupakan beberapa sample gambar pasien non-IDC.
```
`Gambar Normal`

[![2bwRus.png](https://iili.io/2bwRus.png)](https://freeimage.host/)

`Gambar RGB`

[![2b4Z9R.png](https://iili.io/2b4Z9R.png)](https://freeimage.host/)

`Gambar Grey`

[![2b4btI.png](https://iili.io/2b4btI.png)](https://freeimage.host/)

`Gambar Random non-IDC`

[![2b4pnt.md.png](https://iili.io/2b4pnt.md.png)](https://freeimage.host/i/2b4pnt)

```yaml 
3. Sample gambar (IDC)

Dibawah ini merupakan beberapa sample gambar pasien IDC.
```
`Gambar Normal`

[![2b69Pn.png](https://iili.io/2b69Pn.png)](https://freeimage.host/)

`Gambar RGB`

[![2b6JFs.png](https://iili.io/2b6JFs.png)](https://freeimage.host/)

`Gambar Grey`

[![2b62Sf.png](https://iili.io/2b62Sf.png)](https://freeimage.host/)

`Gambar Random IDC`

[![2b6F94.md.png](https://iili.io/2b6F94.md.png)](https://freeimage.host/i/2b6F94)

```yaml 
4. Model Algoritma
Setelah saya melakukan beberapa spliting data (Class_0 dan Class_1) kemudian saya melakukan penentuan sample data yang diuji dengan code OpenCV lalu saya menentukan model terbaik untuk dijadikan algoritma dalam pengujian.
Berikut ini model algoritma yang saya gunakan.
```
`Model Algoritma`

[![2b6KAl.png](https://iili.io/2b6KAl.png)](https://freeimage.host/)

```yaml 
Dari algoritma diatas saya melakukan pengujian dengan 30 epochs dan dari 30 epoch tersebut saya mendapatkan akurasi tertinggi yaitu 0.8603 pada epoch ke-20.
Berikut gambar epoch ke-20 tersebut
```
`Epoch ke-20`

[![2b6fN2.md.png](https://iili.io/2b6fN2.md.png)](https://freeimage.host/i/2b6fN2)

```yaml 
5. Validasi Model
Pengujian masih berlanjut, belum sampai disitu saya kemudian melakukan akurasi terhadap model algoritma yang saya gunakan apakah sudah masuk akal untuk digunakan atau belum dengan mengunakan beberapa pengujian.
Berikut beberapa gambar dari pengujian model tersebut.
```
`Confusion Matrix`

[![2b6qtS.png](https://iili.io/2b6qtS.png)](https://freeimage.host/)

```yaml 
Setelah dilihat dari hasil confusion matrix diatas, dapat dilihat bahwa model cukup masuk akal untuk digunakan lalu kemudian saya memunculkan plot gambar akurasi dan plot gambar loss agar dapat terlihat jelas apakah grafik overfit atau tidak.
```
`Accuracy Plot`

[![2b6oPe.png](https://iili.io/2b6oPe.png)](https://freeimage.host/)

`Loss Plot`

[![2b6zKu.png](https://iili.io/2b6zKu.png)](https://freeimage.host/)

```yaml 
Setelah melihat plot diatas dan cukup puas, saya juga melakukan visualisasi gambar dengan Activation Map, yang dapat dilihat pada gambar berikut.
```

`Activation Map 1`

[![2b6Icb.png](https://iili.io/2b6Icb.png)](https://freeimage.host/)

`Activation Map 2`

[![2b6AHx.md.png](https://iili.io/2b6AHx.md.png)](https://freeimage.host/i/2b6AHx)

```yaml 
Setelah semua sesuai dengan kebutuhan analisa, maka saya terakhir memunculkan tensorboard dengan tujuan agar lebih dapat men-track jumlah penurunan grafik dah melakukan smooting pada grafik accuracy dan loss yang saya dapatkan, pada gambar berikut.
```
`Tensorboard`

[![2b6RAQ.png](https://iili.io/2b6RAQ.png)](https://freeimage.host/)
```yaml 
6. Kesimpulan
Dari hasil pengujian diatas yang saya munculkan, saya cukup puas dengan hasil tersebut dan hasil yang saya dapatkan juga cukup bagus yaitu diangka 0.8603 (val_accuracy) dan 0.3338 (val_loss) sehingga angka tersebut dapat dijadikan acuan terhadap prediksi gambar sejenis (Breast Histopathology Images).
```
