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
### map() Fonksiyonu <br>
Parametre olarak aldığı fonksiyona, paramtere olarak aldığı listenin her elemanını sırasıyla parametre olarak gönderir
```
map(fonksiyon,iterasyon yapılabilecek veritipi(liste,demet,vb)...)
```

### filter() Fonksiyonu<br>
İsminden de anlaşılacağı gibi filtreleme işlemi yapar
```
filter(fonksiyon,iterasyon yapılabilen bir veritipi(liste vb))
```

### zip() Fonksiyonu<br>
iki dizisel elemanın öğelerini birbiriyle eşleştirerek bir zip objesi oluşturur
```
liste1 = [1,2,3,4]
liste2 = [5,6,7,8]
liste3 = ["Python","Java","C#","Javascript"]
list(zip(liste1,liste2,liste3))
```
her dizinin i. indeksini ayrı toplar
çıktısı: [(1, 5, 'Python'), (2, 6, 'Java'), (3, 7, 'C#'), (4, 8, 'Javascript')]

### enumerate() Fonksiyonu<br>
ingilizcede enumerate kelimesi 'numaralandırmak' anlamına gelir. enumerate() fonksiyonunun görevi de kelimenin bu anlamıyla aynıdır yani bu fonksiyonu kullanarak nesneleri numaralandırabiliriz
```
liste = ["Elma","Armut","Muz","Kiraz"]
list(enumerate(liste))
```
[(0, 'Elma'), (1, 'Armut'), (2, 'Muz'), (3, 'Kiraz')]

### all() Fonksiyonu<br>
all() fonksiyonu bütün değerler true ise true, en az bir değer false ise false sonuç döndürür
```
liste1 = [True,True,False]      #sonuç false
all(liste1)

liste2 = [True,True,True]       #sonuç true
all(liste2)
```

### any() Fonksiyonu<br>
any() fonksiyonu bütün değerler False ise False, en az bir değer True ise True sonuç döndürür
```
liste1 = [True,True,False]      #sonuç true
any(liste1)                   

liste2 = [True,False,False]     #sonuç true
any(liste2)

liste3 = [False,False,False]    #sonuç false
any(liste3)
```

**4. HATA YÖNETİMİ**<br>
python programlarında bazen bir değişkenin tanımlanmadan kullanılmaya çalıştırılması, bazen de yapılamayacak bir aritmetik işlemin yapılması python'da hatalara yol açar ancak bu istisnai durumlarda, halatın türüne göre programlarımızı daha güvenli bir şekilde yazabiliriz. Yani hata çıkarabilecek kodlarımızı öngörerek bu hataları programlarımızda yakalayabiliriz
```
print(a)
#NameError: name 'a' is not defined

print(2/0)
#ZeroDivisionError: division by zero

print "Merhaba"
#SyntaxError: Missing parentheses in call to 'print'. Did you mean print(...)?
```

### Try, Except Blokları<br>
try, except bloklarının yapısı şu şekildedir:
<br>

**try:** Hata çıkarabilecek kodlar buraya yazılır<br>
Eğer hata çıkarsa program uygun olan **except** bloğuna girecek<br>
Hata oluşursa **try** bloğunun geri kalanındaki işlemler çalışmayacak
<br>

**except** Hata1: Hata1 oluştuğunda burası çalışacak<br>

**except** Hata2: Hata2 oluştuğunda burası çalışacak<br>