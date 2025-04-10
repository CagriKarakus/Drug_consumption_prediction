
# Madde Bağımlılığı Tahmini | Drug Consumption Prediction

Bu proje, **UCI Drug Consumption** veri seti kullanılarak bireylerin çeşitli maddeleri kullanma risklerini makine öğrenmesi yoluyla tahmin etmeyi amaçlamaktadır. Modelleme sürecinde, **Ridge Classifier** algoritması tercih edilmiş ve temel hiperparametre olan `𝛼` değeri **Bayesian Optimization** (BayesSearchCV) yöntemi ile optimize edilmiştir.

## İçerik

- Ridge Classifier ile çok sınıflı madde kullanımı tahmini
- BayesSearchCV ile hiperparametre optimizasyonu
- Label Encoding, StandardScaler gibi ön işleme teknikleri
- Sınıf dengesizliği analizi ve öneriler
- Özelliklerin madde kullanımına etkisi

## Dosya Yapısı

```
drug-consumption-prediction/
├── README.md
├── drug_consumption_prediction.ipynb
├── drug_consumption_prediction.pdf
├── requirements.txt
├── data/
│   └── README.md
├── figures/
│   └── (görseller buraya)
```

## Kullanılan Veri Seti

UCI Machine Learning Repository üzerinden alınan **Drug Consumption (Quantified)** veri seti kullanılmıştır.

🔗 [Veri Setine Git](https://archive.ics.uci.edu/ml/datasets/Drug+consumption+(quantified))

Veri seti; kişilik özellikleri, yaş, cinsiyet, etnik köken gibi bireysel bilgilerle birlikte 18 farklı maddeye yönelik kullanım geçmişi verilerini içermektedir. Cevaplar, üç sınıflı hale getirilmiştir:

- `0`: Düşük kullanım
- `1`: Orta kullanım
- `2`: Yüksek kullanım

## Kurulum ve Kullanım

Projeyi klonlayın ve bağımlılıkları yükleyin:

```bash
git clone https://github.com/kullanici-adi/drug-consumption-prediction.git
cd drug-consumption-prediction
pip install -r requirements.txt
```

Notebook'u çalıştırmak için:
```bash
jupyter notebook drug_consumption_prediction.ipynb
```

## Hızlı Başlangıç (Google Colab)

Projeyi doğrudan Colab üzerinden çalıştırmak için:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/kullanici-adi/drug-consumption-prediction/blob/main/drug_consumption_prediction.ipynb)

## Öne Çıkan Bulgular

| Madde       | En İyi α | Doğruluk | F1 Skoru |
|-------------|----------|----------|----------|
| Caffeine    | 0.0191   | 0.869    | 0.81     |
| Heroin      | 0.0191   | 0.876    | 0.82     |
| Mushrooms   | 0.0191   | 0.730    | 0.72     |
| Semeron     | 0.0191   | **0.995**| 0.99     |

> **Not:** Bazı maddelerde `yüksek kullanım` sınıfı çok az örnek içerdiği için bu sınıflarda modelin performansı düşmektedir.

## Kullanılan Yöntemler

- `RidgeClassifier` (sklearn)
- `BayesSearchCV` (scikit-optimize)
- `StandardScaler`, `LabelEncoder`
- Confusion Matrix Analizi
- Özellik önem analizi (coef_)

## Geliştirme Önerileri

- `SMOTE` gibi oversampling yöntemleri ile sınıf dengesizliğinin azaltılması
- SHAP gibi açıklanabilirlik tekniklerinin eklenmesi
- Derin öğrenme veya ensemble modeller ile karşılaştırma yapılması

## Lisans

Bu proje [MIT Lisansı](LICENSE) ile lisanslanmıştır.

---

Her türlü katkı, öneri ve düzeltme için iletişime geçmekten çekinmeyin!  
Geliştiriciler: Çağrı Karakuş, Tankut Arca Can, Engin Çetintaş, Velihan Doğrul
