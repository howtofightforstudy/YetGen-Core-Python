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


<br>

**4. DÖNGÜLER**