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