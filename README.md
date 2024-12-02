# Analisis Prediktif Harga Mobil Bekas di Arab Saudi

## Deskripsi Proyek
Proyek ini menganalisis dataset mobil bekas di Arab Saudi untuk memahami faktor-faktor yang mempengaruhi harga dan mengembangkan model prediktif menggunakan machine learning.

## Tujuan
1. Mengidentifikasi faktor utama yang mempengaruhi harga mobil bekas
2. Mengembangkan model machine learning untuk memprediksi harga
3. Memberikan wawasan yang dapat ditindaklanjuti kepada stakeholder

## Dataset
Dataset berisi 5,624 data mobil bekas dengan fitur:
- Type: Jenis mobil
- Region: Wilayah penjualan
- Make: Merek mobil
- GearType: Jenis transmisi
- Origin: Asal mobil
- Options: Pilihan fitur
- Year: Tahun pembuatan
- EngineSize: Ukuran mesin
- Mileage: Jarak tempuh
- Price: Harga (target)

## Metodologi
1. **Data Understanding & EDA**
   - Analisis distribusi harga
   - Korelasi antar fitur
   - Visualisasi pola data

2. **Data Preprocessing**
   - Penanganan missing value
   - Feature engineering
   - Encoding fitur kategorikal
   - Scaling fitur numerik

3. **Modeling**
   - Linear Regression
   - Ridge Regression
   - Lasso Regression
   - Random Forest (model terbaik)

4. **Hyperparameter Tuning**
   - RandomizedSearchCV untuk optimasi Random Forest
   - Parameter optimal: n_estimators=323, min_samples_leaf=2

## Hasil
- Model Random Forest terbaik:
  - RMSE: 34,655.65
  - MAE: 25,764.88
  - R² Score: 0.3387
- Faktor paling berpengaruh:
  - Jarak tempuh (Mileage)
  - Ukuran mesin (Engine Size)
  - Tahun pembuatan (Year)

## Cara Penggunaan
```python
# Load model dan transformers
model, scaler, encoders = load_model_and_transformers()

# Format input data
sample_car = {
    'Make': 'Toyota',
    'Type': 'Land Cruiser',
    'Region': 'Riyadh',
    'Gear_Type': 'Automatic',
    'Origin': 'Saudi',
    'Options': 'Full',
    'Year': 2019,
    'Age': 5,
    'Engine_Size': 4.6,
    'Mileage': 50000
}

# Prediksi harga
predicted_price = predict_price(sample_car, model, scaler, encoders)
```

## Requirements
- Python 3.x
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

## License
This project is open source and available under the [MIT License](LICENSE).
