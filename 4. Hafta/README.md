**1. LISTELER**
* [] içerisinde tutulurlar.
* Indexleme, veri güncelleme, silme, veri ekleme gibi işlemler yapılabilir.
* İç içe listeleme işlemi yapılabilir
<br>
* Listelerde soldan sağa index numaraları sıfırdan başlar, sağdan sola ise -1'den başlar
![bknz](/4.%20Hafta/photo/YetNot3.png)
<br>

**LISTE METODLARI**
**append():** Listenin sonuna eleman ekler <br>
**remove():** Listenin içerisindeki elemanı siler

```
liderler = ["Ahmet","Eslem","Berkcan","Çağla"]
liderler[0] = "Berkcan" #bu ise güncelleme yapmamızı sağlar
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

 **LISTE TOPLAMA**
 iki listeyi birleştirir
 

**2. TUPLE (DEMET)**

**3. SET**

**4. DICTIONARY (SÖZLÜK)**

**5. STRING METODLARI**