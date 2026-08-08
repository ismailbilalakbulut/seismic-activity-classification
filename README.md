# Sismik Aktivite Sınıflandırması

Bu proje, Udemy platformundaki [Derin Öğrenme 2026: 100 Günlük Kamp](https://www.udemy.com/course/derin-ogrenme-bootcamp/) kapsamında geliştirilmiştir ve eğitimin ilk uygulamalı projesidir. 

Projenin amacı, PyTorch kullanılarak doğrusal olarak ayrılamayan (non-linear) karmaşık bir veri setini Çok Katmanlı Algılayıcı (MLP) modeli ile sınıflandırmaktır.

## 📊 Veri Seti
Projede sismik hareketleri temsil eden `08-seismic_activity_svm.csv` adlı veri seti kullanılmıştır.
* **Özellikler (Features):** `underground_wave_energy` (Dalga Enerjisi) ve `vibration_axis_variation` (Titreşim Varyasyonu)
* **Hedef (Target):** `seismic_event_detected` (0: Tespit Edilmedi, 1: Tespit Edildi)
* **Veri Dağılımı:** 400 örneklemden oluşan veri seti görselleştirildiğinde, doğrusal bir çizgiyle ayrılamayan, iç içe geçmiş yay şeklinde bir dağılıma sahip olduğu görülmektedir.

## 🧠 Model Mimarisi
Geliştirilen yapay sinir ağı modeli, aralarında doğrusal olmayan yapıyı öğrenebilmesi için ReLU aktivasyon fonksiyonları bulunan 3 Doğrusal (Linear) katmandan oluşmaktadır:
* **Gizli Katman 1:** 2 girdi -> 10 nöron (Aktivasyon: ReLU)
* **Gizli Katman 2:** 10 nöron -> 10 nöron (Aktivasyon: ReLU)
* **Çıktı Katmanı:** 10 nöron -> 1 çıktı 

## ⚙️ Eğitim Detayları
* **Kayıp Fonksiyonu (Loss Function):** İkili sınıflandırma problemi olduğu için `nn.BCEWithLogitsLoss()` kullanılmıştır.
* **Optimizasyon (Optimizer):** `Adam` algoritması tercih edilmiş olup Öğrenme Oranı (Learning Rate) `0.01` olarak belirlenmiştir.
* **Veri Bölme:** %80 Eğitim (Train), %20 Test
* **Epoch Sayısı:** Model toplam 260 epoch eğitilmiştir.

## 📈 Sonuçlar
Model, veri setindeki non-linear (doğrusal olmayan) karar sınırlarını çok kısa bir sürede öğrenmeyi başarmış olup, 60. epoch itibarıyla hem eğitim hem de test verisinde **%100 doğruluk (accuracy)** oranına ulaşmıştır. Aşırı öğrenme (overfitting) durumu gözlenmemiştir.

Karar sınırları (decision boundaries) eğitimin sonunda kontur grafikleri (contour plot) ile görselleştirilerek modelin veriyi nasıl sınırlandırdığı incelenmiştir.

## 🛠️ Kurulum ve Çalıştırma
Projeyi kendi bilgisayarınızda çalıştırmak için aşağıdaki kütüphanelerin kurulu olması gerekmektedir:
* `torch`
* `pandas`
* `matplotlib`
* `seaborn`
* `scikit-learn`
* `numpy`

Gerekli bağımlılıkları kurduktan sonra `01-NonLinearAssignment.ipynb` dosyasını çalıştırabilirsiniz.
