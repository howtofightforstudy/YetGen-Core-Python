**1. LIST COMPREHENSION**<br>
* Liste işlemlerinde kodu uzun uzadıya yazmak yerine tek bir satırda düzenleme imkanı sunmaktır
<p align="center">
  <img src="/5. Hafta/photo/yetnot.png" width="450">
</p>

**2. FONKSIYON YAPILARI**<br>
* Bir kodu birçok yerde kullanmamız gerekiyorsa, her yerde tekrar tekrar yazmayı önler. <br>
Programlamanın temeli: DRY(Don't Repeat Yourself - Kendini tekrar etme)
* Fonksiyonların içindeki değişkenler yereldir yani bir fonksiyonun içinde bir değişken tanımladığınızda o değişkeni fonksiyonun dışına çağıramayız çünkü o değişken o fonksiyona özeldir ve globalde kullanılamaz
* Ne zaman bir fonksiyon çağırılırsa, fonksiyonu yazdıktan sonra yapmalısınız
* Fonksiyon tanımlamanın yapısı şu şekildedir: <br>
```
    def fonksiyon_adi(parametre1,parametre2... (opsiyonel)):
    #fonksiyon bloğu
    Yapılacak işlemler
    #dönüş değeri - opsiyonel
```

<br>
* Tanımlanan bir fonksiyonun kullanılmasına programlama dillerinde **Fonksiyon Çağrısı** denmektedir<br>
```
    fonksiyon_adi(argüman1,argüman2...)
```
<br>
<br>

**3. ARGUMAN VE RETURN DEYİMİ**<br>
**Argüman (Parametre)**<br>
* İşlev çağırılırken parantez içindeki işlevlere iletilen değerlerdir (string,number vb)<br>
(örnek: islem_adi(argüman))
* Eğer fonksiyon çağırılırken bir argüman yoksa bu argümanın değeri none olur bu nedenle fonksiyonun içinde ifade edilecek bir değer yoksa belirlenen değer kullanılmalıdır
```
    def helloWordl(name = "ziyaretçi"):
      print("Merhaba", name)
```
* Birden fazla parametre olabilir, her biri virgülle ayrılır
<br>

**Return Deyimi**<br>
* Kodun tamamında kullanmak için işlevin kodu tamamlandıktan sonra kalan değeri (sonuç değeri) döndürür
* "return" anahtar sözcüğünden sonraki kodlar yürütülmez, bu durumda görmezden gelindikleri anlamına gelir
* return yardımıyla fonksiyonlar değerleri çağırıldığı yere döndürülebilir ve biz de bu değerleri istediğimiz yerde kullanabiliriz
<br>

**4. ARGS, KWARGS VE PASST DEYİMİ**<br>
***args**<br>
* Sınırsız sayıda parametreli fonksiyon oluşturmak için parametremizin önüne tek yıldız (*) koyabiliriz
* isimsiz argümanlardır
<br>

****kwargs**<br>
* Çift yıldızlı parametrelerin tek yıldızlı parametrelerden en önemli farkı, fonksiyonu çağırılırken anahtar-değer ilişkisiyle çağırabilmemizdir
* İsimli argümanlardır
<br>

**Pass Deyimi**<br>
* Python programlamasında pass ifadesi null değer atama için kullanılır. Python'daki bir açıklama ve geniş ifadesi arasındaki fark, yorumlayıcı bir yorumu tamamen yok sayarken, geçişin göz ardı edilmemesidir
<br>

**5. GLOBAL VE YEREL DEĞİŞKENLER**<br>
* Global değişken fonksiyonlarımızın dışında tanımladığımız değişkenlerdir
* Yerel değişkenler ise fonksiyon içinde kullandığımız değişkenlerdir
* Fonksiyonun dışında tanımladığımız fonksiyonların içinde kullanılırken, fonksiyonların içinde tanımladığımız değişkenler fonksiyonun dışında kullanılmaz
```
#global değişken
  def goster():
      #yerel değişken
```
* Bir fonksiyon kendi içerisinde çağırılırsa sonsuz döngüye girer
<br>

**6.LAMBDA**<br>
* Pythonda isimsiz olarak tanımladığımız fonksiyonlara lambda fonksiyonlar denir
* Tek satırda yazılırlar
```
  fonksiyonAdi = lambda parametreler : yapilacakIslem
```