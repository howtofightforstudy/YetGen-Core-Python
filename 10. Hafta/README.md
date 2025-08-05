**NUMPY NEDİR VE NEDEN NUMPY KULLANIYORUZ?**<br>

**NUMPY**<br>
- Numpy sayısal işlemleri hızlı yapmak için C dili ile yazılmış bir Python kütüphanesidir.<br>
- Veri analizinde kullanılır.<br>
- Bilgisayar kurmak için `pip install numpy` komutu ile kurulabilir<br>
- Bilimsel hesaplamalar için kullanılır.<br>
- Arraylar/ Çok boyutlu arrayler ve martisler üzerinden yükdek performanslı işlemler yapılabilir.<br>
- Temelleri 1995 yılında atıldı ama nihai olarak 2005 yılında Travis Oliphant tarafından hayata geçmiştir.<br>
- Listelere benzerdir fakat verimli veri saklama ve vektör işlemleri için Numpy kullanılır.<br>

```
    import numpy as np
    a = np.array([1,2,3,4])
    b = np.array([2,3,4,5])
    print(a+b)
```

**NUMPY FONKSİYONLARI**<br>
1. RESHAPE() FONKSİYONU <br>
.reshape() fonksiyonu ile arraylerin boyutlarını değiştirebiliriz.

```
    import numpy as np

    x = np.array([1,2,3,4,5,6,7,8,9])
    multi = x.reshape(3,3)
    print(multi)
```
<br>

2. SHAPE() FONKSİYONU <br>
.shape() fonksiyonu ile arraylerin boyutlarını öğrenebiliriz.

```
    import numpy as np

    x = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9])
    multi = x.reshape(3, 3)
    print(multi.shape)
```
<br>

3. NDIM() FONKSİYONU<br>
.ndim() fonksiyonu ile arraylerin boyut sayısını öğrenebiliriz.

```
    import numpy as np

    x = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9])
    multi = x.reshape(3, 3)
    print(x.ndim) #tek boyutlu ndim
    print(multi.ndim) #iki boyutlu ndim
```

**BİRLEŞTİRME (CONCATENATION) FONKSİYONU**<br>
.concatenate() fonksiyonu ile birleştirme yapabiliriz.<br>
- - axis = 0 satır bazında birleştirme yapar.<br>
- - axis = 1 sütun bazında birleştirme yapar.<br>

```
    import numpy as np
    x = np.array([1,2,3,4,5])
    y = np.array([6,7,8,9,10])
    print(np.concatenate([x, y]))

    z = np.array([11,12,13,14,15])
    print(np.concatenate([x, y, z]))

    a = np.array([[1,2,3],[4,5,6]])
    print(np.concatenate([a, a]))

    print(np.concatenate([a, a], axis=1))  # sütun bazında birleştirme
    print(np.concatenate([a, a], axis=0))  # satır bazında birleştirme
```

**ARRAY AYIRMA (SPLITTING)**<br>
1. .split() fonksiyonu ile array ayırma yapabiliriz.<br>

```
    import numpy as np
    n = np.array([1,2,3,99,99,3,2,1])
    print(np.split(n, [3,5]))
    #0-1-2 alır sonra 3-4 alır ve 5-6-7 alır

    a,b,c = np.split(n, [3,5])
    print(a)
    print(b)
    print(c)
```

2. .vsplit() fonksiyonu ile arrayde yatay olarak ayırma yapabiliriz<br>

```
    import numpy as np
    #.arange(16) ile 0'dan 16'ya kadar sayıları oluşturur
    n = np.arange(16).reshape(4, 4)
    np.vsplit(n, [2])
```

3. .hsplit() fonksiyonu ile arrayde dikey olarak ayırma yapabiliriz<br>

```
    import numpy as np
    #.arange(16) ile 0'dan 16'ya kadar sayıları oluşturur
    n = np.arange(16).reshape(4, 4)
    np.hsplit(n, [2])
```

4. np.arange()
- - Belli bir aralıkta sayıları oluşturmak için kullanılır<br>
`np.arange(start, stop, step)`

```
    import numpy as np
    np.arange(3,12,2) 
    #3'ten 12'ye kadar 2'şer artarak sayıları oluşturur
```

5. np.zeros()
- - 0'lardan oluşan bir numpy dizisi oluşturmulması için kullanılır<br>

```
    import numpy as np
    np.zeros(5)  
    # 5 tane sıfırdan oluşan bir dizi oluşturur
```

6. np.ones()
- - 1'lerden oluşan bir numpy dizisi oluşturulması için kullanılır.<br>

```
    import numpy as np
    np.zeros(5)  
    # 5 tane sıfırdan oluşan bir dizi oluşturur
```

7. np.linspace()
- - Belli bir aralıkta sayıları oluşturmak için kullanılır.<br>
- - np.linspace(başlangıç, bitiş, bölünecek aralık)

```
    import numpy as np
    np.linspace(0, 100, 5)
    # 0 ile 100 arasında 5 eşit parçaya bölünmüş sayılar oluştur
```

```
    import numpy as np
    np.random.randint(0,10,3)
    # 0 ile 10 arasında 3 adet rastgele tamsayı oluşturur
```

```   
    import numpy as np
    np.random.randint(2,22,5)
    # 2 ile 22 arasında 5 adet rastgele tamsayı oluşturur
```

**NUMPY ARRAY'IN ÖZELLİKLERİ**<br>
- ndim : Boyut sayısı<br>
- shape: Boyut bilgisi<br>
- size: Toplam eleman sayısı<br>
- dtype: Veri tipi<br>

```
    import numpy as np
    a = np.random.randint(10,size = 10)
    print(a.ndim)
    # a.ndim ile dizinin boyut sayısını (ndim) yazdırır
    print(a.shape)      
    # a.shape ile dizinin boyutlarını (shape) yazdırır
    print(a.size)   
    # a.size ile dizinin toplam eleman sayısını (size) yazdırır
    print(a.dtype) 
    # a.dtype ile dizinin veri tipini (dtype) yazdırır
```

**ARRAY SIRALAMA (SORTING)**<br>
Array sıralama işlemleri yapmak için numpy kütüphanesinde yer alan sort() fonksiyonu kullanılır.<br>

```
    import numpy as np
    v = np.array([8,24,232,12,5,42,55])
    v.sort()
    print(v)
```

**INDEX İLE ELEMANLARA ERİŞMEK**<br>
Aynı listelerde olduğu gibi index ile elemanlara erişebiliriz.<br>

```
    import numpy as np
    a = np.random.randint(10, size=10)
    print(a[0]) # a dizisinin ilk elemanını yazdırır
    print(a[-1]) # a dizisinin son elemanını yazdırır
    a[0] = 100 
    print(a)

    # 3 satır ve 5 sütundan oluşan rastgele bir matris oluşturur
    x = np.random.randint(10, size=(3,5)) 
    print(x)
    print(x[0, 0]) # x matrisinin ilk satır ve ilk sütun elemanını yazdırır
```

**SLICING İLE ELEMANLARA ERİŞMEK (ARRAY ALT KÜMESİNE ERİŞMEK)**<br>

```
    import numpy as np
    a = np.arange(20,30)
    print(a)

    print(a[0:3]) # a dizisinin ilk üç elemanını yazdırır
    print(a[:3])  # a dizisinin ilk üç elemanını yazdırır
    print(a[3:])  # a dizisinin dördüncü elemanından sonrasını yazdırır
    print(a[3::6])  # a dizisinin dördüncü elemanından başlayarak her altıncı elemanını yazdırır
    print(a[::2]) # a dizisinin her ikinci elemanını yazdırır
    print(a[::-1]) # a dizisini ters çevirir
    print(a[1:8:2]) # a dizisinin ikinci elemanından başlayarak

    b = np.random.randint(10, size=(5,5))
    print(b)
    print(b[:,0]) # b matrisinin tüm satırlarını ve ilk sütununu yazdırır
    print(b[0,:]) # b matrisinin ilk satırını ve tüm sütunlarını yazdırır
    print(b[0:2,0:3]) # b matrisinin ilk iki satırını ve ilk üç sütununu yazdırır
    print(b[::2, ::2]) # b matrisinin her ikinci satırını ve her ikinci sütununu yazdırır
```

**ALT KÜME ÜZERİNDE İŞLEM YAPMAK**<br>

```
    import numpy as np
    b = np.random.randint(10, size=(5,5))
    alt_b = b[0:2, 0:3]  # b matrisinin ilk iki satırını ve ilk üç sütununu alır
    alt_b

    alt_b[0,0] = 100  # alt_b matrisinin ilk satır ve ilk sütun elemanını 100 olarak günceller
    alt_b
```

**FANCY INDEX**<br>
Bir liste içine bu arrayden istediğimiz indislerini koyarak o indislerdeki verileri alabiliriz.<br>

```
    import numpy as np
    v = np.arange(0,30,3) # 0'dan 30'a kadar 3'er artan bir dizi oluşturur
    print(v)

    yetgen = [1,3,5]
    print(v[yetgen]) # v dizisinin 1, 3 ve 5 indekslerindeki elemanlarını yazdırır

    n = np.arange(9).reshape(3,3)
    satir = np.array([0,1])
    sutun = np.array([0,2])
    print(n[satir, sutun])  # n matrisinin 0. ve 1. satırlarının 0. ve 2. sütun elemanlarını yazdırır
```

**KOŞULLU ELEMAN İŞLEMLERİ**<br>

```
    v = np.array([1,2,3,4,5])
    print(v > 3)  # v dizisindeki elemanların 3'ten büyük olup olmadığını kontrol eder ve True/False değerlerini yazdırır
    print(v[v > 3])  # v dizisindeki 3'ten büyük elemanları yazdırır
    print(v[v < 3])  # v dizisindeki 3'ten küçük elemanları yazdırır
    print(v[v == 3])  # v dizisindeki 3'e eşit elemanları yazdırır
    print(v[v != 3])  # v dizisindeki 3'e eşit olmayan elemanları yazdırır
    print(v[v >= 3])  # v dizisindeki 3'e eşit veya daha büyük elemanları yazdırır
    print(v[v <= 3])  # v dizisindeki 3'e eşit veya daha küçük elemanları yazdırır
```

**MATEMATİKSEL İŞLEMLER**<br>

```
    v = np.array([1,2,3,4,5])
    print(v*2) # v dizisini 2 ile çarpar
    print(v + 2)  # v dizisine 2 ekler
    print(v - 2)  # v dizisinden 2 çıkarır      
    print(v / 2)  # v dizisini 2'ye böler
    print(v ** 2)  # v dizisinin her elemanını karesini al
    print(np.subtract(v, 2))  # v dizisinden 2 çıkarır
    print(np.add(v, 2))  # v dizisine 2 ekler   
    print(np.multiply(v, 2))  # v dizisini 2 ile çarpar
    print(np.divide(v, 2))  # v dizisini 2'ye böler
    print(np.power(v, 2))  # v dizisinin her elemanının karesini alır  
    print(np.sqrt(v))  # v dizisinin her elemanının karekökünü alır
    print(np.exp(v))  # v dizisinin her elemanının e üzeri değerini alır
    print(np.mod(v, 2))  # v dizisinin her elemanının 2 ile bölümünden kalanı alır
    print(np.abs(v))  # v dizisinin her elemanının mutlak değerini alır
    print(np.absolute(v))  # v dizisinin her elemanının mutlak değerini alır
    print(np.floor(v))  # v dizisinin her elemanının alt tamsayısını alır
    print(np.ceil(v))  # v dizisinin her elemanının üst tamsayısını alır
    print(np.round(v))  # v dizisinin her elemanını en yakın tamsayıya yuvarlar
    print(np.clip(v, 2, 4))  # v dizisinin her elemanını 2 ile 4 arasında sınırlar 
```

**İKİ BİLİNMEYENLİ DENKLEM ÇÖZÜMÜ**<br>

```
    import numpy as np
    A = np.array([[2, 3], [1, 2]])
    B = np.array([8, 5])
    x = np.linalg.solve(A, B)  # A matrisini ve B vektörünü kullanarak x ve y'yi çözer
    print(x) 
```