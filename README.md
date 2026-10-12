Wine Quality Exploratory Data Analysis (EDA)

Bu proje Kaggle'dan alınan **WineQT** veri seti kullanılarak kırmızı şarapların kimyasal özellikleri ile kalite dereceleri arasındaki ilişkileri inceleyen bir Keşifçi Veri Analizi çalışmasıdır.

Şarabın kimyasal bileşenlerinin (asitlik, alkol, pH, sülfat vb.) kalite puanı üzerindeki etkilerini anlamak amacıyla veri seti Python ile analiz edilmiştir. Çalışma kapsamında veri yapısının incelenmesi (`Id` sütununun çıkarılması ve duplicate kayıtların tespiti), istatistiksel özetler ve korelasyon analizleri gerçekleştirilmiştir.

---

## Girdi Değişkenleri (Fizikokimyasal Testlere Dayalı)
- `fixed acidity`: Sabit asitlik
- `volatile acidity`: Uçucu asitlik
- `citric acid`: Sitrik asit
- `residual sugar`: Kalıntı (artık) şeker
- `chlorides`: Klorürler
- `free sulfur dioxide`: Serbest kükürt dioksit
- `total sulfur dioxide`: Toplam kükürt dioksit
- `density`: Yoğunluk
- `pH`: Asitlik/Bazlık derecesi
- `sulphates`: Sülfatlar
- `alcohol`: Alkol oranı

**Çıktı Değişkeni (Duyusal Verilere Dayalı):**
- `quality`: Şarap kalite puanı (0 ile 10 arasında)

---

##  Veri Seti Özeti
* **Kaynak:** `WineQT.csv`
* **Başlangıç Boyutu:** 1,143 satır, 13 sütun (`Id` sütunu analizden çıkarılmıştır).
* **Eksik Veri (Missing Values):** Bulunmamaktadır.
* **Yinelenen Veri (Duplicates):** Veri setinde 125 adet tekrar eden satır tespit edilmiştir.
* **Hedef Değişken:** `quality` (3 - 8 arasında kalite puanları; çoğunluk 5 ve 6 puanlarında yoğunlaşmıştır).

---

## Öne Çıkan Bulgular (Insights)
* **Alkol Oranı:** Alkol yüzdesi ile şarap kalitesi arasında pozitif yönlü güçlü bir ilişki (`~0.48`) bulunmaktadır, yüksek kaliteli şarapların alkol oranı ortalamada daha yüksektir.
* **Uçucu Asitlik:** Uçucu asitlik (`volatile acidity`) arttıkça kalite puanı düşmektedir (`~-0.41` negatif korelasyon).
* **Diğer Faktörler:** Sülfatlar (`sulphates`) ve sitrik asit (`citric acid`) bileşenleri de kaliteyi olumlu yönde etkileyen diğer önemli etkenler arasındadır.

### Korelasyon Analizi
Değişkenler arasındaki ilişkileri gösteren ısı haritası (heatmap):
<img width="2654" height="1880" alt="wine_correlation_heatmap" src="https://github.com/user-attachments/assets/8a6823a9-fb9d-40b0-bdaa-2bac971c4e75" />

---

## Kullanılan Teknolojiler
* **Python**
* **Pandas & NumPy** (Veri manipülasyonu)
* **Matplotlib & Seaborn** (Veri görselleştirme)
