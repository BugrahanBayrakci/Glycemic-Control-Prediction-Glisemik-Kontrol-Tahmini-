# 🩸 Glycemic Control Prediction (Glisemik Kontrol Tahmini)

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)

## 📌 Proje Hakkında
Bu proje, sağlık verileri üzerinden hastaların **Glisemik Kontrol (Glycemic_control)** durumunu tahmin etmeyi amaçlayan uçtan uca bir makine öğrenmesi ve derin öğrenme çalışmasıdır. Veri bilimi yaşam döngüsünün tüm adımlarının uygulandığı bu projede; veri ön işleme, sınıf dengesizliği (imbalanced data) yönetimi ve farklı algoritmaların performans karşılaştırmaları kapsamlı bir şekilde gerçekleştirilmiştir.

## 🚀 Veri Ön İşleme ve Pipeline (Neler Yapıldı?)
Model başarısını maksimize etmek için aşağıdaki profesyonel adımlar izlenmiştir:
* **Keşifçi Veri Analizi (EDA):** Veri setinin dağılımı incelendi, eksik değerler kontrol edildi ve Heatmap ile değişkenler arası korelasyon analizleri yapıldı.
* **Aykırı Değer (Outlier) Temizliği:** Veri setindeki gürültüyü azaltmak için Z-Skoru (Z-Score) yöntemi kullanılarak aykırı değerler tespit edildi ve filtrelendi.
* **Veri Ölçeklendirme:** Algoritmaların daha stabil ve hızlı çalışması için özellikler `StandardScaler` ile ölçeklendirildi.
* **Dengesiz Veri Yönetimi:** Sağlık verilerinde sıkça görülen sınıf dengesizliği problemini çözmek için `SMOTETomek` tekniği (SMOTE ve Tomek Links kombinasyonu) uygulandı.
* **Özellik Seçimi ve Boyut İndirgeme (Dimensionality Reduction):** Model karmaşıklığını optimize etmek adına `SelectKBest` ile en anlamlı 50 özellik seçildi, ardından `PCA` (Temel Bileşen Analizi) ile boyut uzayı daraltıldı.

## 🧠 Kullanılan Modeller
Proje kapsamında geniş bir algoritma yelpazesi eğitilmiş ve performans metrikleri (Accuracy, F1-Score, ROC-AUC) üzerinden karşılaştırmalar yapılmıştır:

**Geleneksel Makine Öğrenmesi Modelleri:**
* Random Forest Classifier
* XGBoost
* Logistic Regression
* K-Nearest Neighbors (KNN)
* Gradient Boosting & Extra Trees
* Naive Bayes & Decision Tree

**Derin Öğrenme Modelleri:**
* **MLP (Multi-Layer Perceptron):** Keras ile inşa edilen, Dropout katmanlarıyla aşırı öğrenmenin (overfitting) önüne geçilen temel sinir ağı.
* **CNN (Convolutional Neural Network):** Tablo verisi özel bir dönüşümle (5x10x1) matris formatına getirilerek evrişimli sinir ağına beslendi.

## 📊 Değerlendirme ve Sonuç
Sistem, çalıştırılan tüm modellerin tahmin sonuçlarını Karmaşıklık Matrisi (Confusion Matrix) ve Sınıflandırma Raporları ile görselleştirmektedir. Tüm pipeline sonucunda en yüksek doğruluğu üreten model tespit edilmekte ve daha sonra kullanılmak üzere (`.joblib` veya `.h5` formatında) otomatik olarak dışa aktarılmaktadır.

## 🛠️ Kullanılan Teknolojiler
* **Programlama Dili:** Python
* **Veri Manipülasyonu ve Görselleştirme:** Pandas, NumPy, Matplotlib, Seaborn
* **Makine Öğrenmesi & Veri İşleme:** Scikit-learn, Imbalanced-learn (SMOTE)
* **Derin Öğrenme:** TensorFlow, Keras
