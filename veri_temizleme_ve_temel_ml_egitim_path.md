# Job Salary Prediction Dataset ile Veri Temizleme ve Temel Makine Öğrenmesi Eğitim Path'i

## Amaç

Bu eğitim path'inin amacı, veri analizi temeli atılmış bir kişinin aynı veri seti üzerinden veri temizleme, makine öğrenmesi mantığı ve temel makine öğrenmesi modellerini öğrenmesini sağlamaktır.

Bu dosya özellikle şu sırayı öğretmek için hazırlanmıştır:

1. Veriyi modele hazırlamadan önce neden temizlemek gerekir
2. Makine öğrenmesinde `hedef değişken` ve `özellikler` nasıl seçilir
3. Veriyi eğitim ve test olarak ayırmak neden zorunludur
4. Temel modeller nasıl kurulur ve nasıl karşılaştırılır
5. Sonucun sadece skor değil, yorum da gerektirdiği nasıl anlaşılır

Bu veri setinde hedef değişken `salary` olduğu için bu path ağırlıklı olarak `regression` mantığı üzerinden ilerlemelidir.

## Bu Dosya Ne Zaman Kullanılmalı

Bu eğitim, `veri_analizi_egitim_path.md` içindeki temel veri inceleme ve görselleştirme aşamaları tamamlandıktan sonra kullanılmalıdır.

Önerilen sıra:

1. Önce veriyi tanı
2. Sonra veriyi analiz et
3. Sonra veriyi temizle
4. Sonra temel makine öğrenmesi mantığını öğren
5. En sonda modelleri karşılaştır

## Bu Eğitimde Kullanılacak Temel Kütüphaneler

- `pandas`: Veri okuma, temizleme, dönüştürme ve tablo işlemleri
- `numpy`: Sayısal işlemler
- `matplotlib`: Temel grafik çizimi
- `seaborn`: Dağılım ve ilişki grafikleri
- `scikit-learn`: Makine öğrenmesi araçları ve modelleri

Makine öğrenmesi tarafında özellikle öğrenilmesi gereken modüller:

- `train_test_split`
- `StandardScaler`
- `OneHotEncoder`
- `ColumnTransformer`
- `Pipeline`
- `LinearRegression`
- `KNeighborsRegressor`
- `DecisionTreeRegressor`
- `RandomForestRegressor`
- `mean_absolute_error`
- `mean_squared_error`
- `r2_score`

## Başlangıçta Verilmesi Gereken Ana Fikir

Makine öğrenmesi, veriye model vermeden önce veriyi doğru hazırlama işidir. Başlangıç seviyesindeki bir öğrenciye en başta şu açıkça söylenmelidir:

- Kötü hazırlanmış veri ile iyi model kurulmaz
- Yüksek skor tek başına iyi analiz demek değildir
- Model kurmak, veriyi anlamanın yerine geçmez
- Test verisini önceden görmek ciddi bir hatadır

## Aşama 1: Veri Temizleme Nedir ve Neden Gerekir

### Hedef

Kişi veri temizlemeyi “bozuk satır silme” olarak değil, analiz ve modelleme öncesi güvenilir veri hazırlama süreci olarak görsün.

### Bu aşamada yaptırılacaklar

- Veri temizleme kavramını kendi cümlesiyle yazsın
- Neden veri temizliği yapılmadan modele geçilmemesi gerektiğini açıklasın
- Bu veri setinde hangi sütunların temizleme açısından kritik olduğunu belirlesin

### Bu veri seti için vurgulanacak noktalar

- `salary` hedef olduğu için burada yapılacak hata tüm modeli bozar
- `experience_years`, `skills_count`, `certifications` sayısal alanlar olduğu için mantık kontrolü önemlidir
- `job_title`, `education_level`, `industry`, `company_size`, `location`, `remote_work` model öncesi dönüştürme gerektirebilir

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `numpy`

### Beklenen çıktı

Kısa bir açıklama metni:

```md
Veri temizleme bu proje için neden gerekli?
- ...
- ...
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 2: Eksik Değer, Tekrar Eden Satır ve Bozuk Değer Kontrolü

### Hedef

Kişi modelleme öncesi temel kalite kontrollerini sistemli şekilde yapmayı öğrensin.

### Bu aşamada yaptırılacaklar

- Eksik değer kontrolü yapsın
- Tekrarlayan satırları kontrol etsin
- Sayısal sütunlarda negatif veya mantıksız değerleri kontrol etsin
- Kategorik sütunlarda yazım tutarlılığına baksın

### Bu veri seti için özel kontrol başlıkları

- `experience_years` negatif mi
- `salary` sıfır veya negatif mi
- `skills_count` mantıklı bir aralıkta mı
- `certifications` mantıklı bir aralıkta mı
- `remote_work` beklenen sabit kategorilerle mi geliyor

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `numpy`

### Beklenen çıktı

```md
## Temizlik Kontrol Özeti

- Eksik değer:
- Tekrar eden satır:
- Şüpheli sayısal değer:
- Kategorik tutarsızlık:
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 3: Aykırı Değer ve Mantık Kontrolü

### Hedef

Kişi aykırı değeri sadece “silinmesi gereken satır” olarak değil, önce anlaşılması gereken gözlem olarak görsün.

### Bu aşamada yaptırılacaklar

- `salary` için boxplot oluştursun
- `experience_years` için dağılımı incelesin
- Çok yüksek veya çok düşük değerlerin mantıklı olup olmadığını yorumlasın
- Aykırı değer görüldüğünde hemen silmek yerine önce not alsın

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `matplotlib`
- `seaborn`

### Öğrenilmesi gereken ana fikir

- Her aykırı değer hata değildir
- Aykırı değeri silmek, dönüştürmek veya olduğu gibi bırakmak farklı sonuçlar doğurur
- Başlangıç seviyesinde amaç tüm aykırı değerleri yok etmek değil, onları tanımaktır

### Beklenen çıktı

```md
## Aykırı Değer Notu

- Hangi sütunda dikkat çekici değerler var:
- Bunlar veri hatası mı, doğal uç değer mi:
- Şimdilik nasıl davranılacak:
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 4: Modelleme Öncesi Özellik ve Hedef Seçimi

### Hedef

Kişi `X` ve `y` mantığını öğrensin.

### Bu aşamada yaptırılacaklar

- Hedef değişkeni `salary` olarak ayırsın
- Özellik sütunlarını belirlesin
- Hedef sütunun neden giriş değişkenleri arasına konulmaması gerektiğini açıklasın
- Sayısal ve kategorik özellikleri iki ayrı grup halinde yazsın

### Bu veri seti için örnek ayrım

- `y`: `salary`
- Sayısal özellikler: `experience_years`, `skills_count`, `certifications`
- Kategorik özellikler: `job_title`, `education_level`, `industry`, `company_size`, `location`, `remote_work`

### Bu aşamada kullanılacak kütüphaneler

- `pandas`

### Beklenen çıktı

```md
## Modelleme İçin Değişkenler

- Hedef değişken:
- Sayısal özellikler:
- Kategorik özellikler:
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 5: Makine Öğrenmesinin Temel Mantığı

### Hedef

Kişi makine öğrenmesinin sadece kod değil, tahmin mantığı olduğunu kavrasın.

### Bu aşamada yaptırılacaklar

- `regression` ve `classification` farkını öğrensin
- Bu veri setinin neden `regression` problemi olduğunu açıklasın
- Eğitim verisi ve test verisi farkını yazsın
- Aşırı ezberleme mantığını basit dille anlatsın

### Özellikle vurgulanması gereken kavramlar

- `feature`
- `target`
- `prediction`
- `train set`
- `test set`
- `overfitting`
- `generalization`

### Bu aşamada kullanılacak kütüphaneler

- Bu aşama daha çok kavramsaldır
- Örnek göstermek için `pandas` kullanılabilir

### Beklenen çıktı

```md
Bu veri seti neden regression problemidir?
- ...

Train ve test ayrımı neden gereklidir?
- ...
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 6: Eğitim ve Test Ayrımı

### Hedef

Kişi model kurmadan önce veriyi doğru şekilde ayırmayı öğrensin.

### Bu aşamada yaptırılacaklar

- Veriyi `train` ve `test` olarak ayırsın
- Aynı veri ile hem eğitip hem test etmenin neden yanlış olduğunu açıklasın
- Sabit `random_state` kullanımının neden önemli olduğunu öğrensin

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `scikit-learn`

### Öğrenilmesi gereken temel araç

- `train_test_split`

### Beklenen çıktı

```md
- Eğitim verisi boyutu:
- Test verisi boyutu:
- Bu ayrımı neden yaptım:
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 7: Kategorik Verileri Dönüştürme ve Ölçekleme

### Hedef

Kişi modelin sayısal giriş beklediğini ve bazı modellerin ölçekten etkilendiğini öğrensin.

### Bu aşamada yaptırılacaklar

- Kategorik sütunların neden doğrudan modele verilemeyeceğini öğrensin
- `OneHotEncoder` mantığını öğrensin
- Sayısal sütunların ne zaman ölçeklenmesi gerektiğini öğrensin
- Özellikle `KNN` modelinde ölçeklemenin neden kritik olduğunu açıklasın

### Bu veri seti için vurgulanacak nokta

- `job_title`, `education_level`, `industry`, `company_size`, `location`, `remote_work` dönüştürme gerektirir
- `KNN` uzaklık temelli çalıştığı için ölçekleme önemlidir

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `scikit-learn`
- `numpy`

### Öğrenilmesi gereken araçlar

- `OneHotEncoder`
- `StandardScaler`
- `ColumnTransformer`
- `Pipeline`

### Beklenen çıktı

```md
## Veri Hazırlama Kararı

- Hangi sütunlar encode edildi:
- Hangi sütunlar scale edildi:
- Bunun nedeni:
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 8: İlk Model Olarak Linear Regression

### Hedef

Kişi ilk modelini en basit ve yorumlaması en kolay yapı ile kursun.

### Bu aşamada yaptırılacaklar

- Bir `LinearRegression` modeli kursun
- Train verisi ile modeli eğitsin
- Test verisi üzerinde tahmin üretsin
- Temel hata metriklerini hesaplasın

### Bu model neden önce öğretilmeli

- Basittir
- Hızlıdır
- Başlangıç seviyesinde iyi bir referans modeldir
- Daha karmaşık modelleri karşılaştırmak için temel oluşturur

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `scikit-learn`
- `numpy`

### Beklenen çıktı

```md
## Linear Regression Sonucu

- MAE:
- RMSE:
- R2:
- İlk yorum:
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 9: KNN Regressor

### Hedef

Kişi `KNN` modelinin temel mantığını ve ölçekleme ile ilişkisini öğrensin.

### Bu aşamada yaptırılacaklar

- `KNeighborsRegressor` modeli kursun
- Farklı `k` değerleri denesin
- Ölçekleme ile ve ölçekleme olmadan sonucu karşılaştırsın
- `KNN` modelinin neden komşuluk mantığıyla çalıştığını açıklasın

### Bu model için özellikle öğretilmesi gerekenler

- Küçük `k` daha hassas olabilir
- Büyük `k` daha yumuşak sonuç verebilir
- Özellik ölçekleri farklıysa uzaklık hesabı bozulabilir

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `numpy`
- `scikit-learn`
- `matplotlib`

### Beklenen çıktı

```md
## KNN Sonucu

- Denenen k değerleri:
- En iyi sonuç veren k:
- Ölçekleme fark yarattı mı:
- KNN için kısa yorum:
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 10: Decision Tree Regressor

### Hedef

Kişi ağaç tabanlı modellerin doğrusal olmayan ilişkileri nasıl yakalayabildiğini görsün.

### Bu aşamada yaptırılacaklar

- `DecisionTreeRegressor` modeli kursun
- Ağacın çok derin olmasının neden riskli olduğunu öğrensin
- Farklı `max_depth` değerleri deneyerek sonuçları karşılaştırsın

### Bu model için özellikle öğretilmesi gerekenler

- Karar ağaçları kolay ezberleyebilir
- Çok iyi train sonucu almak her zaman iyi model demek değildir
- Ağaç tabanlı modeller ölçeklemeden genellikle daha az etkilenir

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `numpy`
- `scikit-learn`

### Beklenen çıktı

```md
## Decision Tree Sonucu

- Denenen derinlikler:
- En iyi test sonucu:
- Overfitting şüphesi var mı:
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 11: Random Forest Regressor

### Hedef

Kişi tek bir ağacın yerine çoklu ağaç mantığını öğrensin.

### Bu aşamada yaptırılacaklar

- `RandomForestRegressor` modeli kursun
- `n_estimators` kavramını öğrensin
- Sonucu karar ağacı ile karşılaştırsın

### Bu model için özellikle öğretilmesi gerekenler

- Birden fazla ağacın birlikte çalışması genelde daha dengeli sonuç verir
- Tek bir ağaca göre aşırı ezberleme riski daha kontrollü olabilir
- Başlangıç seviyesi için güçlü ama yine de yorumlanabilir bir modeldir

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `numpy`
- `scikit-learn`

### Beklenen çıktı

```md
## Random Forest Sonucu

- n_estimators:
- MAE:
- RMSE:
- R2:
- Decision Tree ile farkı:
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 12: Model Değerlendirme Metrikleri

### Hedef

Kişi model sonuçlarını sadece “iyi” veya “kötü” diye değil, metriklerle yorumlayabilsin.

### Bu aşamada yaptırılacaklar

- `MAE` nedir öğrensin
- `MSE` nedir öğrensin
- `RMSE` nedir öğrensin
- `R2` nedir öğrensin
- Aynı modelleri aynı metriklerle kıyaslasın

### Özellikle vurgulanması gerekenler

- Tek bir metriğe bakmak yeterli değildir
- Düşük hata değeri genelde daha iyidir
- `R2` tek başına karar vermek için yeterli değildir

### Bu aşamada kullanılacak kütüphaneler

- `numpy`
- `pandas`
- `scikit-learn`

### Beklenen çıktı

```md
## Model Karşılaştırma Tablosu

| Model | MAE | RMSE | R2 | Kısa Yorum |
|------|-----|------|----|------------|
| Linear Regression |  |  |  |  |
| KNN |  |  |  |  |
| Decision Tree |  |  |  |  |
| Random Forest |  |  |  |  |
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 13: Sonuçları Yorumlama ve Model Seçimi

### Hedef

Kişi en yüksek skoru alan modeli körü körüne seçmek yerine neden seçtiğini açıklayabilsin.

### Bu aşamada yaptırılacaklar

- Hangi modelin neden daha iyi olduğunu yazsın
- Skor, sadelik ve yorumlanabilirlik arasında denge kursun
- Hangi modelin başlangıç seviyesi için daha öğretici olduğunu açıklasın

### Bu veri seti için beklenen düşünme biçimi

- `Linear Regression` basit ve öğreticidir
- `KNN` uzaklık mantığını öğretir
- `Decision Tree` ezberleme riskini gösterir
- `Random Forest` daha güçlü topluluk mantığını gösterir

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `scikit-learn`

### Beklenen çıktı

```md
## Seçilen Model

- En dengeli model:
- Neden:
- Güçlü yönü:
- Zayıf yönü:
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Bonus Aşama: Cross Validation ve Basit Hiperparametre Denemeleri

### Hedef

Kişi model skorunun tek bir train-test ayrımına bağımlı olabileceğini fark etsin.

### Bu aşamada yaptırılacaklar

- `cross validation` mantığını öğrensin
- `GridSearchCV` veya çok temel parametre denemeleri yapsın
- Özellikle `KNN` için farklı `k` değerlerini sistemli karşılaştırsın

### Bu aşamada kullanılacak kütüphaneler

- `scikit-learn`
- `pandas`
- `numpy`

### Beklenen çıktı

```md
- Denenen parametreler:
- En iyi parametre:
- Önceki sonuca göre fark:
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Bu Eğitim İçin Hazır Görevler

### Veri temizleme görevleri

- Eksik değer kontrolü yap
- Tekrar eden satırları kontrol et
- Negatif veya mantıksız sayısal değerleri ara
- Kategorik sütunlarda tutarsız yazımları kontrol et

### Temel makine öğrenmesi görevleri

- `X` ve `y` ayrımını yap
- Train ve test verisini ayır
- Kategorik sütunları dönüştür
- Gerekli sayısal sütunları ölçekle

### Model görevleri

- Linear Regression kur
- KNN kur ve farklı `k` değerleri dene
- Decision Tree kur
- Random Forest kur
- Sonuçları tek tabloda karşılaştır

## Sık Yapılan Hatalar

- `salary` sütununu yanlışlıkla giriş değişkenlerine dahil etmek
- Train-test ayrımını model kurduktan sonra yapmak
- Ölçekleme gerektiren modellerde ölçekleme yapmamak
- Tüm veri üzerinde dönüşüm yapıp sonra test ayırmak
- Sadece en yüksek skora bakıp model seçmek
- Overfitting riskini görmezden gelmek

## Eğitim Sonunda Beklenen Kazanımlar

Bu path tamamlandığında kişi:

- Veri temizleme adımlarını sistemli uygular
- Makine öğrenmesinde hedef ve özellik ayrımını yapar
- Train-test ayrımının mantığını anlar
- Kategorik verileri modele hazır hale getirebilir
- Ölçekleme gereksinimini temel düzeyde bilir
- Linear Regression, KNN, Decision Tree ve Random Forest kurabilir
- MAE, RMSE ve R2 ile model kıyaslayabilir
- Hangi modeli neden seçtiğini açıklayabilir

## Eğitmen Notu

Başlangıç seviyesindeki biri için en verimli öğretim sırası şöyledir:

- önce veri temizleme mantığı,
- sonra hedef ve özellik ayrımı,
- sonra train-test yapısı,
- sonra veri hazırlama,
- sonra basit model,
- sonra `KNN`,
- sonra ağaç tabanlı modeller,
- en sonda model karşılaştırma

Bu sıranın temel avantajı, öğrencinin model isimlerini ezberlemek yerine neyi neden yaptığını anlamasıdır.
