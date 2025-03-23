**1. MODÜLLER**<br>
### MODÜL MANTIĞI<br>
Bir Python modülünü programımıza dahil ederek bu modüller içinde yazılan fonksiyonlardan ve sınıflardan kullanabilir, programlarımızı daha efektif bir şekilde yazabiliriz. Eğer modül diye bir kavram olmasaydı programlarımızdaki her bir fonksiyonu ve sınıfı kendimiz yazmak zorunda kalacaktık
<br>
Python modülü, içinde fonksiyonlar, sınıflar ve değişkenler barındıran bir Python dosyasıdır. Başka Python dosyalarında bu modülü import ederek tekrar kullanabilirsin.

**2. MATH MODÜLÜ**
```
import math 
```
bu şekilde math modülünü import ediyoruz

```
dir(math) 
```
ile modülün içinde hangi fonksiyonların olduğunu görebiliyoruz

```
help(math)
```
bu şekilde fonksiyonların ne işe yaradığını görebiliyoruz

### KENDİ MODÜLÜMÜZÜ YAZALIM<br>
```
from modül_adı import * 
```
bu şekilde kütüphanemizi kullanabiliriz

```
from math import *
def factorial(sayi):
    print("Kendi Faktöriyel Fonksiyonum")
    faktoriyel = 1 
    if(sayi == 0 or sayi == 1):
        return 1
    while(sayi >= 1):
        faktoriyel *= sayi
        sayi -= 1
    return faktoriyel
factorial(5)
```

**3. GÖMÜLÜ FONKSİYONLAR**<br>
### Map Fonksiyonu <br>
Parametre olarak aldığı fonksiyona, paramtere olarak aldığı listenin her elemanını sırasıyla parametre olarak gönderir
```
map(fonksiyon,iterasyon yapılabilecek veritipi(liste,demet,vb)...)
```
<br>

### Filter Fonksiyonu<br>
İsminden de anlaşılacağı gibi filtreleme işlemi yapar
```
filter(fonksiyon,iterasyon yapılabilen bir veritipi(liste vb))
```

**4. HATA YÖNETİMİ**

