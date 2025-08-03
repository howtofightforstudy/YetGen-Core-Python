**DOSYA OKUMA İŞLEMLERİ**<br>
* Dosya açmak ve oluşturmak için open() kullanılır
```
open(dosyaIsmi, dosyaModu)
```
*dosyaModu*: Dosyanın hangi modda açacağını belirtir<br>
*r*: Okuma modunda açmayı sağlar, belirtilen konumda dosya olması gerekir<br>
*close()*: Dosyayı kapatır<br>

**READ() FONKSİYONU**<br>
read() fonksiyonu eğer içine hiçbir değer vermezsek bütün dosyamızı okuyacaktır<br>
* readline() ile her çalıştırıldığında bir satırı okuyabilir eğer fazladan yazdırmaya çalışırsak boş döner
```
file = open("bilgiler.txt","r",encoding="utf-8")
print(file.readline())
print(file.readline())
print(file.readline())
file.close()
```
* read() fonksiyonuyla bir dosyayı okuduğumuzda dosya imlecimiz dosyanın en sonuna gider ve read() fonksiyonu 2. okuma da artık boş string döner
```
file = open("bilgiler.txt","r",encoding="utf-8")
icerik = file.read()
print("1.okuma dosya içeriği\n", icerik)

#!burada ikinci okuma için imleci başa aldık
file.seek(0) 
icerik2 = file.read()
print("2.okuma dosya içeriği\n", icerik2)
file.close()
```
* readlines() fonksiyonu dosyanın bütün satırlarını bir liste şeklinde döner
```
file = open("bilgiler.txt","r",encoding="utf-8")
print(file.readlines())
```
**DOSYA YAZMA**<br>
*w*: Yazma moduç Dosya konumda oluşturur, dosya konumda varsa ekleme işlemi yapar.<br>
```
file = open("bilgiler.txt","w",encoding="utf-8")
file.write("İZMİR\n")
file.close()
```
*a*: append (ekleme) modudur. Dosya konumda varsa oluşturur, dosya konumda varsa ekleme işlemi yapar<br>
```
file = open("bilgiler.txt","a",encoding="utf-8")
file.write("İSTANBUL\n")
file.close()
```
*r+*: Hem okuma hem yazma modudur. Dosya konumda yoksa hata verir<br>
```
file = open("bilgiler.txt","r+",encoding="utf-8")
file.write("ANKARA\n")
file.read()
file.close()
```
İZMİR'i silip ANKARA yazdı<br>
**Neden böyle oluyor?**<br>
Çünkü r+ modunda dosya başından itibaren yazmaya başlar.<br> 
file.write("ANKARA\n") dediğinde:<br>
* ANKARA\n ifadesi 7 karakter uzunluğundadır.Bu yüzden dosyanın başındaki ilk 7 karakterin üzerine yazar.
* "İZMİR\n" toplam 6 karakterdi, yani ANKARA onu ezip geçer.<br>
Bu durum "overwrite" (üzerine yazma) olarak adlandırılır.<br>

**DOSYALARI OTOMATİK KAPATMA**<br>
with yapısı kullanılarak dosya işlemleri tamamlandığında dosyanın otomatik olarak kapanması sağlanır.<br>
```
with open(dosya_adi, dosya_kipi) as file:
    Dosya işlemleri
```

**DOSYAYI İLERİ_GERİ SARMAK**<br>
* seek() metodunu kullanarak istediğiniz bayt konumuna dönebilirsiniz
* Dosyanın hangi bayt konumunda bulunduğunu öğrenmek istersek de tell() metodunu kullanabiliriz
```
with open("bilgiler.txt","r",encoding="utf-8") as file:
    file.seek(20) #20.bayta gitti
    print(file.tell()) #file dosyasının hangi baytta olduğunu yazdırdı
```

**DOSYA SONUNDA DEĞİŞİKLİK YAPMAK**<br>
Belirli bir konuma giderek dosya içeriğinin ortasında ya da sonunda değişiklik yapmayı sağlar.<br>
```
with open("bilgiler.txt","r+",encoding="utf-8") as file:
    file.seek(10)
    file.write("deneme")

with open("bilgiler.txt","r+",encoding="utf-8") as file:
    print(file.read())

#çıktısı:
ANKARA
ADdenemeDIYAMAN
AFYONKARAHİSAR
İSTANBUL
```

**DOSYANIN BAŞINDA DEĞİŞİKLİK YAPMAK**<br>
Dosya içeriği okunarak başına yeni veriler eklemek için kullanılır.<br>
```
with open("bilgiler.txt","r+",encoding="utf-8") as file:
    icerik = file.read()
    icerik = "Zonguldak\n" + icerik
    file.seek(0)
    file.write(icerik)

with open("bilgiler.txt","r+",encoding="utf-8") as file:
    print(file.read())

#çıktısı:
Zonguldak
ANKARA
ADdenemeDIYAMAN
AFYONKARAHİSAR
İSTANBUL
```

**DOSYA ORTASINDA DEĞİŞİKLİK YAPMAK**<br>
Dosya satır satır okunarak istenilen satıra yeni bir satır eklemek için kullanılır.<br>
```
with open("bilgiler.txt","r+",encoding="utf-8") as file:
    liste = file.readlines()
    liste.insert(3,"ESKİŞEHİR\n")
    file.seek(0)
    file.writelines(liste)

with open("bilgiler.txt","r+",encoding="utf-8") as file:
    print(file.read())

#çıktısı:
Zonguldak
ANKARA
ADdenemeDIYAMAN
ESKİŞEHİR
AFYONKARAHİSAR
İSTANBUL
```

**NESNE YÖNELİMLİ PROGRAMLAMA (OOP)**<br>
DRY (Don't Repeat Yourself) sağlar. Kod tekrarını önlemek, hem okunabilirliği arttırır hem de rüski azaltır<br>
Class, nesne, constructor ve self parametresi, nesne yönelimli programlamanın (OOP) temel kavramlarıdır.<br>

**1. CLASS**<br>
Sınıflar veya Classlar objelerimizi oluştururken objelerin özelliklerin ive metodlaırnı tanımladığımız bir yapıdır<br>
Sınıf oluşturma:
```
class Araba():
    #sınıf özellikleri(attribute)
    model = "Renault Megane"
    renk = "Gümüş"
    beygirGucu = 110
    silindir = 4
```

<br>

**OBJE OLUŞTURMA**<br>
Obje oluşturmak, bir sınıftan (class) örnek üretmektir bu sayede o sınıfın sahip olduğu özellikleri ve davranışları taşıyan bir nesne elde ederiz.
```
obje_ismi = Sınıf_ismi(parametreler(opsiyonel))
```

**ÖZELLİKLERE ERİŞME**<br>
Bir obje oluşturduktan sonra o objeye ait özelliklere nokta (.) notasyonu ile erişebiliriz. Özellikler, sınıf içinde self ile tanımlanmış değişkenlerdir.
```
obje_ismi.ozellik_ismi
```
<p align="center">
  <img src="/8. Hafta/yetgennot.png" width="450">
</p>
<br>

```
class Araba():
    #sınıf özellikleri(attribute)
    model = "Renault Megane"
    renk = "Gümüş"
    beygirGucu = 110
    silindir = 4

#bu şekilde erişim sağlanabilir
araba1 = Araba()
print(araba1.model)
print(araba1.renk)
print(araba1.beygirGucu)
print(araba1.silindir)

#bu şekilde de erişim sağlanabiliriz
class Hayvan():
    isim = "Kuş"
    print(isim)
```

**INIT() FONKSİYONU**<br>
Pythonda yapıcı(constructor) fonksiyon olarak tanımlanmaktadır. Bu metod objelerimiz oluşturulurken otomatik olarak ilk çağrılan fonksiyondur. Bu metodu özel olarak tanımlayarak objelerimizi farklı değerlerle oluşturabiliriz
```
class Araba():
    def __init__(self):
        print("init fonksiyonu çalıştı")
    
araba = Araba()
```
Self anahtar kelimesi objeyi oluşturduğumuz zaman o objeyi gösteren bir referanstır ve metodlarımızda en başta bulunması gereken bir parametredir<br>
Self anahtar kelimesi sayesinde, her objeye ait özellikleri tek tek tanımlamak yerine, o objeyi temsil eden referansı kullanarak sınıf içindeki tüm özelliklere ve metodlara erişim sağlarız.
```
class Araba():
    def __init__(self,model,renk,beygirGücü,silindir):
        self.model = model
        self.renk = renk
        self.beygirGücü = beygirGücü
        self.silindir = silindir

araba2 = Araba("Peugeot 301","Beyaz",90,4)
print(araba2.model)
```