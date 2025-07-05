# 📊 Telekom Müşteri Terk (Churn) Analizi ve Tahmin Modeli

Bu proje, bir telekom şirketinin müşteri verilerini kullanarak, hangi müşterilerin hizmeti terk etme (churn) eğiliminde olduğunu analiz eder ve bu durumu tahmin eden makine öğrenmesi modelleri geliştirir.

## 🎯 İş Problemi

Müşteri kaybı, telekom şirketleri için önemli bir gelir kaybı anlamına gelmektedir. Mevcut bir müşteriyi elde tutmanın maliyeti, yeni bir müşteri kazanmaktan çok daha düşüktür. Bu projenin amacı, müşterilerin demografik bilgileri, abonelik detayları ve kullanım alışkanlıklarına dayanarak, hangi müşterilerin ayrılma riski taşıdığını önceden tespit etmektir. Bu sayede şirket, riskli müşterilere özel kampanyalar ve teklifler sunarak onları elde tutma şansı yakalayabilir.

## 💾 Veri Seti

Bu projede kullanılan veri seti, Kaggle'da bulunan "Telco Customer Churn" veri setidir. Veri seti, 7043 müşteriye ait 21 farklı özellik içermektedir.

## 🛠️ Uygulanan Adımlar

1.  **Veri Yükleme ve Keşifsel Veri Analizi (EDA):** Veri seti incelenmiş, temel istatistikler çıkarılmış ve görselleştirmeler yapılmıştır. Müşteri kaybı oranının %27 civarında olduğu ve bunun bir "dengesiz veri seti" problemi olduğu tespit edilmiştir.
2.  **Veri Ön İşleme:** Modellerin anlayabilmesi için kategorik veriler (örn: 'Yes'/'No') sayısal değerlere dönüştürülmüş ve `One-Hot Encoding` tekniği uygulanmıştır.
3.  **Modelleme:** Veri, Eğitim (%80) ve Test (%20) olarak ikiye ayrılmıştır. Sınıflandırma problemi için iki güçlü model kullanılmıştır:
    * **Random Forest Classifier**
    * **XGBoost Classifier**
4.  **Model Değerlendirme:** Modellerin performansı `Accuracy`, `Precision`, `Recall`, `F1-Score` gibi metriklerle ve `Confusion Matrix` ile değerlendirilmiştir.

## 📈 Model Sonuçları ve Bulgular

Her iki model de ~%78 doğruluk oranı elde etmiştir. Müşteri kaybını tahmin etmede en önemli metrik olan **Recall** değerinde, **XGBoost modeli (%55)**, Random Forest modeline (%51) göre biraz daha iyi performans göstermiştir.

Özellik Önem Analizi'ne göre, müşteri kaybını etkileyen en önemli 3 faktör şunlardır:
1.  **İnternet Servisi (Fiber Optik)**: İnternet Servisi'ne sahip müşterilerin ayrılma olasılığı çok daha yüksek.
2.  **Sözleşme Tipi (2 yıllık)**: 2 yıllık sözleşmeye sahip müşterilerin ayrılma olasılığı çok daha yüksek.
3.  **Sözleşme Tipi (1 yıllık)**: 1 yıllık sözleşmeye sahip müşterilerin ayrılma olasılığı çok daha yüksek.

## 💻 Kullanılan Teknolojiler
* Python
* Pandas & NumPy
* Matplotlib & Seaborn
* Scikit-learn
* XGBoost