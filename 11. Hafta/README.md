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
