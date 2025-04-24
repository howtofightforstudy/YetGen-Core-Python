**Dosya Okuma İşlemleri**<br>
* Dosya açmak ve oluşturmak için open() kullanılır
```
open(dosyaIsmi, dosyaModu)
```
* dosyaModu: Dosyanın hangi modda açacağını belirtir
* r : Okuma modunda açmayı sağlar, belirtilen konumda dosya olması gerekir
* close(): Dosyayı kapatır<br>

**read() Fonksiyonu**<br>
read() fonksiyonu eğer içine hiçbir değer vermezsek bütün dosyamızı okuyacaktır<br>
* her çalıştırıldığında bir satırı okuyabilir eğer fazladan yazdırmaya çalışırsak boş döner
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
file.seek(0)  #!burada ikinci okuma için imleci başa aldık
icerik2 = file.read()
print("2.okuma dosya içeriği\n", icerik2)
file.close()
```