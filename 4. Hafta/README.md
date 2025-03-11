**1. LISTELER**
* [] içerisinde tutulurlar.
* Indexleme, veri güncelleme, silme, veri ekleme gibi işlemler yapılabilir.
* İç içe listeleme işlemi yapılabilir
<br>
* Listelerde soldan sağa index numaraları sıfırdan başlar, sağdan sola ise -1'den başlar<br>

<br>
<br>
<p align="center">
  <img src="/4. Hafta/photo/YetNot3.png" width="450">
</p>

**LISTE METODLARI**<br>
**append():** Listenin sonuna eleman ekler <br>
**remove():** Listenin içerisindeki elemanı siler

```
liderler = ["Ahmet","Eslem","Berkcan","Çağla"]
liderler[0] = "Berkcan" 
#bu ise güncelleme yapmamızı sağlar
print(liderler)
```
Eğer index numarasında bulunan bi eleman yoksa hata verir, güncelleme yapmaz

**clear():** Listenin içerisindeki elemanları siler

**index():** Listedeki elemanın indexini verir<br>
Aranan veriyi ilk bulunduğunda durur, diğer verilerde aunı veri varsa getirmez. Eğer veri bulunamazsa ValueError hatası verir

 **pop():** Listedeki elemanı siler<br>
 Eğer index verilmezse son elemanı siler, index verilirse verilen indexdeki elemanı siler

 **insert():** İstenilen indexe eleman ekler 

 **reverse():** Listeyi ters çevirir

 **sort():** Listeyi küçükten büyüğe sıralar
 <br>

 **LISTE TOPLAMA**<br>
 iki listeyi birleştirir

**2. TUPLE (DEMET)**
* Tuple listelere benzerdir
* Tuple ile liste arasındaki en önemli fark tuple elemanlarının değiştirilemez, liste elemanlarının değiştirilebilir olmasıdır
* Performanslı bir data sağlar
* () içerisinde tanımlanabilir
* İç içe tuple oluşturulabilir
* Liste içerisinde tuple, tuple içerisinde liste tanımlamak mümkündür
* Bir kere tanımlandıktan sonra değiştirilemezler yalnızca okunurlar
* Tek elemansa tuple olduğunu belirtmek için bir virgül koyulmalıdır

**3. SET**
* Listelere benzer
* En önemli özelliği indexsiz ve sırasız elemanlardan oluşmasıdır
* Veri tekrarı söz konusu değildir, tüm elemanlar eşsizdir
* {} içerisinde tanımlanır
* Çok hızlı bir veri tipidir

**Set Metodları**<br>
**add():** Sete eleman ekler<br>
**remove():** Setten eleman siler<br>
**clear():** Setin içerisindeki elemanları siler<br>
**pop():** Serin son elemanını siler<br>
**update():** Sete eleman ekler<br>
**union():** İki seti birleştirir<br>
**intersection():** İki setin kesişimini alır<br>
**difference():** İki setin farkını alır<br>

**4. DICTIONARY (SÖZLÜK)**
* Sırasız veri tutar
* Günlük hayatta olan sözcükler gibi düşünebiliriz
* {} arasında tanımlanır
* key: anahtar (bir bilgiye ulaşmak için kullanılır)
* value: değer
* key-value örneği:<br>
```
{06:"Ankara"}
```
*06 key, Ankara value*
* dict("") şeklinde de sözlük tanımlayabiliriz<br>
<br>

*Sözlüklerde integer, float, string ya da tuple veri tipleri kullanılırken listeler ve sözlükler kullanılamaz*

**5. STRING METODLARI**<br>
**String Parçalama**<br>
```
x = "YetGen"
print(x[2:5])
#ikinci elemandan başlar beşinci elemana kadar yazdırır, 5 dahil değildir

print(x[2:])
#ikinci elemandan itibaren yazdırır

print(x[:2])
#ikinci elemana kadar yazdırır, ikinci eleman dahil değil

print(x[::-1])
#tersten yazdırırız
```
<br>

**String Metodları**<br>
**len():** Stringin uzunluğunu verir
**upper():** Stringin tüm harflerini büyük harfe çevirir
**lower():** Stringin tüm harflerini küçük harfe çevirir
**capitalize():** Stringin ilk harfini büyük harfe çevirir
**swapcase():** Stringin tüm büyük harflerini küçük harfe, küçük harflerini büyük harfe çevirir
**replace():** Stringin içerisindeki veriyi değiştirir
**split():** Stringi parçalar
**strip():** Stringin başındaki ve sorunundaki boşlukları siler
**startwith():** Stringin belirtilen karakterle başlayıp başlamadığını kontrol eder
```
deger = "YetGen"
print(deger.startswith("Y"))
print(deger.startswith("y"))
#küçük-büyük harf duyarlılığı vardır
```
**endswith():** Stringin belirtilen karakterle bitip bitmediğini kontrol eder
**find():** Stringin tüm karakterlerinin alfabetik olup olmadığını kontrol eder. Eğer yoksa -1 döndürür.
**index():** Stringin içerisindeki verinin indexini verir. Eğer veri yoksa ValueError hatası verir
**isalpha():** Stringin tüm karakterlerinin alfabetik olup olmadığını kontrol eder
**isdigit():** Stringin tüm karakterinin rakam olup olmadığını kontrol eder.