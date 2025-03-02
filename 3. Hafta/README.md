**1. KARŞILAŞTIRMA OPERATÖRLERİ**

* = atama operatörüdür (mesela x=5 dersek x değerini 5'e atmaış oluyoruz)
* == iki değerin birbirine eşit olup olmadığını kontrol eder. Eşitse true, eşit değilse false değerini döndürür
* != eşit değil mi?
cevap eşit değilse true, eşitse false değerini döndürür
* < küçüktür, > büyüktür
* <= küçük eşittir, >= büyük eşittir
<br>

**2. MANTIKSAL OPERATÖRLER**

**And Operatörü**
<br>Her iki durumda eğer doğruysa true değerini döndürür, diğer durumlarda hep false değerini döndürür

* true and tue = true
* true and false = false
* false and true = false
* false and false = false

**Or Operatörü**
<br>Yalnızca 2 durumun yanlış olduğu zaman False, diğer her durumda true değer verir

* true or true = true 
* true or false = true
* false or true = true
* false or false = false

**Not Operatörü**
<br>true değerini false, false için true döndürür
<br>

**3. KARAR YAPILARI**

* Eğer if bloğu doğruysa diğer durumlara bakılmaz ve if bloğu altındaki kodlar çalışır
* else yapısının kullanılması zorunlu değildir, olsa da olur olmasada olur
* elif yapıısnın kullanılması zorunlu değildir, olsa da olur olmasada olur
* else yapısı if ve varsa elif yapısının false olduğu durumda ikinci nihai durum oalrak çalışır
* elif yapısına birden çok farklı koşullardan doğacak durumların kontrolünü sağlamak için kullanırız

```
if kosul:
    # koşul doğruysa çalışacak kodlar
elif kosul2:
    # koşul2 doğruysa calışacak kodlar
else:
    # koşul ve koşul2 yanlışsa çalışacak kodlar
```
**In operatörü**
<br>Belirtilen bir değerin, dizi, metin liste veya demet gibi bir dizinin ögesi olup olmadığını kontrol eder. True ya da false değer döndürür.<br>
Küçük-büyük harf duyarlılığı vardır.

<br>

**4. DÖNGÜLER**
* Döngüler, temel olarak verilen koşullar karşılanana kadar devam eden tekrar eden bir süreçtir.
* Döngünün koşulu her zaman doğruysa döngü sonsuza kadar devam eder. Buna da *"sonsuz döngü"* denir. Bu tür döngülere genellikle while döngüsünde rastlarız.
* Eğer bir döngünün koşulu baştan yanlışsa, bu nedenle döngünün çalışmasına izin vermez. Sonra buna *"sıfır açma döngü"* denir.

**For Döngüsü**
<br>Listelerin, demetlerin, stringlerin ve hatta sözcüklerin üzerinde dolaşmamızı sağlayan bir döngü türüdür.
<br>
Yapısı şu şekildedir:
```
for eleman in veriYapisi:
    yapılacak işlemler
```

**While Döngüsü**
<br>Belli bir koşul sağladığı sürece bloğundaki işlemleri gerçekleştirmeye devam eder. While döngülerinin sona ermesi için koşul durumunun bir süre sonra False olması gereklidir.
<br>
Yapısı şu şekildedir:
```
while kosul:
    yapılacak işlemler
```

**range() Fonksiyonu**
<br>Belirli bir aralıktaki sayıları üretmek için kullanılır.

**range(stop):** 0'dan stop değerine kadar (hariç) sayı üretir.
**range(start, stop):** start değerinden başlayarak stop değerine kadar (hariç) sayı üretir.
**range(start, stop, step):** start'tan başlayarak step kadar artarak stop değerine kadar (hariç) sayı üretir.
<br>
```
print(list(range(5)))       # [0, 1, 2, 3, 4]
print(list(range(2, 6)))    # [2, 3, 4, 5]
print(list(range(1, 10, 2))) # [1, 3, 5, 7, 9]
```

**Break**
<br>Döngüyü sonlandırır.

**Continue**
<br>Döngünün sonraki adımına geçer.