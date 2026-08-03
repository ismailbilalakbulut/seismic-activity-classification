# Derin Öğrenme Eğitimi Projeleri

Bu depo, [Derin Öğrenme 2026: 100 Günlük Kamp](https://www.udemy.com/course/derin-ogrenme-bootcamp/) kapsamında verilen toplam 8 adet ödevin çözümlerini ve çalışma dosyalarını içermektedir. Süreç boyunca PyTorch kullanılarak çeşitli yapay sinir ağı mimarileri ve derin öğrenme teknikleri uygulanmıştır.

## 📌 İçindekiler
1. [Ödev 1: Sismik Aktivite Sınıflandırması (Non-Linear MLP)](#ödev-1-sismik-aktivite-sınıflandırması)
2. *Ödev 2: (İleride eklenecek)*
3. *Ödev 3: (İleride eklenecek)*
...

---

## 🛠️ Kurulum ve Bağımlılıklar
Bu depodaki projeleri kendi bilgisayarınızda çalıştırmak için aşağıdaki kütüphanelerin kurulu olması gerekmektedir:
* `torch`
* `pandas`
* `matplotlib`
* `seaborn`
* `scikit-learn`
* `numpy`
---

## 🚀 Ödevler

### Ödev 1: Sismik Aktivite Sınıflandırması
**Dosya:** [`01-NonLinearAssignment.ipynb`](./01-NonLinearAssignment.ipynb)

Bu projede, doğrusal olarak ayrılamayan (non-linear) sismik aktivite verilerini sınıflandırmak için PyTorch ile çok katmanlı bir algılayıcı (MLP) geliştirilmiştir. 
* **Veri:** `underground_wave_energy` ve `vibration_axis_variation` özellikleri kullanılarak sismik olay tespiti (0 veya 1).
* **Mimari:** 2 Girdi -> 10 (ReLU) -> 10 (ReLU) -> 1 Çıktı
* **Eğitim:** BCEWithLogitsLoss ve Adam optimizer (lr=0.01) ile 260 epoch.
* **Sonuç:** Model karar sınırlarını başarıyla öğrenerek test verisinde %100 doğruluk (accuracy) oranına ulaşmıştır.

---

### Ödev 2: (Ödevin Konusu)
*Yeni ödev eklendiğinde buraya kısa bir özet ve dosya linki gelecek.*

---