# online_payments_ML
Projem, Online Payments Fraud Detection Dataset kullanarak online ödemelerde dolandırıcılığı tespit etmeyi amaçlamaktadır. Kullanıcı işlem verilerini analiz ederek dolandırıcılık olasılıklarını belirlemek için Lojistik Regresyon, KMeans ve DBSCAN gibi makine öğrenmesi algoritmalarını kullanarak güvenli bir ödeme ortamı sağlamayı hedefliyorum.

PROJENİN KAGGLE LİNKİ:https://www.kaggle.com/code/rukiyekaraatli/online-payments-ml/edit

Online Payments Fraud Detection Dataset Açıklama: Bu veri seti, online ödemelerde dolandırıcılığı tespit etmeye yönelik bir veri setidir. Kategorik ve sayısal değişkenleri içerir.

Kategorik Değişkenler: isFraud, TransactionType, TransactionDate, MerchantCategoryCode Sayısal Değişkenler: TransactionAmount, MerchantID, UserID

print(classification_report(y_test, y_pred_log_reg))
Lojistik Regresyon Performansı:
              precision    recall  f1-score   support

           0       1.00      1.00      1.00      1995
           1       1.00      0.80      0.89         5

    accuracy                           1.00      2000
   macro avg       1.00      0.90      0.94      2000
weighted avg       1.00      1.00      1.00      2000

Lojistik Regresyon Modeli Performans Değerlendirmesi
Lojistik regresyon modelinin performans sonuçları şu şekildedir:

Genel Performans:
Doğruluk (Accuracy): %100, model tüm test verilerini doğru tahmin etmiştir.
Sınıflar Arası Değerlendirme:
Sınıf 0 (Dolandırıcılık Değil):

Precision: 1.00 (Yanlış pozitif yok)
Recall: 1.00 (Yanlış negatif yok)
F1-Score: 1.00 (Mükemmel dengede)
Sınıf 1 (Dolandırıcılık):

Precision: 1.00 (Yanlış pozitif yok)
Recall: 0.80 (Gerçek dolandırıcılık işlemlerinin %80’i tespit edilmiş)
F1-Score: 0.89 (İyi performans, ancak recall düşük)
Ağırlıklı ve Makro Ortalamalar:
Makro Ortalama: Dengesizlik nedeniyle daha düşük.
Ağırlıklı Ortalama: %100, dolandırıcılık olmayan sınıfın fazla olmasının etkisi.
Sonuç:
Model dolandırıcılık olmayan işlemleri mükemmel tespit ederken, dolandırıcılık işlemlerinde bazı eksiklikler göstermektedir. Veri setindeki dengesizlik, dolandırıcılık tespitinde zorluk yaratıyor. Bu durumu iyileştirmek için daha fazla dolandırıcılık örneği eklemek ya da daha karmaşık modelleri değerlendirmek faydalı olabilir.

DBSCAN Modeli Sonuçları
Çıktılar:
Küme Sayısı: 0
Silhouette Skoru Hesaplanamıyor: Küme sayısı 1'den az.
Yorum:
DBSCAN, belirlenen parametrelerle hiçbir küme bulamadı. Bu, veri setinin yapısı, uzaklık ayarları (eps) veya veri dengesizliği nedeniyle olabilir.

Öneriler:
Parametreleri Değiştirin: eps ve min_samples değerlerini ayarlamayı deneyebiliriz.
Veri Ön İşleme: Aykırı değerleri temizleyebiliriz.
Alternatif Modelleri Deneyin: K-Means gibi başka yöntemler de değerlendirebiliriz.

K-Means Modeli Sonuçları
Çıktılar:
Küme Sayısı: 3
Silhouette Skoru: 0.81

Yorum:
Küme Sayısı: Model, 3 farklı küme oluşturdu. Bu, veri setinin belirgin alt gruplara sahip olduğunu gösterir.
Silhouette Skoru: 0.81, kümeler arasındaki ayrışmanın iyi olduğunu belirtir. Bu değer 1'e yakınsa, iyi bir ayrım sağlanmış demektir.
Küme Merkezleri: Her bir kümenin merkez noktaları, o kümedeki verilerin ortalamasını yansıtır. Merkezlerin değerleri, her kümenin karakteristik özellikleri hakkında bilgi verir.
Genel Değerlendirme:
K-Means, bu veri seti için uygun bir model gibi görünüyor; iyi bir ayrım ve anlamlı kümeler oluşturulmuş. Sonuçları daha iyi anlamak için her bir kümenin içindeki verileri incelemek faydalı olabilir.
