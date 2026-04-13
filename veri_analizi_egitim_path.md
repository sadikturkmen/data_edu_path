# Job Salary Prediction Dataset ile Veri İnceleme, Analiz ve Görselleştirme Eğitim Path'i

## Amaç

Bu eğitim path'inin amacı, veri incelemeyi, veri analizini ve veri görselleştirmeyi hiç bilmeyen bir kişinin `job_salary_prediction_dataset.csv` veri seti üzerinden adım adım ilerleyerek temel veri okuryazarlığı kazanmasını sağlamaktır.

Bu path, kişiyi doğrudan ileri seviye modellere götürmek yerine önce şu üç yetkinliği sağlamlaştırır:

1. Veriyi tanıma ve doğru sorular sorma
2. Veriyi temizce inceleme ve anlamlandırma
3. Bulguları grafiklerle anlatabilme

Bu veri seti bu eğitim için uygundur çünkü:

- Satır sayısı yüksektir ve gerçek veri hissi verir
- Sayısal ve kategorik sütunları birlikte içerir
- Maaş (`salary`) gibi net bir hedef değişken içerir
- İş unvanı, eğitim, tecrübe, sektör, lokasyon ve uzaktan çalışma gibi analiz için güçlü boyutlara sahiptir

## Veri Seti Özeti

Bu veri setinde toplam `250000` satır ve `10` sütun vardır.

Sütunlar:

- `job_title`
- `experience_years`
- `education_level`
- `skills_count`
- `industry`
- `company_size`
- `location`
- `remote_work`
- `certifications`
- `salary`

Bu veri setinde ilk incelemeye göre eksik değer görünmemektedir. Bu, başlangıç seviyesi bir öğrenci için iyi bir avantajdır; çünkü eğitim ilk etapta eksik veri tamamlama zorluğuna değil, veri okuma ve yorumlama becerisine odaklanabilir.

## Bu Eğitimde İzlenecek En Verimli Yol

Başlangıç seviyesindeki biri için en verimli yol aşağıdaki sıradır:

1. Önce veriyi sadece görmek ve sütunları anlamak
2. Sonra temel tablo inceleme komutlarını öğrenmek
3. Ardından sayısal ve kategorik sütunları ayrı ayrı analiz etmek
4. Daha sonra maaşı etkileyebilecek ilişkileri görselleştirmek
5. Son aşamada analiz sonuçlarını kısa bir hikayeye dönüştürmek

Bu sıranın önemli nedeni şudur:

- Temizlik ve teknik detaylara çok erken girilirse kişi motivasyon kaybeder
- Grafiklere çok erken geçilirse grafik yorumlama ezbere dönüşür
- Modellemeye çok erken geçilirse veri anlama becerisi zayıf kalır

Bu yüzden bu eğitimde önce analiz düşüncesi, sonra görsel anlatım, en sonda isterse bonus olarak tahminleme adımı vardır.

## Önerilen Çalışma Formatı

Bu eğitim için önerilen çıktı yapısı:

- `01_veriyi_tanima.ipynb`
- `02_veri_inceleme.ipynb`
- `03_temel_analiz.ipynb`
- `04_gorsellestirme.ipynb`
- `05_sonuclari_yorumlama.md`

Eğer notebook kullanılmayacaksa aynı yapı tek bir `.md` veya `.docx` raporla da ilerletilebilir. Ancak öğrenme açısından notebook düzeni daha verimlidir.

## Bu Eğitimde Kullanılacak Temel Kütüphaneler

- `pandas`: Veri okuma, tablo inceleme, filtreleme ve özetleme
- `numpy`: Sayısal işlemler, temel hesaplamalar ve dizi mantığı
- `matplotlib`: Temel grafik çizimi
- `seaborn`: Daha kolay ve daha okunabilir istatistiksel görselleştirmeler

Not:

- Bu path'te en kritik kütüphane `pandas` olacaktır
- Grafik tarafında başlangıç için `matplotlib` + `seaborn` birlikte kullanmak yeterlidir
- `numpy` her aşamada yoğun görünmeyebilir ama veri analizi mantığını güçlendirir

## Aşama 1: Veri Setini Sadece Tanıma

### Hedef

Kişi önce veri setini korkmadan açabilsin ve her sütunun ne anlattığını kendi cümlesiyle ifade edebilsin.

### Bu aşamada yaptırılacaklar

- CSV dosyasını açsın
- İlk 20 satıra baksın
- Sütun isimlerini tek tek yazsın
- Her sütunun ne anlattığını kendi cümlesiyle açıklasın
- Hangi sütunların sayısal, hangilerinin kategorik olduğunu ayırsın
- Hedef değişkenin neden `salary` olduğunu açıklasın

### Bu veri seti için özellikle fark etmesi gerekenler

- `salary` sayısal hedef değişkendir
- `experience_years`, `skills_count`, `certifications` doğrudan ölçülebilir sayısal değişkenlerdir
- `job_title`, `education_level`, `industry`, `company_size`, `location`, `remote_work` kategorik değişkenlerdir

### Bu aşamada kullanılacak kütüphaneler

- `pandas`

### Beklenen çıktı

Öğrenci bu aşamanın sonunda veri sözlüğü benzeri kısa bir açıklama hazırlasın.

Örnek çıktı formatı:

```md
- job_title: Kişinin iş unvanını gösterir
- experience_years: Kişinin toplam deneyim yılını gösterir
- salary: Tahmin etmek veya analiz etmek istediğimiz maaş bilgisidir
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 2: Temel Veri İnceleme Komutlarını Öğrenme

### Hedef

Kişi bir veri setine bakarken ilk hangi komutları çalıştırması gerektiğini öğrensin.

### Bu aşamada yaptırılacaklar

- Veri setinin satır ve sütun sayısını bulsun
- İlk 5 ve son 5 satırı görüntülesin
- Sütun tiplerini kontrol etsin
- Sayısal sütunlar için özet istatistik çıkarsın
- Her sütunda kaç farklı değer olduğunu bulsun

### Öğrenmesi gereken temel kavramlar

- `shape`
- `head`
- `tail`
- `info`
- `describe`
- `nunique`

### Bu veri seti için yorumlaması gereken noktalar

- Veri seti büyük olduğu için örnek satırlara bakmak önemlidir
- `salary` sütununda çok fazla farklı değer olacaktır
- Bazı kategorik sütunlarda sınıf sayısı düşüktür, bu da grafik üretmeyi kolaylaştırır

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `numpy`

### Beklenen çıktı

Kısa bir özet metni:

```md
Bu veri setinde X satır ve Y sütun vardır.
Sayısal sütunlar şunlardır: ...
Kategorik sütunlar şunlardır: ...
En çok farklı değere sahip sütun: ...
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 3: Veri Kalitesi Kontrolü

### Hedef

Kişi veriyi analiz etmeden önce temel kalite kontrollerini alışkanlık haline getirsin.

### Bu aşamada yaptırılacaklar

- Eksik değer var mı kontrol etsin
- Tekrarlayan satır var mı kontrol etsin
- Sayısal sütunlarda mantıksız değer var mı baksın
- Kategorik sütunlarda yazım tutarsızlığı var mı kontrol etsin

### Bu veri seti için özel kontrol noktaları

- `experience_years` negatif olmamalı
- `salary` sıfır veya negatif olmamalı
- `skills_count` ve `certifications` mantıklı aralıklarda mı bakılmalı
- `remote_work` sütununda beklenen değerlerin tutarlı olup olmadığı incelenmeli
- `education_level` seviyeleri tutarlı isimlerle mi yazılmış bakılmalı

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `numpy`

### Beklenen çıktı

Öğrenci şu başlıklarla kısa bir kontrol notu hazırlasın:

```md
## Veri Kalitesi Sonucu

- Eksik değer durumu:
- Tekrar eden satır durumu:
- Şüpheli değer var mı:
- Analize başlamadan önce yapılacak düzeltme var mı:
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 4: Tek Değişkenli Analiz

### Hedef

Kişi her sütunu tek başına incelemeyi öğrensin.

### Bu aşamada yaptırılacaklar

- `salary` dağılımını inceletsin
- `experience_years` dağılımını inceletsin
- `skills_count` dağılımını inceletsin
- `certifications` dağılımını inceletsin
- Kategorik sütunlar için frekans tabloları oluştursun

### Kullanılması gereken grafikler

- Histogram
- Boxplot
- Countplot / bar chart

### Bu veri seti için sorulacak sorular

- En sık görülen iş unvanı hangisi?
- En sık görülen eğitim seviyesi hangisi?
- Maaş dağılımı dengeli mi, sağa çarpık mı?
- Tecrübe yılı düşük seviyelerde mi yoğunlaşıyor?

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `matplotlib`
- `seaborn`

### Beklenen çıktı

Her sütun için şu formatta kısa yorum yazsın:

```md
### salary
- Dağılımın genel yapısı:
- Aykırı değer şüphesi:
- En dikkat çeken nokta:
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 5: Maaş Merkezli Temel Analiz

### Hedef

Kişi artık tüm incelemeyi `salary` etrafında yapmayı öğrensin.

### Bu aşamada yaptırılacaklar

- Maaşın ortalamasını, medyanını, minimumunu ve maksimumunu çıkarsın
- En yüksek ortalama maaşa sahip iş unvanlarını bulsun
- Eğitim seviyesine göre ortalama maaşı hesaplasın
- Uzaktan çalışma durumuna göre maaş farkını incelesin
- Şirket büyüklüğüne göre maaş değişimini incelesin

### Bu veri seti için cevaplaması gereken temel sorular

- En yüksek maaş hangi iş unvanlarında görülüyor?
- Tecrübe arttıkça maaş gerçekten artıyor mu?
- Eğitim seviyesi yükseldikçe maaş artıyor mu?
- `remote_work` türleri arasında maaş farkı var mı?
- Büyük şirketlerde maaş daha yüksek mi?

### Kullanılması gereken grafikler

- Ortalama maaş için sıralı bar chart
- Kategoriye göre boxplot
- Grouped bar chart

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`

### Beklenen çıktı

Kişi bu aşamada maaşı etkileyen en az 5 gözlem yazsın.

Örnek:

```md
- Ortalama maaş en yüksek olan iş unvanları ...
- PhD grubunun maaş seviyesi ...
- Hybrid çalışanların maaşı ...
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 6: İlişki Analizi

### Hedef

Kişi iki değişken arasındaki ilişkiyi incelemeyi öğrensin.

### Bu aşamada yaptırılacaklar

- `experience_years` ile `salary` ilişkisini inceletsin
- `skills_count` ile `salary` ilişkisini inceletsin
- `certifications` ile `salary` ilişkisini inceletsin
- Sayısal sütunlar arasında korelasyon matrisi oluştursun

### Kullanılması gereken grafikler

- Scatter plot
- Line plot
- Heatmap

### Bu veri seti için kritik yorum soruları

- Deneyim ile maaş arasında doğrusal bir ilişki var mı?
- Beceri sayısı arttıkça maaş düzenli mi artıyor?
- Sertifika sayısı tek başına güçlü bir gösterge mi?
- Hangi sayısal değişken maaşla en güçlü ilişkiye sahip?

### Öğrenciye özellikle söylenecek nokta

Korelasyon görmek, nedensellik kanıtlamak değildir. Bu fark özellikle bu aşamada vurgulanmalıdır.

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`

### Beklenen çıktı

Kişi en az 3 ilişki yorumu yazsın:

```md
- experience_years ile salary arasında ...
- skills_count ile salary arasında ...
- certifications ile salary arasında ...
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 7: Segment Bazlı Analiz

### Hedef

Kişi tek bir boyuta bakmak yerine alt kırılımlar üzerinden düşünmeyi öğrensin.

### Bu aşamada yaptırılacaklar

- `industry` bazında maaş karşılaştırması yaptırsın
- `location` bazında maaş karşılaştırması yaptırsın
- `job_title + education_level` kombinasyonuna göre analiz yaptırsın
- `industry + remote_work` kombinasyonunda maaş farkına baktırın
- `company_size + experience_years` birlikte düşünüldüğünde maaşın nasıl değiştiğini inceletsin

### Kullanılması gereken yapılar

- Pivot table
- Groupby
- Çoklu kırılım tabloları
- Isı haritası veya sıralı bar grafikler

### Bu veri seti için güçlü analiz örnekleri

- Aynı iş unvanında eğitim seviyesi arttıkça maaş nasıl değişiyor?
- Aynı sektörde remote çalışma şekline göre maaş farkı oluşuyor mu?
- Bazı lokasyonlarda belirli iş unvanları daha mı yüksek maaş alıyor?

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`

### Beklenen çıktı

Kişi bu aşamada en az 3 segment içgörüsü çıkarsın.

Örnek:

```md
- Teknoloji sektöründe hybrid çalışanların maaşı ...
- Belirli lokasyonlarda Data Analyst maaşı ...
- Büyük şirketlerde deneyim etkisi ...
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 8: Görselleştirme Kalitesini Geliştirme

### Hedef

Kişi sadece grafik üretmesin; okunabilir, açıklayıcı ve düzenli grafik hazırlamayı öğrensin.

### Bu aşamada yaptırılacaklar

- Grafik başlıklarını anlamlı yazsın
- Eksen isimlerini açık yazsın
- Para birimini ve sayı formatını okunabilir hale getirsin
- En önemli kategorileri sıralı göstersin
- Aynı raporda renk kullanımını tutarlı yapsın
- Gereksiz grafiklerden kaçınsın

### Bu aşamada öğretilmesi gereken kurallar

- Her grafik bir soruya cevap vermeli
- Çok fazla kategori tek grafikte gösterilmemeli
- Ortalama ve medyan gerektiğinde birlikte düşünülmeli
- Boxplot ile aykırı değerler gözden kaçırılmamalı
- Büyük veri setinde grafikler sade tutulmalı

### Bu aşamada kullanılacak kütüphaneler

- `matplotlib`
- `seaborn`
- `pandas`

### Beklenen çıktı

Öğrenci önce kötü bir grafik hazırlasın, sonra onu daha okunabilir hale getirsin. Böylece görselleştirme kalitesinin neden önemli olduğunu deneyimleyerek öğrensin.

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 9: Analiz Sonuçlarını Hikayeye Dönüştürme

### Hedef

Kişi sadece tablo ve grafik üretmekle kalmasın; sonucu anlatmayı da öğrensin.

### Bu aşamada yaptırılacaklar

- En önemli 5 bulguyu seçsin
- Her bulgu için hangi grafikle desteklediğini yazsın
- Sonuçları teknik olmayan birine anlatır gibi özetlesin
- “Bu veri bize ne söylüyor?” sorusuna kısa cevap versin

### Bu veri seti için yazdırılabilecek örnek başlıklar

- Maaşı en çok etkileyen görünen faktörler
- Eğitim ve deneyimin maaşa etkisi
- Sektör ve lokasyon farklarının etkisi
- Uzaktan çalışma modelinin maaşla ilişkisi

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `matplotlib`
- `seaborn`

### Beklenen çıktı

Kısa bir mini rapor:

```md
## Sonuç Özeti

1. ...
2. ...
3. ...

## Öneri

- Eğer maaş analizine yeni başlanıyorsa önce ...
- Eğer yöneticiye sunum yapılacaksa ...
```

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Aşama 10: Final Projesi

### Hedef

Kişi öğrendiği tüm adımları kendi başına tamamlayabildiğini göstersin.

### Final projede yapılacaklar

- Veri setini yüklesin
- Veri sözlüğü oluştursun
- Veri kalitesi kontrolü yapsın
- En az 5 temel istatistik çıkarsın
- En az 8 grafik üretsin
- En az 10 bulgu yazsın
- En az 1 sayfalık sonuç raporu hazırlasın

### Final proje teslim formatı

- Notebook veya script
- Grafik çıktıları
- Kısa sonuç raporu

### Final proje değerlendirme kriterleri

- Veriyi gerçekten anlamış mı?
- Grafikler doğru seçilmiş mi?
- Yorumlar grafiklerle tutarlı mı?
- Maaş odaklı düşünce kurulmuş mu?
- Sonuçlar açık ve sade anlatılmış mı?

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Bonus Aşama: İsterse Basit Maaş Tahmini

### Hedef

Kişi temel analiz tamamlandıktan sonra veri bilimi tarafına kontrollü şekilde adım atsın.

### Bu aşamaya ne zaman geçilmeli

Sadece önceki aşamalar tamamlandıktan sonra geçilmelidir. Veri analizi temeli oturmadan modelleme aşamasına geçmek önerilmez.

### Bu aşamada yaptırılacaklar

- Kategorik verilerin modele nasıl hazırlanacağını öğrensin
- Eğitim ve test ayrımını öğrensin
- Basit bir regresyon modeli kursun
- Model performansını temel metriklerle yorumlasın

### Özellikle vurgulanması gereken nokta

Bu bonus aşamanın amacı en iyi modeli kurmak değil, analiz ile tahminleme arasındaki farkı göstermektir.

### Bu aşamada kullanılacak kütüphaneler

- `pandas`
- `numpy`
- `scikit-learn`
- `matplotlib`
- `seaborn`

### Öğrenme kaynakları

- İnternet sitesi linki:
- YouTube eğitim videosu:

## Bu Veri Seti İçin Hazır Analiz Soruları

Bu bölüm, eğitimi verirken doğrudan görev olarak kullanılabilir.

### Başlangıç seviyesi görevler

- Veri setindeki sütunları sayısal ve kategorik olarak ayır
- Maaşın temel istatistiklerini çıkar
- En sık görülen 5 iş unvanını bul
- En sık görülen 5 lokasyonu bul
- Maaş dağılımını histogram ile göster

### Orta seviye görevler

- İş unvanına göre ortalama maaşları sırala
- Eğitim seviyesine göre medyan maaşı karşılaştır
- Remote çalışma tipine göre maaş farkını boxplot ile göster
- Tecrübe yılı ile maaş arasındaki ilişkiyi görselleştir
- Beceri sayısı ile maaş arasındaki ilişkiyi yorumla

### İleri başlangıç görevleri

- Sektör ve iş unvanını birlikte kullanarak maaş analizi yap
- Lokasyon ve remote çalışma tipini birlikte karşılaştır
- En yüksek maaşlı 3 segmenti bul
- En dengeli ve en değişken maaş dağılımına sahip kategorileri belirle

## Eğitimi Uygularken Dikkat Edilecek Kurallar

- İlk gün grafik ezberletilmemeli, önce veri mantığı anlatılmalı
- Öğrenciye her adımda “Bu sütun bize ne anlatıyor?” sorusu sorulmalı
- Yorum yazdırmadan yeni aşamaya geçilmemeli
- Her grafik için mutlaka kısa açıklama istenmeli
- Sadece kod yazması değil, çıktı yorumlaması da değerlendirilmelidir

## Sık Yapılan Hatalar

- Sadece kod çalıştırıp sonucu yorumlamamak
- Ortalama ile medyan farkını görmezden gelmek
- Kategorik değişkenlerde sıralama yapmadan grafik üretmek
- Çok fazla kategoriyi tek grafikte göstermeye çalışmak
- Korelasyonu doğrudan neden-sonuç gibi yorumlamak
- Veri temizliği kontrolünü atlamak

## Eğitim Sonunda Beklenen Kazanımlar

Bu path tamamlandığında kişi:

- Bir CSV veri setini açıp okuyabilir
- Sütun türlerini ayırt edebilir
- Temel veri inceleme adımlarını uygulayabilir
- Sayısal ve kategorik analiz yapabilir
- Temel görselleştirmeler üretebilir
- Maaş odağında anlamlı içgörüler çıkarabilir
- Sonuçları kısa rapor halinde sunabilir

## Eğitmen Notu

Bu veri setiyle en doğru öğretim yaklaşımı:

- önce veri tanıma,
- sonra temel inceleme,
- sonra maaş odaklı analiz,
- sonra ilişki ve segment analizi,
- en sonda hikayeleştirme

şeklindedir.

Eğer öğrenci tamamen sıfır seviyedeyse, ilk hedef teknik mükemmellik değil; veriyle rahat ilişki kurmasını sağlamaktır.
