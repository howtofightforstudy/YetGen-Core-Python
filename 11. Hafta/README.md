**PANDAS NEDİR?**<br>
- Pandas kütüphanesi ver ianalizi için kullanılan bir kütüphanedir.<br>
- Panel Data'dan gelmektedir.<br>
- Yapısal verilerle çalışmak için kullanılır.<br>
- Veri manipülasyonu ve analizi için yazılmış açık kaynaklı bir Python kütüphanesidir.<br>
- Ekonometrik ve finansal verilerle çalışmak için kullanılır.<br>
- 2008 yılında Wes McKinney tarafından geliştirilmiştir<br>

`pip install pandas` komutu ile pandas kütüphanesi kurabiliriz.<br>

**PANDAS SERİSİ OLUŞTURMA**<br>
1. pd.Series() ile pandas serisi oluşturabiliriz.<br>

```
    import pandas as pd
    import numpy as np
    seri = pd.Series([1,2,3,4,5,6,7,8,9])
    print(seri)
    type(seri)
```
2. .axes ile serinin başlangıç, bitiş ve adım değerlerini (eksen bilgilerini) görebiliriz.<br>

```
    import pandas as pd
    import numpy as np
    seri = pd.Series([1,2,3,4,5,6,7,8,9])   
    print(seri.axes)
```

3. dtype ile serinin veri tipini göerbiliriz.<br>

```
    import pandas as pd
    import numpy as np
    seri = pd.Series([1,2,3,4,5,6,7,8,9])
    print(seri.dtype)
```

4. .size ile serinin boyutunu görebiliriz<br>

```
    import pandas as pd
    import numpy as np
    seri = pd.Series([1,2,3,4,5,6,7,8,9])
    print(seri.size)
```

5. .ndim ile serinin boyut sayısını görebiliriz<br>
```
    import pandas as pd
    import numpy as np
    seri = pd.Series([1,2,3,4,5,6,7,8,9])
    print(seri.ndim)
```

6. .values ile serinin değerlerini görebiliriz.<br>

```
    import pandas as pd
    import numpy as np
    seri = pd.Series([1,2,3,4,5,6,7,8,9])
    print(seri.values)
```

7. .head() ile serinin ilk 5 değerini görebiliriz. Eğer isterseniz .head(10) diyerek ilk 10 değeri görebilirsiniz.<br>

```
    import pandas as pd
    import numpy as np
    seri = pd.Series([1,2,3,4,5,6,7,8,9])
    seri.head()
```

8. .tail() ile serinin son 5 değerini görebiliriz. Eğer isterseniz .tail(10) diyerek son 10 değeri görebilirsiniz.<br>

```
    import pandas as pd
    import numpy as np
    seri = pd.Series([1,2,3,4,5,6,7,8,9])
    seri.tail()
```

**PANDAS DATAFRAME OLUŞTURMA**<br>
*pd.DataFrame()* <br>
- DataFrame oluşturabiliriz.<br>
- columns parametresi ile kolon isimlerini belirleyebiliriz.<br>
- index parametresi ile index isimlerini belirleyebiliriz.<br>

**ELEMAN İŞLEMLERİ**<br>
- df.drop() ile kolon veya satır silme işlemi yapabiliriz.<br>
- axis = 1 ile kolon silme işlemi yapabiliriz.<br>
- axis = 0 ile satır silme işlemi yapabiliriz.<br>
- inplace parametresi ile değişikliği kalıcı kaydetme işlemi yapabiliriz. Diğer durumlarda değişkenlikler geçici olarak kaydedilir<br>

```
    df.drop("c", axis=0) # DataFrame'den b satırını siler
    # geçici olarak siler, kalıcı olarak silmek için inplace=True parametresini kullanabilirsiniz
    df.drop("c", axis=0, inplace=True) # DataFrame'den c satırını kalıcı olarak siler
```

**GÖZLEM ve DEĞİŞKEN SEÇİMİ**<br>

```
    m = np.random.randint(1,30, size = (10,3)) # rastgele 10 satır ve 3 sütunlu bir matris oluşturur
    df = pd.DataFrame(m, columns=["var1", "var2", "var3"]) # DataFrame oluşturur
    df
```

1. LOC<br>
    - Tanımlandığı şekliyle seçim yapmak için kullanılır.<br>

```
    df.loc[0:3] 
    # DataFrame'in 0'dan 3'e kadar olan satırlarını döndürür
```

2. ILOC<br>
    - Alışık olduğumuz indexleme mantığıyla seçim yapmak için kullanılır.<br>

```
    df.iloc[0:3] 
    # DataFrame'in 0'dan 3'e kadar olan satırlarını döndürür, iloc sayısal indeksleme yapar

    df.iloc[:3 , :3] 
    # DataFrame'in ilk 3 satırını ve ilk 3 sütununu döndürür

    df.loc[0:3,"var3"] 
    # DataFrame'in 0'dan 3'e kadar olan satırlarının var3 sütununu döndürür   

    df.iloc[0:3, 0:2] 
    # DataFrame'in 0'dan 3'e kadar olan satırlarının ilk 2 sütununu döndürür
```

**KOŞULLU ELEMAN İŞLEMLERİ**<br>

```
    df[df.var1 >15] 
    #var1 sütunundaki değerleri 15'ten büyük olan satırları döndürür   

    df[df.var1 % 2 == 0] 
    #var1 sütunundaki değerleri 2'ye tam bölünebilen satırları döndürür

    df.loc[(df.var1 > 15) & (df.var2 < 15), "var2"] 
    #var1 sütunundaki değerleri 15'ten büyük ve var2 sütunundaki değerleri 20'den küçük olan satırları döndürür

    df.query("var1 > 15 & var3 < 15")
    #DataFrame'de var1 sütunundaki değerleri 15'ten büyük ve var3 sütunundaki değerleri 20'den küçük olan satırları döndürür
```

**BİRLEŞTİRME (JOIN) İŞLEMLERİ**<br>

```
    df2 = df + 99
    df2
```

- . concat() fonksiyonu ile iki DataFrame'i birleştirebiliriz. `ignore_index` parametresi ile indexleri sıfırlayabiliriz.<br>

- join parametresi ile hangi kolon üzerinden birleştirileceğini belirleyebiliriz.<br>

```
    pd.concat([df, df2])
    #DataFrame'leri birleştirir, df ve df2'yi yan yana ekler

    pd.concat([df, df2], ignore_index=True)
    #DataFrame'leri birleştirir ve index değerlerini sıfırlar

    df2.columns = ["var1", "var2", "var3"] 
    pd.concat([df,df2], join="inner")
    #DataFrame'leri birleştirir ve ortak sütunları alır
```

**İLERİ BİRLEŞTİRME İŞLEMLERİ**<br>

```
    df1 = pd.DataFrame({"Çalışanlar": ["Ali", "Ayşe", "Mehmet", "Fatma"],
                        "Grup": ["Koordinatör","Full Time Çalışan","Eğitim Koordinatörü","İş Geliştirme"]})
    df1

    df2 = pd.DataFrame({"Çalışanlar": ["Ali", "Ayşe", "Mehmet", "Fatma"],
                    "İlk Giriş Yılları": [2021, 2019, 2022, 2018]})
    df2
```

- .merge() fonksiyonu ile birebir birleştirme işlemlerini gerçekleştirebiliriz.<br>
- Merge komutu ile yapılan işlemleri SQL'de bulunan inner join, outer join...'e benzetebiliriz.<br>

```
    pd.merge(df1, df2)
    # DataFrame'leri "Çalışanlar" sütununa göre birleştirir

    pd.merge(df1, df2, on="Çalışanlar")
    # DataFrame'leri "Çalışanlar" sütununa göre birleştirir ve ortak sütunları alır
```

**TOPLULAŞTIRMA VE GRUPLAMA İŞLEMLERİ (AGGREGATION & GROUPING)**<br>

Basit Toplulaştırma İşlemleri<br>

- **count():** Eleman sayısı
- **first(), last():** İlk ve son eleman
- **mean(), median():** Ortalama ve medya
- **min(), max():** Minimum ve maksimum değer
- **std(), var():** Standart sapma ve varyans
- **sum():** Toplam değer

`pip install seaborn` ile kütüphaneyi yükleriz.<br>

```
    import seaborn as sns 
    #seaborn kütüphanesini içe aktarır
    df = sns.load_dataset("planets") 
    #seaborn kütüphanesinden planets veri setini yükler
    df.head()

    df.shape 
    #DataFrame'in boyutlarını döndürür

    df.count() 
    #DataFrame'deki her sütunun kaç tane değer içerdiğini döndürür

    df["mass"].mean() 
    #mass sütununun ortalamasını döndürür

    df["mass"].count() 
    #mass sütunundaki değerlerin sayısını döndürür

    df["mass"].min() 
    #mass sütununun minimum değerini döndürür

    df["mass"].max() 
    #mass sütununun maksimum değerini döndürür

    df["mass"].sum() 
    #mass sütununun toplamını döndürür

    df["mass"].std() 
    #mass sütununun standart sapmasını döndürür

    df["mass"].var() 
    #mass sütununun varyansını döndürür

    df.describe() 
    #DataFrame'in istatistiksel özetini döndürür

    df.describe().T 
    #DataFrame'in istatistiksel özetini transpoze eder

    df.dropna().describe().T 
    #NaN değerleri içermeyen DataFrame'in istatistiksel özetini transpoze eder
```

**GRUPLAMA İŞLEMLERİ (GROUPING)**<br>
Gruplama işlemi veri serinde yer alan kategorik değişkenlerin gruplarının yakalanması ve gruplar özelinde gruplama işlemlerinin yapılması işlemidir.<br>

```
    df = pd.DataFrame({"Gruplar": ["A", "B", "C", "A", "B", "C"],
                   "Veri": [10, 11, 52, 53, 43, 55]})
    df

    df.groupby("Gruplar").mean() 
    #Gruplara göre ortalama değerleri hesaplar

    df.groupby("Gruplar").sum() 
    #Gruplara göre ortalama değerleri hesaplar
```

- .groupby() fonksiyonu ile gruplama işlemleri yapılır.<br>
- sum(), mean(), count(), max(), min() gibi fonksiyonlar ile gruplama işlemleri yapılır.<br>

```
    df = sns.load_dataset("planets") 
    df.head()

    df.groupby("method")["orbital_period"].mean() 
    #method sütununa göre orbital_period sütununun ortalamasını hesaplar 

    df.groupby("method")["year"].describe()
    #method sütununa göre year sütununun istatistiksel özetini döndürür
```

**İLERİ TOPLUMLAŞTIRMA İŞLEMLERİ (ADVANCED AGGREGATION)**<br>
- aggregate() fonksiyonu ile toplulaştırma işlemleri yapılır.<br>

```
    df = pd.DataFrame({
        "Gruplar": ["A", "B", "C", "A", "B", "C"],
        "Değişken1": [10, 11, 33, 22, 11, 99],
        "Değişken2": [100, 252, 333, 262, 111, 969]})
    df

    df.groupby("Gruplar").aggregate(["min",np.median ,"max"])
    #Gruplara göre min, medyan ve max değerleri hesaplar

    df.groupby("Gruplar").aggregate({"Değişken1": "min", "Değişken2": "max"})
    #DataFrame'de gruplara göre minimum ve maksimum değerleri hesaplar
```

- filter() fonksiyonu ile gruplama işlemelrinden sonra gruplar üzerinde filtreleme işlemi yapılır.<br>

```
    def filter_func(x):
    return x["Değişken1"].std() > 9
    df.groupby("Gruplar").filter(filter_func)
    #Gruplara göre Değişken1 sütununun standart sapması 9'd
```

**TRANSFORM**<br>
- Verileri dönüştürmek için kullanılacak işlev.<br>

```
    dfa = df.iloc[:,1:3]  # DataFrame'den 1. ve 2. sütunları seçer
    dfa.transform(lambda x: x - x.mean())
    #DataFrame'deki her sütunun ortalamasını çıkarır
```

- apply() fonksiyonu kullanıcıya istediği bir fonksiyonu her bir değere uygulamasına izin verir.<br>

```
    df.apply(np.sum)
    #DataFrame'deki her sütunun toplamını hesaplar

    df.apply(np.min)
    #DataFrame'deki her sütunun minimum değerini hesaplar

    df.groupby("Gruplar").apply(np.sum)
    #Gruplara göre her sütunun toplamını hesaplar
```

**PİVOT TABLOLAR (PIVOT TABLES)**<br>
- Pivot tablolar, özellikle pandas kütüphanesinde verileri özetlemek, gruplamak ve farklı eksenler üzerinde yeniden düzenlemek için kullanılan güçlü bir araçtır.<br>

```
    import seaborn as sns
    titanic = sns.load_dataset("titanic") # titanic veri setini yükler
    titanic.head()

    age= pd.cut(titanic["age"],[0,18,90]) 
    #age sütununu 0-18 ve 18-90 yaş aralıklarına böler
    titanic.pivot_table("survived",["sex",age],"class") 
    #DataFrame'de cinsiyet ve yaş aralıklarına göre hayatta kalma oranlarını hesaplar
```

**DIŞARIDAN VERİ OKUMA**<br>

```
    ornekcsv = pd.DataFrame({
    "Ad": ["Ali", "Ayşe", "Mehmet"],
    "Soyad": ["Yılmaz", "Demir", "Kara"],
    "Yaş": [25, 30, 22]})
    ornekcsv.to_csv("ornekcsv.csv", sep=";") # DataFrame'i CSV dosyasına kaydeder
    pd.read_csv("ornekcsv.csv",sep=";").head() #CSV dosyasını okur ve ilk 5 satırı gösterir
```