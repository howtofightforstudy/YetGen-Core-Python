**NESNE YÖNELİMLİ PROGRAMLAMA (OOP)**<br>
DRY (Don't Repeat Yourself) sağlar. Kod tekrarını önlemek, hem okunabilirliği arttırır hem de rüski azaltır<br>
Class, nesne, constructor ve self parametresi, nesne yönelimli programlamanın (OOP) temel kavramlarıdır.<br>

**2. METOT**<br>
Metotlar, sınıflar içinde tanımlanan ve nesnelerin belirli işlemleri gerçekleştirmesini sağlayan fonksiyonlardır.
<br>

```
class Yazilimci:
    def __init__(self, isim, soyisim, numara, maas, diller):
        self.isim = isim
        self.soyisim = soyisim
        self.numara = numara
        self.maas = maas
        self.diller = diller

    def bilgiler_goster(self):
        print(f"""
        Çalışan bilgisi:
            İsim: {self.isim}
            Soyisim: {self.soyisim}
            Numara: {self.numara}
            Maaş: {self.maas}
            Bildiği diller: {self.diller}
        """)

    def dil_ekle(self, yeni_dil):
        print("Dil eklendi")
        self.diller.append(yeni_dil)

    def maas_yukselt(self, zam):
        print("Zam yapılıyor")
        self.maas += zam 

yazilimci = Yazilimci("Berkcan", "Işık", "12345", 10000, ["Python", "JavaScript", "Flutter"])
yazilimci.bilgiler_goster()
yazilimci.maas_yukselt(3500)
yazilimci.bilgiler_goster()
yazilimci.dil_ekle("React")
yazilimci.bilgiler_goster()
```
<br>

**INHERITANCE**<br>
- Bu konsepti aslında bizim kendi anne babamızdan değişik özellikleri ve davranışları miras almamıza benzetebiliriz.<br>
- Bir sınıfın özelliklerinin ve metotlarının başka sınıflara aktarılarak işlevinin artırılmasını sağlar.<br>
- Mesela öğrenci ve öğretmeni düşündüğümüz zaman öğrencinin adı soyadı, adresi, cinsiyeti ve numarası vardır. Öğretmeninse ad, soyad, adres, cinsiyet ve branşı vardır. Bunun yerine kisi sınıfı oluşturup ad, soyad, adres ve cinsiyet tutulur.<br>
- Öğrenci ve öğretmen classında ise öğrenciyeveya öğretmene özgü özellikler ve metotlar tutulur.<br>
- super() en genel anlamıyla miras aldığımız sınıfın metodlarını alt sınıflardan kullanmamızı sağlar<br>
- super().init() metodu çalışırken sınıfın özelliklerini ve metotlarını kullanır.
- 