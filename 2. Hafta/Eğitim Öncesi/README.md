**1. PRINT FONKSİYONU NEDİR, NE İŞE YARAR VE PARAMETRELERİ NELERDİR?**

**PRINT() FONKSİYONU NEDİR?**
* print() fonksiyonunun görevi ekrana çıktı vermemizi sağlamaktır.
* Metinsel ifadelerde ** veya "" içinde yazılır.


**PRINT() FONKSİYONUNUN PARAMETRELERİ**
*  **sep** <br>
İngilizcede separator(ayırıcı, ayraç) kelimesinin kısaltmasıdır. Dolayısıyla print() fonksiyonundaki bu sep parametresi, ekrana basılarak öğeler arasına hangi karakterin yerleştirileceğini gösterir. Kullanılmasının veya kullanılmamasının pek bir önemi yoktur çünkü görünmese bile oradadır.
*  **end** <br>
Tıpkı sep parametresi gibi end parametresi de print() fonksiyonunda görünmese bile her zaman oradadır. end parametresi ise bu parametrelerin sonuna neyin geleceğini belirler.

**2. YORUM SATIRLARI**
* Python programlama dilinde tek satır halinde açıklama satırı eklemek için # işareti, çoklu yorum satırı için 3 tane tek tırnak kullanılır.
* Satırın başı ve sonu arasındaki herhangi bir metin ve kodun Python programlama dili tarafından yok sayılır ve çalıştırılmaz.
* Kodu inceleyen başka yazılımcılar için ipucu vermek için kullanılır. 

**3. DEĞİŞKENLER VE TANIMLAMA KURALLARI**
* Değişkenler bir verinin değerini saklamayı sağlar.
* Değişkenler verilerin sonradan değiştirilmesine olanak sağladığı için çok kullanışlıdır.
* Kodlar sırayla çalışır.

* Bir değişken tanımlarken aşağıdaki yapıyı kullanacağız.
```
değişken ismi = atanacak değer
```

**DEĞİŞKEN TANIMLAMA KURALLARI**
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

**4. TYPE FONKSİYONU**
* Bir değişkenin integer, float, string ya da boolean olup olmadığını verir yani değişkenin veri tipini verir.

**5. SAYI VERİ TÜRLERİ VE MATEMATİKSEL İŞLEMLER**
**SAYI VERİ TÜRLERİ**
Sayısal ifadelerde tırnak işareti kullanmamıza gerek yok
**int**
* Tam sayıları temsil eder. <br>
(mesela 10,20,0,-45)

**float**
* Ondalıklı sayıları ifade eder.<br>
(mesela 10.0, 20.5, 0.0, -56.7)
* Python iki rakamı birbirine böldüğü zaman gerçek sonucak ulaşmak için float değer döndürür.
<br>
**MATEMATİKSEL İŞLEMLER**
**Aritmetik Operatörler**
toplama(+), çıkarma(-), çarpma(*), bölme(/), üs alma(**), mod alma(%), tam bölme(//)


**6. STRING, BOOLEAN VERİ TÜRLERİ**
**string**
* Metinsel ifadelerdir.
* Metinsel ifadeler "", '', "" "" arasına yazılmalıdır.
* Metinsel ifadelerde eğer tek tırnak ile başlandıysa tek tırnak ile devam edilmesi gerekmektedir.
* Metinsel ifadelerin index ile ulaşma imkanı sağlar. Yazılımda index 0'dan başlar.<br>
(mesela "Merhaba Dünya" metninin 2. indexinde r vardır)
<p align="center">
  <img src="/2.%20Hafta/photo/YetNot1.png" width="400">
  <img src="/2.%20Hafta/photo/YetNot2.png" width="400">
</p>

**7. INPUT FONKSİYONU**