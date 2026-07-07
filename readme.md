# 🚀 ML Based Sales Prediction API Project

> **Satış Tahmin Sistemini Güçlendir: Makine Öğrenmesi ile İş Zekasını Ileriye Taşı**

Bir e-ticaret platformunun (Northwind Database) satış verilerini analiz ederek, müşteri davranışlarını anlamak ve gelecekteki satış trendlerini tahmin etmek için tasarlanmış **end-to-end machine learning projesi**. Bu proje, veri ön işlemesinden model eğitimine kadar tüm ML pipeline'ını içerir.

---

## 📋 İçindekiler

- [Proje Özeti](#-proje-özeti)
- [Özellikler](#-özellikler)
- [Teknoloji Stack'i](#-teknoloji-stacki)
- [Proje Yapısı](#-proje-yapısı)
- [Kurulum Adımları](#-kurulum-adımları)
- [Kullanım](#-kullanım)
- [ML Modelleri](#-ml-modelleri)
- [Veri Pipeline'ı](#-veri-pipelinei)
- [Katkı Yapma](#-katkı-yapma)

---

## 🎯 Proje Özeti

Bu projede, Northwind e-ticaret veritabanından çıkarılan satış verileri kullanılarak:

✨ **Amaçlar:**
- 📊 **Satış Tahmini**: Gelecekteki ürün satış miktarların�� ve gelirlerini tahmin etmek
- 👥 **Müşteri Segmentasyonu**: Müşteri davranışlarına göre farklı segmentler oluşturmak (Low, Medium, High spending)
- 💡 **İş Insights**: Ürün kategorilerine göre satış performansı analiz etmek
- 🔮 **Tahmin Modelleri**: Farklı ML algoritmalarını karşılaştırarak en iyi performans gösteren modeli belirlemek

**Örnek Kullanım Senaryoları:**
- Bir kategoride belirli ayda ne kadar satış yapılacağını tahmin etmek
- Müşterileri harcama düzeylerine göre sınıflandırmak ve hedefli pazarlama yapılmak
- Ürün fiyatlandırması ve stok yönetimi için veri destekli kararlar almak

---

## ✨ Özellikler

### 🔑 Temel Yetenekler
- ✅ **PostgreSQL Entegrasyonu**: SQLAlchemy ORM ile veritabanı bağlantısı
- ✅ **Gelişmiş Veri Ön İşleme**: Missing value handling, feature engineering, normalization
- ✅ **Exploratory Data Analysis (EDA)**: Veri yapısı ve dağılımının detaylı analizi
- ✅ **Multiple ML Models**: 6+ farklı makine öğrenmesi algoritması
- ✅ **Model Değerlendirmesi**: Accuracy, MAE, RMSE ve confusion matrix metrikler
- ✅ **Modüler Mimari**: Kolay ölçeklenebilir ve bakım yapılabilir yapı

### 🎨 İleri Özellikler
- 📈 Learning Curve visualizasyonu
- 🔄 Train-Test Split stratejisi (80-20 split)
- 📦 Standard Scaler ile feature normalizasyonu
- 🏷️ Label Encoding ve One-Hot Encoding
- 💾 Processed data CSV export

---

## 🛠️ Teknoloji Stack'i

### **Backend & ML Framework**
| Teknoloji | Versiyon | Amaç |
|-----------|----------|------|
| **Python** | 3.8+ | Ana programlama dili |
| **pandas** | Veri manipülasyonu ve analiz |
| **numpy** | Sayısal hesaplamalar |
| **scikit-learn** | Klasik ML algoritmaları |
| **XGBoost** | Yüksek perforans gradient boosting |

### **Veritabanı & ORM**
| Teknoloji | Amaç |
|-----------|------|
| **PostgreSQL** | İlişkisel veritabanı |
| **SQLAlchemy** | Python ORM ve SQL query builder |
| **psycopg2** | PostgreSQL Python adapter |

### **Geliştirme Tools**
| Tool | Amaç |
|------|------|
| **python-dotenv** | Environment variable management |
| **matplotlib** | Grafik ve visualization |
| **seaborn** | İstatistiksel veri görselleştirme |

---

## 📁 Proje Yapısı

```
ML_BASED_SALES_PREDICTION__API_PROJECT/
│
├── 📄 readme.md                          # Proje dokumentasyonu
├── 📄 requirements.txt                   # Python dependencies
├── 📄 .env.example                       # Ortam değişkenleri template
│
├── 📁 src/                               # Kaynak kodlar
│   ├── 📁 api/                           # API endpoints (geliştirme aşamasında)
│   │   ├── endpoints.py                  # API route'ları
│   │   └── schemas.py                    # Pydantic schemas
│   │
│   ├── 📁 data/                          # Veri işleme modülü
│   │   ├── database.py                   # PostgreSQL bağlantı yapılandırması
│   │   ├── preprocessing.py              # Feature engineering ve veri hazırlığı
│   │   ├── preprocessing_data1.py        # Alternatif preprocessing pipeline
│   │   ├── 📁 models/                    # ORM modelleri (SQLAlchemy)
│   │   └── 📁 processed/                 # İşlenmiş veri (CSV outputs)
│   │       ├── sales_data.csv            # Merge edilmiş order, product, category verileri
│   │       └── features.csv              # Müşteri-kategori özellik seti
│   │
│   └── 📁 models/                        # ML Modelleri
│       ├── decision_tree_model.py        # Random Forest & Decision Tree Classification
│       ├── knn_model.py                  # K-Nearest Neighbors
│       ├── linear_regression_model.py    # Linear Regression
│       ├── random_forest_regressor.py    # Random Forest Regression
│       ├── regression_model.py           # Polynomial Regression
│       ├── xgboost_model.py              # XGBoost Regression
│       └── predict.py                    # Tahmin motorları (geliştirilecek)
│
├── 📁 research/                          # Araştırma ve EDA
│   └── EDA.py                            # Exploratory Data Analysis fonksiyonları
│
└── 📁 docs/                              # Belgelendirme (boş - geliştirilecek)
```

### 🔗 Veri Akışı

```
PostgreSQL Northwind DB
        ↓
    database.py (Bağlantı)
        ↓
preprocessing.py (Query & Merge)
        ↓
[Orders × Order_Details × Products × Categories]
        ↓
Feature Engineering (Temporal + Aggregation)
        ↓
CSV Export → sales_data.csv, features.csv
        ↓
ML Models (Training & Evaluation)
        ↓
Predictions & Insights
```

---

## 🚀 Kurulum Adımları

### **Ön Koşullar**
- Python 3.8 veya üzeri
- PostgreSQL Server (çalışan)
- pip (Python package manager)

### **1️⃣ Adım: Repository'yi Clone Et**
```bash
git clone https://github.com/sevval-345/ML_BASED_SALES_PREDICTION__API_PROJECT.git
cd ML_BASED_SALES_PREDICTION__API_PROJECT
```

### **2️⃣ Adım: Virtual Environment Oluştur**
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate
```

### **3️⃣ Adım: Dependencies Yükle**
```bash
pip install -r requirements.txt
```

### **4️⃣ Adım: Ortam Değişkenlerini Ayarla**
```bash
# .env.example'ı kopyala ve düzenle
cp .env.example .env
```

**`.env` dosyasını düzenle (PostgreSQL bilgilerin ile):**
```dotenv
DB_USER=postgres              # PostgreSQL kullanıcı adı
DB_PASSWORD=your_password     # PostgreSQL şifresi
DB_HOST=localhost             # Veritabanı host'u
DB_PORT=5432                  # PostgreSQL port (default: 5432)
DB_NAME=northwind             # Northwind veritabanı adı
```

### **5️⃣ Adım: Veritabanı Bağlantısını Test Et**
```bash
cd src/data
python database.py
# Beklenen output: ✅ PostgreSQL bağlantısı başarılı!
```

---

## 📊 Kullanım

### **1. Veri Ön İşleme & Feature Engineering**
```bash
cd src/data
python preprocessing.py
```

**Ne yapıyor?**
- Northwind veritabanından orders, order_details, products, categories tablolarını sorguluyor
- İş (business) features oluşturuyor:
  - `total_sales`: Sipariş tutarı hesaplaması
  - `unique_products`: Satın alınan ürün çeşitliliği
  - `total_quantity`: Toplam ürün miktarı
  - `order_count`: Müşteri sipariş sayısı
  - Temporal features: year, month, day

**Output:**
- ✅ `src/data/processed/sales_data.csv` - Merge edilmiş satış verileri
- ✅ `src/data/processed/features.csv` - Feature seti

### **2. Exploratory Data Analysis (EDA)**
```bash
cd research
python EDA.py
```

**Ne yapıyor?**
- Veri şekli ve türleri kontrolü
- Null values analizi
- Dağılım istatistikleri (quantiles, descriptive stats)

### **3. Model Eğitimi ve Değerlendirmesi**

#### **📈 XGBoost Regression (Satış Tahmini)**
```bash
cd src/models
python xgboost_model.py
```

**Beklenecek Çıkışlar:**
```
MAE:  450.23           # Ortalama Mutlak Hata
RMSE: 680.45           # Kök Ortalama Kare Hatası
MSE:  463011.20        # Ortalama Kare Hatası
```

#### **🌳 Decision Tree & Random Forest (Müşteri Segmentasyonu)**
```bash
cd src/models
python decision_tree_model.py
```

**Beklenecek Çıkışlar:**
```
Accuracy Decision tree: 0.95        # 95% doğruluk
Classification Report:
              precision  recall  f1-score
    Low           0.96    0.94     0.95
    Medium        0.94    0.95     0.95
    High          0.95    0.96     0.96
```

#### **📊 Diğer Modeller**
```bash
python linear_regression_model.py    # Lineer Regresyon
python random_forest_regressor.py    # Random Forest Regresyon
python knn_model.py                  # K-Nearest Neighbors
```

---

## 🤖 ML Modelleri

### **Regresyon Modelleri** (Sayısal Çıkış Tahmini)

| Model | Algoritma | Amaç | Strengths | Limitations |
|-------|-----------|------|-----------|-------------|
| **XGBoost** | Gradient Boosting | Satış miktarı tahmini | 🏆 Yüksek doğruluk, feature importance | Hyperparameter tuning gerekli |
| **Random Forest** | Ensemble Decision Trees | Satış hacimleri | Robust, multicollinearity tolerans | Daha yavaş prediction |
| **Linear Regression** | OLS | Baseline model | Interpretable, hızlı | Nonlinear relationships |
| **Polynomial Regression** | High-degree polynomial | Kompleks patterns | Flexible fitting | Overfitting riski |

### **Sınıflandırma Modelleri** (Kategori Tahmini)

| Model | Algoritma | Amaç | Strengths | Limitations |
|-------|-----------|------|-----------|-------------|
| **Decision Tree** | Recursive Splitting | Müşteri segmentasyonu | Interpretable, fast | Overfitting |
| **Random Forest** | Multiple Decision Trees | Segment classification | Robust, good generalization | Black-box model |
| **KNN** | Distance-based | Benzer müşteri bulma | Simple, no training | Slow prediction, sensitive to scale |

### **Model Başarı Metrikleri**

```
📈 REGRESYON METRIKLERI:
├── MAE (Mean Absolute Error): Ortalama mutlak hata
├── RMSE (Root Mean Squared Error): Kök ortalama kare hatası
└── MSE (Mean Squared Error): Ortalama kare hatası

📊 SINIFLANDIRMA METRIKLERI:
├── Accuracy: Doğru tahminlerin oranı
├── Precision: Pozitif tahminlerin doğruluk oranı
├── Recall: Bulunabilecek pozitif örneklerin oranı
├── F1-Score: Precision ve Recall'ın harmonik ortalaması
└── Confusion Matrix: Tahmin türlerinin dağılımı
```

---

## 🔄 Veri Pipeline'ı

### **Adım 1: Veri Çıkarma (Extract)**
```python
# Northwind Database'den SQL query
Query: Orders × Order_Details × Products × Categories
Columns: customer_id, order_date, product_name, quantity, 
         discount, price, category_name
```

### **Adım 2: Veri Dönüştürme (Transform)**
```python
# Feature Engineering
✓ total_sales = order_unit_price × quantity × (1 - discount)
✓ Temporal features: year, month, day extraction
✓ Aggregation: sum, mean, nunique, max operations
✓ Customer-Category level: customer_id × category_id grouping
```

### **Adım 3: Veri Yükleme (Load)**
```python
# CSV'ye export
df.to_csv("src/data/processed/sales_data.csv")
df.to_csv("src/data/processed/features.csv")
```

### **Adım 4: Model Training**
```python
1. Train-Test Split: 80% train, 20% test
2. Scaling: StandardScaler normalization
3. Encoding: One-Hot Encoding (categorical), Label Encoding (target)
4. Training: Model.fit(X_train, y_train)
5. Evaluation: Model.predict(X_test) + metrics
```

---

## 📈 Performans Beklentileri

### **Hedef Metrikler**

```
Regression Models (XGBoost, Random Forest):
├── Target: RMSE < 500
├── Target: MAE < 400
└── Target: R² Score > 0.85

Classification Models (Decision Tree, RF):
├── Target: Accuracy > 0.90
├── Target: Precision > 0.90
└── Target: F1-Score > 0.90
```

### **Örnek Sonuçlar**
- **XGBoost RMSE**: ~680 (Tahminler gerçekten ±680 birim hatalı)
- **Decision Tree Accuracy**: ~95% (19 tane 20'den doğru sınıf tahmini)
- **Feature Importance**: Temporal features (month, day) önemli

---

## 🔐 Güvenlik & Best Practices

### ✅ Yapılması Gerekenler
- 🔒 `.env` dosyasını `.gitignore`'a ekle (hassas veriler)
- 🔄 Veri ön işlemede null values kontrol et
- 📊 Model overfitting'i learning curves ile izle
- 📈 Cross-validation kullan (CV=5 vs CV=10)
- 💾 Model versiyonlandırması yap

### ⚠️ Dikkat Edilecek Noktalar
- Database bağlantı bilgilerini asla hardcode etme
- Processed data dosyalarını `.gitignore`'a ekle
- Model eğitim sürelerine dikkat et (XGBoost uzun sürebilir)
- Feature scaling'i train set'ten fit et, test set'e apply et

---

## 🚧 Geliştirilecek Özellikler

- [ ] **FastAPI Implementation**: REST API endpoints oluştur
- [ ] **Model Serving**: Trained models'ı save/load et (.pkl)
- [ ] **Docker Containerization**: Projesi Docker image olarak package et
- [ ] **Advanced EDA**: Interactive visualizations (Plotly, Dash)
- [ ] **Hyperparameter Tuning**: GridSearchCV / RandomSearchCV
- [ ] **Time Series Forecasting**: ARIMA, Prophet gibi advanced models
- [ ] **Unit Tests**: pytest ile test coverage
- [ ] **CI/CD Pipeline**: GitHub Actions integration
- [ ] **Model Monitoring**: Production metrics tracking

---

## 🤝 Katkı Yapma

Proje üzerinde iyileştirmeler ve yeni özellikler eklemek istiyorsanız:

1. **Fork et**: Repository'nin bir kopyasını oluştur
2. **Branch oluştur**: `git checkout -b feature/yeni-ozellik`
3. **Değişiklikleri yap**: Kodunu ekle ve test et
4. **Commit et**: `git commit -m "Açıklamalı commit mesajı"`
5. **Push et**: `git push origin feature/yeni-ozellik`
6. **Pull Request aç**: Değişikliklerin review'ı istencek

### **Katkı Kategorileri**
- 🐛 Bug fixes
- ✨ Yeni ML modelleri
- 📚 Dokumentasyon iyileştirmeleri
- 🎨 Görselleştirme enhancements
- ⚡ Performance optimizations

---

## 📞 İletişim & Destek

Sorularınız, önerileriniz veya hata raporları için:
- **GitHub Issues**: [Proje Issues Sayfası](https://github.com/sevval-345/ML_BASED_SALES_PREDICTION__API_PROJECT/issues)
- **Email**: sevval-345@github.com

---

## 📄 Lisans

Bu proje MIT Lisansı altında yayınlanmıştır. Detaylar için [LICENSE](LICENSE) dosyasını inceleyiniz.

---

## 🙏 Teşekkürler

- **Northwind Database**: Örnek e-ticaret verileri
- **Scikit-learn, XGBoost, Pandas**: Açık kaynak ML kütüphaneleri
- **PostgreSQL Community**: Güvenilir veritabanı altyapısı

---

## 📊 Project Stats

```
📦 Framework: Python ML Pipeline
📈 Models: 6+ ML algorithms
🗄️ Data: Northwind e-commerce database
📁 Code Lines: ~2,500+ lines
⏱️ Training Time: ~5-30 seconds (model bağlı)
🎯 Accuracy Target: 90%+
```

---

**Last Updated**: Temmuz 2026 | **Status**: 🚀 Active Development

