World Happiness Report — EDA & Predictive Analysis
2015-2017 yılları arasındaki Dünya Mutluluk Raporu verilerini analiz ettim. Ülkelerin mutluluk skorlarını etkileyen faktörleri keşfettim ve mutluluk skoru tahmini için model kurdum.
Dataset
Kaggle'dan aldım: World Happiness Report
3 yıl (2015-2016-2017), 470+ ülke-yıl gözlemi. Feature'lar: GDP, Family, Health, Freedom, Trust, Generosity.
EDA Bulguları
Bölgesel analizde Batı Avrupa ve Kuzey Amerika ülkeleri dominant. GDP ile mutluluk arasında güçlü pozitif korelasyon var — zengin ülkeler daha mutlu. Heatmap analizinde Family ve Health faktörleri GDP kadar güçlü sinyal veriyor. Freedom ve Trust daha zayıf ama anlamlı katkı sağlıyor.
Yıllar içinde trend analizinde bazı ülkelerin 3 yıl boyunca tutarlı yükseliş, bazılarının ise düşüş gösterdiğini gözlemledim.
Model
LazyPredict ile tüm modelleri hızlıca karşılaştırdım — Linear Regression en iyi performansı verdi. Sonra GridSearchCV ile hiperparametre optimizasyonu yaptım.
Sonuçlar:

R²: ~0.99 (çok yüksek — feature'lar skoru neredeyse tamamen açıklıyor)
MSE: çok düşük

Bu sonuç mantıklı çünkü Happiness Score zaten bu feature'lardan türetilmiş bir kompozit skor.
Önemli Bulgular
GDP tek başına yeterli değil — Family ve Health birlikte daha güçlü tahmin gücü veriyor. En mutlu ülkeler (Finlandiya, Danimarka, Norveç) tüm faktörlerde dengeli yüksek skor alıyor. En mutsuz ülkeler ise tek bir faktörde değil, tümünde düşük skor gösteriyor.
Kullanılanlar
Python, Pandas, Matplotlib, Seaborn, Scikit-learn, LazyPredict
