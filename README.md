# Döviz Kuru Şoklarında Dinamik Fiyatlama ve Kâr Optimizasyonu

Bu proje; perakende satış verilerini USD/TRY kuru ve Tüketici Güven Endeksi ile birleştirerek gelecek haftanın ürün bazlı talebini tahmin eder. Tahmin edilen talep ve fiyat esnekliği kullanılarak her ürün için beklenen kârı en yüksek yapan fiyat değişimi seçilir.

## Proje Kapsamı

- **Veri harmanlama:** Online Retail işlemleri, OECD/FRED USD/TRY kuru ve TCMB EVDS Tüketici Güven Endeksi
- **Özellik mühendisliği:** fiyat esnekliği, kur değişimi, kur volatilitesi, makro risk bayrağı, talep gecikmeleri ve dört haftalık talep ortalaması
- **Modelleme:** zaman bazlı eğitim/test ayrımı, medyan temel model ve XGBoost
- **Model değerlendirme:** MAE, RMSE ve R²
- **Açıklanabilir yapay zeka:** SHAP değişken önemleri
- **Finansal simülasyon:** %5 kur şoku altında sabit zam ve ürün bazlı optimize fiyat karşılaştırması
- **İşletme değeri:** maliyet sonrası net fayda ve ROI hesabı

## Veri Kaynakları

- [UCI Online Retail](https://archive.ics.uci.edu/dataset/352/online+retail)
- [TCMB EVDS](https://evds2.tcmb.gov.tr/)
- [OECD/FRED USD/TRY - CCUSMA02TRM618N](https://fred.stlouisfed.org/series/CCUSMA02TRM618N)

## Çalıştırma

`Final_Projesi` klasöründeki dosyaları aynı dizinde tutun ve `proje.ipynb` dosyasını Jupyter Notebook veya JupyterLab ile açın. Hücreleri yukarıdan aşağıya çalıştırın. İlk hücre gerekli Python paketlerini kurar.

Notebook çalıştığında aşağıdaki çıktılar oluşturulur:

- `Omer_Faruk_Ilan_Yonetici_Ozeti.pdf`
- `eda_ozet.png`
- `model_tahmin.png`
- `shap_grafigi.png`
- `finansal_simulasyon.png`
- `model_metrikleri.xlsx`
- `optimizasyon_sonuclari.xlsx`

## Finansal Varsayımlar

Veri setinde gerçek ürün maliyeti bulunmadığı için simülasyonda başlangıç brüt kâr marjı %30, dövize duyarlı maliyet payı %40 ve haftalık uygulama maliyeti 2.500 para birimi olarak kabul edilmiştir. Fiyat seçenekleri -%5 ile +%10 arasında taranır.

## Sınırlılık

Online Retail verisi Birleşik Krallık merkezli bir perakendeciden alınmıştır. Türkiye makro verileriyle yapılan birleşim, ithal girdili bir perakendeci için karar destek prototipi olarak değerlendirilmelidir. Üretim kullanımında gerçek satın alma maliyetleri, rakip fiyatları ve Türkiye satış verileriyle yeniden kalibrasyon gerekir.

## Öğrenci

Ömer Faruk İlan - 132330060
