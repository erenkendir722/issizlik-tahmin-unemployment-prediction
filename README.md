# 🇹🇷 Türkiye İşsizlik Oranı Tahmini / Turkey Unemployment Rate Forecasting

---

## Türkçe

### Proje Hakkında

Bu proje, **TÜİK (Türkiye İstatistik Kurumu)** tarafından yayımlanan aylık işsizlik verilerini kullanarak Türkiye'nin işsizlik oranını tahmin etmeyi amaçlamaktadır. 2005–2025 yılları arasındaki aylık veriler üzerinde makine öğrenmesi modelleri eğitilerek **2026 yılına ait işsizlik oranı tahminleri** üretilmektedir.

### Veri Seti

| Dosya | Açıklama |
|-------|----------|
| `Veri Seti/issizlik_tuik.csv` | Temizlenmiş CSV formatında aylık işsizlik verileri |
| `Veri Seti/issizlik_tuik_2005-2025.xls` | TÜİK'ten alınan ham Excel verisi |

Veri seti aşağıdaki sütunları içermektedir:
- **Yıl**, **Ay** — Zaman bilgisi
- **Nüfus**, **İş Gücü**, **İstihdam**, **İşsiz** — Nüfus istatistikleri
- **İş Gücüne Dahil Değil** — İş gücü dışında kalan nüfus
- **İşgücüne Katılım Oranı**, **İstihdam Oranı**, **İşsizlik Oranı** — Oransal göstergeler (%)

### Yöntem

1. **Veri Ön İşleme**: Tarih sıralaması, eksik değer kontrolü
2. **Keşifsel Veri Analizi (EDA)**: Zaman serisi ve aylık ortalama grafikleri
3. **Öznitelik Mühendisliği**: Gecikme (lag) değişkenleri oluşturma (`lag_1`, `lag_2`, `lag_12`)
4. **Model Eğitimi**: Linear Regression ve Random Forest Regressor ile eğitim (%85 eğitim / %15 test)
5. **Değerlendirme**: RMSE ve R² metrikleri ile model performans karşılaştırması
6. **2026 Tahmini**: En iyi model (Random Forest) ile 2026 yılının 12 ayı için işsizlik oranı tahmini

### Kullanılan Teknolojiler

- Python 3
- Pandas, NumPy
- Matplotlib
- Scikit-learn

### Çalıştırma

```bash
cd Kod
jupyter notebook issizlik_Tuik.ipynb
```

---

## English

### About the Project

This project aims to forecast Turkey's unemployment rate using monthly unemployment data published by **TÜİK (Turkish Statistical Institute)**. Machine learning models are trained on monthly data from 2005–2025 to generate **unemployment rate predictions for 2026**.

### Dataset

| File | Description |
|------|-------------|
| `Veri Seti/issizlik_tuik.csv` | Cleaned monthly unemployment data in CSV format |
| `Veri Seti/issizlik_tuik_2005-2025.xls` | Raw Excel data from TÜİK |

The dataset contains the following columns:
- **Yıl (Year)**, **Ay (Month)** — Time information
- **Nüfus (Population)**, **İş Gücü (Labor Force)**, **İstihdam (Employment)**, **İşsiz (Unemployed)** — Population statistics
- **İş Gücüne Dahil Değil (Not in Labor Force)** — Population outside the labor force
- **İşgücüne Katılım Oranı (Labor Force Participation Rate)**, **İstihdam Oranı (Employment Rate)**, **İşsizlik Oranı (Unemployment Rate)** — Rate indicators (%)

### Methodology

1. **Data Preprocessing**: Date ordering, missing value checks
2. **Exploratory Data Analysis (EDA)**: Time series and monthly average visualizations
3. **Feature Engineering**: Lag variables (`lag_1`, `lag_2`, `lag_12`)
4. **Model Training**: Linear Regression and Random Forest Regressor (85% train / 15% test split)
5. **Evaluation**: Model performance comparison using RMSE and R² metrics
6. **2026 Forecasting**: Predicting 12 months of 2026 unemployment rates using the best model (Random Forest)

### Technologies Used

- Python 3
- Pandas, NumPy
- Matplotlib
- Scikit-learn

### How to Run

```bash
cd Kod
jupyter notebook issizlik_Tuik.ipynb
```

---

## 📁 Project Structure / Proje Yapısı

```
issizlik_tahmini/
├── Kod/
│   └── issizlik_Tuik.ipynb        # Ana notebook / Main notebook
├── Veri Seti/
│   ├── issizlik_tuik.csv          # CSV veri seti / CSV dataset
│   └── issizlik_tuik_2005-2025.xls # Ham Excel verisi / Raw Excel data
├── .gitignore
└── README.md
```

---

## 📜 Lisans / License

Bu proje akademik amaçlarla geliştirilmiştir.
This project was developed for academic purposes.
