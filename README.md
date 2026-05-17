# data-analysis-toolkit (Hatırlatma ve yeni bilgi açıklaması)

loaded_df = None --> Df yüklemek ve diğer tüm alanlar kullanabilmek adına kapsamı global olan bir değişken ilk değeri none daha sonra onu df olarak düzenliyoruz. 

Tüm button fonksiyonlarında laoded_df'e pandas ile yüklenen df kullanarak pandasın sunduğu shape, describe, dtypes, columns gibi özellikleri kullanılmıştır bunlar için yazımları ve düzenlemeleri kullanmak adına for ve print sıkça eklenmiştir. 

to_frame dediğimiz method ise dizi veya sözlük olarak gelen bir yapıyı tabloya çevirir. dtypes bize bir sözlük döndürür bunu rahat görebilmek adına to_frame ekleriz tablo yapması için. 

missing_values yani kayıp değerleri görmek için kullandığımız yöntem biraz kafa karıştırabilir. Burada loaded_df yüklenen df için pandasın sunduğu isnull methodu kullanıyoruz bu bize boş alanlar için True dolu alanlar için False döndürür. Buna ek olarak sum methodu eklediğimizde ise pandas True değerleri 1 False değerleri ise 0 olarak kabul eder ve hepsini toplar. son olarak bize series döndürür. Series değimiz yapı tek boyutlu bir yapıdır bunu tablo yapmak için to_frame methodunu ekleriz. 

yine missing_values de yaptığımız ikinci satırda ise to_frame ile çevirdiğimiz tabloya yeni bir columns yani sutün ekliyoruz. Buradaki amacımız isnull.mean yaparak yani mean ile bize eksik değer oranını vermektedir. ancak bunu 0.5 veya 0.2 gibi değerler ile veriri bunu yüzdeli görmek için 100 ile çarparız. son olarak round dediğimiz method ise oranın virgülden sonraki kısmının uzamaması için virgülden sonra 2 basamak ekletir. 

mean hesaplama mantığını netleştirmek adına ; 

elimizde böyle tablo olsun 

age
25
boş
30
boş

isnull yaptığımızda ise 

False
True
False
True

Pandas bunu şu şekilde hesaplamaktadır ; 

False = 0
True  = 1
False = 0
True  = 1

yanı bu değer 0, 1, 0, 1 olarak görünür. Mean methodunu eklediğimizde ise şu işlemi yapar == "(0 + 1 + 0 + 1) / 4 = 2 / 4 = 0.5" Bu değeri 100 ile çarptığımızda ise 4 satırlık tabloda iki satırın eksik olması %50 eksik değer anlamına gelir. 