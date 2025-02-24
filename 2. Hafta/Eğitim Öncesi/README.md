**1. Print fonksiyonu nedir, ne işe yarar ve parametreleri nelerdir?**

**print() Fonksiyonu Nedir?**
* print() fonksiyonunun görevi ekrana çıktı vermemizi sağlamaktır.
* Metinsel ifadelerde ** veya "" içinde yazılır.


**print() Fonksiyonunun Parametreleri**
*  **sep** <br>
İngilizcede separator(ayırıcı, ayraç) kelimesinin kısaltmasıdır. Dolayısıyla print() fonksiyonundaki bu sep parametresi, ekrana basılarak öğeler arasına hangi karakterin yerleştirileceğini gösterir. Kullanılmasının veya kullanılmamasının pek bir önemi yoktur çünkü görünmese bile oradadır.
*  **end** <br>
Tıpkı sep parametresi gibi end parametresi de print() fonksiyonunda görünmese bile her zaman oradadır. end parametresi ise bu parametrelerin sonuna neyin geleceğini belirler.

**2. Yorum satırları**
* Python programlama dilinde tek satır halinde açıklama satırı eklemek için # işareti, çoklu yorum satırı için 3 tane tek tırnak kullanılır.
* Satırın başı ve sonu arasındaki herhangi bir metin ve kodun Python programlama dili tarafından yok sayılır ve çalıştırılmaz.
* Kodu inceleyen başka yazılımcılar için ipucu vermek için kullanılır. 

**3. Değişkenler ve tanımlama kuralları**
* Değişkenler bir verinin değerini saklamayı sağlar.
* Değişkenler verilerin sonradan değiştirilmesine olanak sağladığı için çok kullanışlıdır.
* Kodlar sırayla çalışır.

* Bir değişken tanımlarken aşağıdaki yapıyı kullanacağız.
```
değişken ismi = atanacak değer
```

**Değişken Tanımlama Kuralları**
* Değişken adlarında sayılar, harfler ya da alt çizgi kullanılabilir ama değişken isimlendirmeleri alt çizgi ya da harfle başlar.
```
1berkcan = 5  Hatalı bir adlandırma
berkcan1 = 5  Doğru bir adlandırma
_berkcan = 5  Doğru bir adlandırma
```
Değişken adlandırırken Türkçe karakter kullanmamaya özen göstermeliyiz.
```
ağırlık = 5  Hatalı kullanım
agirlik = 5  Doğru kullanım
```

* Değişken isimlendirirken boşluk kullanılmaz. Genellikle camelCase adlandırma yaparız<br>
(**camelCase:** ilk kelimenin harfi küçük, ondan sonra gelecek kelimelerin ilk harfi büyük ve bütün kelimeler bitişik kullanımdır)
```
isim soyisim = "Berkcan Gümüşışık"
isimSoyisim = "Berkcan Gümüşışık"
isim_soyisim = "Berkcan Gümüşışık"
```

* Python anahtar kelimeleri kullanılmaz [bknz](https://www.bilgigunlugum.net/prog/python/python_keywords)
* Değişken adlandırılırken rakamla başlayamaz.
* Değişken adları ne çok kısa ne de çok uzun olamlıdır. Aynı zamanda kodu okuyan kişi değişkenin ne için kullanıldığını anlaması gerekir.

**4. Type fonksiyonu**

**5. Sayı veri türleri ve matematiksel işlemler**

**6. String, boolean veri türleri**

**7. Input fonksiyonu**