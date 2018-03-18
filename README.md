# CODE OF DUTY (2018)
Code of Duty için, IEEE İYTE öğrenci topluluğu tarafından 9-10-11 Mart 2018 tarihinde düzenlenen, 3 ana kategoride 48 saat boyunca aralıksız mücadele sunan bir etkinlik diyebiliriz. Biz, 3 kişilik bir takım olarak bu yarışmaya BrainHack (Algoritma Geliştirme) kategorisinde katıldık. IEEE IYTE ekibinin özenle hazırladığı 24 adet soruyu cevaplamak için savaştık. Etkinlikte görevli ekibin güleryüzlü ve misafirperverliğini de unutmamak lazım tabiki.

HackerRank sitesi üzerinden yapılan hackathonda sorulan soruları ve bizim bu sorulara getirdiğimiz çözümleri aşağıda bulabilirsiniz. Yazımı paylaşmayı unutmayın. İyi okumalar...

## Bilinmeyen Denklemler
`a1x+b1y=c1` ve `a2x+b2y=c2` şeklinde iki bilinmiyenli iki denklem iki string olarak kullanıcı tarafından giriliyor. Denklemlerinin katsayıları `a1,a2,b1,b2,c1,c2` reel sayılardır. Katsayılardan herhangi biri 1 ise örneğin denklemlerden biri `x-y=9` ise, `1x-1y=9` şeklinde girilmektedir. Denklemler yalnız ve yalnız yukarıdaki formda tek bir `x`, tek bir `y` ve tek bir sabit terim içerecek şekilde, `x` li terim sol başta, `y` li terim sağ yanında ve sabit terim eşitliğin sağ tarafında olacak şekilde girilmektedir. Denklemlere yukarıda
verlenler dışında hiç bir illegal karakter girilmemektedir.

isdigit ve herhangi bir string library fonksyonu kullanmadan, Kullanıcı tarafından string olarak girilen ve bir diziye kaydedilen denklemlerin katsayılarını yazacağınız void GetCoefficients(char equation[],int equation_index) prototipli fonksiyonu kullanarak okuyup reel sayılara dönüştüren ve denklemlerin çözümünü otomatik olarak yalnız bu stringlerden yararlanarak bulup kullanıcıya gösteren bir program yazınız.

[Soru metninin tamamı için tıklayınız.](/sorular/bilinmeyen-denklemler.pdf)


```Python
d1 = input().split(" ")
d2 = input().split(" ")

y = (int(d2[0])*int(d1[2])-int(d1[0])*int(d2[2]))/(int(d2[0])*int(d1[1])-int(d1[0])*int(d2[1]))
x = (int(d1[2])-int(d1[1])*y)/int(d1[0])

print(int(x))
print(int(y))
```

## Paskal Üçgeni
`(a + b)` ifadesinin açınımında a ve b nin katsayıları paskal üçgeni ile belirlenmektedir.

a) Verilen bir `n` değeri için paskal üçgeninin katsayıların üretip aşağıdaki form şeklinde gösteren bir program yazınız.

[Soru metninin tamamı için tıklayınız.](/sorular/paskal-ucgeni.pdf)


```Python
n = int(input())

for i in range(0, n+1):
    a = 1
    for k in range(0, i):
        print(a,end=" ")
        a = int(a * (i - k) / (k + 1))
    print(1)
```

## Takıntılı Biri
Sanırım biraz takıntılı biriyim. Sabah aynanın karşısında dişlerimi fırçalarken her zaman önce boş zamanlarımı hesaplarım sonra da yapmam gereken işleri önem sırasına göre sıralarım. Sonra her boş zamanımda sırayla işlerimi yaparak günümü tamamlarım.

Eğer o boş zaman dilimi içerisinde o işi bitiremiyorsam asla o işe başlamam. Yalnız takıntılıyım dedim ya o iş kafamdayken de diğer işe asla geçemem.

Bugün size boş zaman sürelerimi ve yapmam gereken işlerin sürelerini söyleyeceğim. Göreviniz kaç işi tamamlayabileceğimi bulmak.

[Soru metninin tamamı için tıklayınız.](/sorular/takintili-biri.pdf)

```Python
nt = input().split(" ")
isler = input().split(" ")
boszaman = input().split(" ")
is_sirasi = 0
zaman_sirasi = 0

while zaman_sirasi < len(boszaman) and is_sirasi < len(isler):
    if 1 <= int(nt[0]) and 1 <= int(nt[1]) and int(nt[1]) <= 100 and int(nt[0]) <= 100:
        if int(isler[is_sirasi]) <= int(boszaman[zaman_sirasi]):
            boszaman[zaman_sirasi] = int(boszaman[zaman_sirasi]) - int(isler[is_sirasi])
            is_sirasi += 1
        elif int(isler[is_sirasi]) > int(boszaman[zaman_sirasi]):
            zaman_sirasi += 1

print(is_sirasi)
```

## Çarpımlar Karşısında Çarpılmışa Döndük

`F(x)` bir fonksiyon olsun ve bu fonsiyon `X` rakamlarının çarpımını verir. Hemen bir örnek verelim.

`F(0)=0`

`F(234)=2x3x4=24`

`F(104)=1x0x4=0`

Size üç sayı verilmektedir. Sırasıyla `A,B` ve `K`. Sizden istenen output, `[A,B]` aralığında çarpımları `K`’yı veren kaç tane integer sayının var olduğunun bulunmasıdır.

`A<= X <= B ve F(X)=K`

[Soru metninin tamamı için tıklayınız.](/sorular/carpimlar-karsisinda-carpilmisa-donduk.pdf)
```Python
N = int(input())
abx = []

for i in range(0, N):
    abx.append(input().split(" "))

def hesapla (list):
    counter = 0
    for a in range(int(list[0]), int(list[1])):
        key = 1
        for k in range(0, len(str(a))):
            key = int(str(a)[k])*key
        if key == int(list[2]):
            counter += 1
    return counter

for j in range(0,abx.__len__()):
    counter = hesapla(abx[j])
    print("Case " + str(j+1) + ": " + str(counter))

```

## BrainHack Yarışması

Size BrainHack’e katılan N tane insanın listesi verilmektedir. Her insanın bildiği veya bilmediği konular vardır. Amacınız, 2 insanın birleşerek en fazla kaç konunun bilinebileceğini bulmaktır. 0 konuyu hiç bilmediği 1 ise konuya hakim olduğunu gösterir. Maksimum 2 insan birleşerek bir takım oluşturabilir ve birinin konuya hakim olması yeterlidir. Buna ek olarak en fazla konunun bilinebilceği bu 2’li grupların sayısını da bulmanız istenmektedir.

Not: a,b ve c üç farklı insan olsun, o halde (a,b) ve (b,c) iki farklı takım olarak sayılır.

[Soru metninin tamamı için tıklayınız.](/sorular/brainhack-yarismasi.pdf)

```Python
nm = input().split(" ")
arr = []
for i in range(0, int(nm[0])):
    arr.append("0b" + input())
bilgiler = []

for i in range(0, arr.__len__()-1):
    for j in range(i+1, arr.__len__()):
        bilgiler.append(str(bin(int(arr[i], 2) | int(arr[j], 2))).count("1"))
bilgiler.sort()
print(bilgiler[-1])
print(bilgiler.count(bilgiler[-1]))

```

## Alpcan'ın Isparta Sıcağıyla İmtihanı

Güneşli bir yaz gününde Alpcan’ın dışarıda zaman geçirmesi gerekiyor.Alpcan geziye çıkmaya karar veriyor! Toplu ulaşım aracı olarak Tren i kullanmayı seçiyor. Alpcan ,trenin hareket saatini ve gideceği lokasyona ne zaman varacağını biliyor.Yalnız Alpcan’ın Matematik ile arası çok iyi değildir,bu sebeple sizin yardımınıza ihtiyacı var!

Göreviniz, kalkış ve genel seyahat süresine göre, Alpcan'ın varış noktasına varma süresini hesaplamaktır.

[Soru metninin tamamı için tıklayınız.](/sorular/alpcanin-isparta-sicagiyla-imtihani.pdf)

```Python
hm1 = input().split(" ")
hm2 = input().split(" ")
result = [00,00]
if int(hm1[0])< 24 and int(hm1[1]) < 60:
    result[0] = int(hm1[0]) + int(hm2[0])
    result[1] = int(hm1[1]) + int(hm2[1])
    while result[1] > 59:
        result[0] += 1
        result[1] -= 60

    while result[0]> 23:
        result[0] -= 24

print(str(result[0]).zfill(2) + " " + str(result[1]).zfill(2))

```

## Şifre Çözmek Ne Kadar Kolay

Size her kelimenin arasında boşluklar bulunacak şekilde bir cümle verilecektir. Bu cümle, cümleyi veren kişinin şifresini barındıran gizli bir mesaj barındırmaktadır. Siz bu cümleleri oluşturan her kelimenin baş harflerini alıp birleştirerek şifrenin ne olduğunu bulmalısınız.

[Soru metninin tamamı için tıklayınız.](/sorular/sifre-cozmek-ne-kadar-kolay.pdf)

```Python
n = input().split(" ")
crypted = ""
	for i in range(0, len(n)):
		crypted += n[i][0]
	print(crypted)

```

## Fasulyeleri Taşı

Çocukluk oyuncaklarını karıştırırken 1.sınıftaki sayma fasulyelerini bulan Ayşe ve Buğra bir oyun oynamaya karar verdiler. Oyunu başlatmak için fasulyeleri N adet yatay kutuya böldüler. Kutuların bazıları boş olabilir. Oyun boyunca oyuncu aşağıdaki hamleleri yapabilir:

- 1 fasulyeli bir kutu seçip onu oyundan çıkarabilir

- 2 fasulyeli bir kutu seçip 1 fasulyeyi çıkarıp diğer fasulyeyi soldaki kutuya koyabilir. Bu hamle en soldaki kutuyla yapılamaz.

- 3 veya daha fazla fasulye içeren bir kutu seçilip 1 fasulye çıkarılabilir, bir fasulye soldaki kutuya konup diğeri ise sağdaki kutuya konabilir. Bu hamle en sağdaki ve en soldaki kutularla yapılamaz.Oyun, her oyuncunun kendi turları sırasında bu hamleleri yapmasıyla devam eder. Hamle yapamayan oyuncu, oyun dışı kalır.

Amacınız oyuna uygun bir algoritma geliştirerek verilen bir oyun için kazanan oyuncuyu belirlemektir. Her
oyuncunun mümkün olan en iyi (yani, her oyuncu kazanmak için en doğru hamleyi yapmalıdır) hamleyi
yaptığını varsaymalısınız.

Not: Her zaman oyuna A başlar

[Soru metninin tamamı için tıklayınız.](/sorular/fasulyeleri-tasi.pdf)

```Python
kutu = input().split(" ")
sira = 'A'
array = []
val = 0

# sıranın kimde olduğunu sayan fonksiyon
def elimSende(sira):
    if sira == 'A':
        return 'B'
    else:
        return 'A'

# boş olmayan kutular bir listeye atanır
def test():
    sarray = []
    for i in range(0,array.__len__()):
        if array[i][1] != 0:
            sarray.append(array[i])
    return sarray

# her zaman birinci kutunun seçilmesini istiyoruz.
# Çünkü en risksiz kutu 1. kutu. Eğer 1. kutu boş ise sağa doğru devam ederiz.
def secim(sarray):
    if sarray.__len__() > 1:
        secilen = sarray[1]
    else:
        secilen = sarray[0]
    return secilen

# kutuların içindeki değere göre gerekli koşulları yerine getiren fonksiyon
def kutu_degistir(liste, sira):
    if liste[1] == 1:
        array[liste[0]][1] = array[liste[0]][1]-1
        elimSende(sira)
        return 0, sira
    elif liste[1] == 2 and liste[0] - 1 >= 0 and array[liste[0]-1][1] < 30:
        array[liste[0]][1] = array[liste[0]][1] - 1
        array[liste[0]-1][1] = array[liste[0]-1][1] + 1
        elimSende(sira)
        return 0, sira
    elif liste[1] >= 3 and liste[0] + 1 < array.__len__()
				and liste[0] - 1 >= 0
				and array[liste[0]-1][1] < 30:
        array[liste[0]][1] = array[liste[0]][1] - 1
        array[liste[0] - 1][1] = array[liste[0]-1][1] + 1
        array[liste[0] + 1][1] = array[liste[0]+1][1] + 1
        elimSende(sira)
        return 0, sira
    else:
        elimSende(sira)
        print("{}".format(sira))
        return 1, sira

for i in range(0,kutu.__len__()):
    array.append([i, int(kutu[i])])

while val == 0:
    test()
    val, sira = kutu_degistir(secim(test()), sira)


```

## Ali Ayşe'yi Seviyoor!

Ayşe ile Ali sevgilidir fakat Ayşe Ali'ye küsmüştür. Alinin kendini affetirebilmesi için Ayşe'nin Ali'ye verdiği Array i çözmesi gerekmektedir. Ayşe Ali'den arrayin içindeki sayıların çarpımlarından oluşacak sonuçların bir sayının tam karesi olmasını istemektedir ve bunlardan oluşacak sayıların kaç tanesinin bir sayının tam karesi olduğunu bulmasını istemektedir.

Hadi Ali'ye yardım edelim de küsleri barıştıralım.

Örneğin: Array `[7,6,10,15,2]` olarak verilsin.

`6*10*15=900=30^2`

[Soru metninin tamamı için tıklayınız.](/sorular/ali-ayseyi-seviyoor.pdf)

```Python
import math
size = input().split(" ")
arr = input().split(" ")
counter = 0
for i in range(0, len(arr)):
    temp = 1
    for j in range(i, len(arr)):
        temp = temp * int(arr[j])
        if (math.sqrt(int(temp)))%1 == 0:
            #print(math.sqrt(int(temp)))
            counter += 1
print(counter)

```

## Dilara Partide

Dilara, çocuklar için verilen bir partiye gönüllü olarak katılıyor ve çocuklara çok sevdikleri bir çizgi film karakterini lego parçaları ile yaptırması görevi veriliyor. Bu karakterden lego parçaları ile bir tane yapmak için n farklı renk eş şekilli lego parçasından a_i adet gerekiyor.

Dilara kendisine verilen kutuyu açtığında her bir renk parçadan b_i tane olduğunu görüyor. Ek olarak da k tane renksiz lego parçası ve boya olduğunu fark ediyor.

Göreviniz Dilara’nın bu renksiz parçaları boyayarak legolarla bu karakterden maksimum sayıda çocuklara yaptırmasına yardımcı olmak.

[Soru metninin tamamı için tıklayınız.](/sorular/dilara-partide.pdf)

```Python
nk = input().split(" ")
gerekli = input().split(" ")
elimizde = input().split(" ")
counter = 0
while True:
    for i in range(0, elimizde.__len__()):
        if int(elimizde[i]) >= int(gerekli[i]):
            elimizde[i] = int(elimizde[i]) - int(gerekli[i])
        else:
            nk[1] = int(nk[1]) + int(elimizde[i]) - int(gerekli[i])
    if int(nk[1]) < 0:
        break
    counter += 1
print(counter)

```

## Ulaş'a Güven Olur mu?

Ulaş, Hasan’a ne olursa olsun onun tarafında olacağına dair söz veriyor. Hasan ise Ulaş’ın bu sözünün ne kadar güvenilir olduğundan pek emin değil.Bunun için onun sözünün güvenilirliğini test etmek için F(N) fonksiyonunu hesaplamak istiyor. F(N) fonksiyonu için ise alttaki iki koşulu sağladığı biliniyor.

`1≤K≤N gcd(K,N)=1`

Bu F(N) fonksiyonu, yukardaki koşulu sağlayan kaç tane sayı olduğunu bulan bir fonksiyondur.

Hasan verilen N değerinin F(N) fonksiyonu yardımıyla, kaç iterasyon sonucunda 1’e ulaşacağını Ulaş’ın bulmasını istiyor.Eğer N çok büyük bir değer ise,

`N = a^b * c^d * e^f * g^h`

formunda verilecektir. Eğer Ulaş bunu yapamazsa, on bin kirpik alacaktır. Ulaş’ın bu görevi yerine getirmesine ve Hasan’a olan değerini kanıtlamasına yardım edin.

[Soru metninin tamamı için tıklayınız.](/sorular/ulasa-guven-olur-mu.pdf)

```Python
from math import gcd

case = int(input())
array = []
for i in range(0, case):
    array.append(input().split(" "))

def function(sayi, stepCounter):
    stepCounter += 1
    gcdCounter = 0
    if sayi == 1:
        stepCounter -= 1
    for i in range(0, sayi):
        if gcd(i, sayi) == 1:
            gcdCounter += 1

    if gcdCounter == 1:
        print(stepCounter)

    else:
        return function(gcdCounter, stepCounter)


def NFinder(l):
    N = (int(l[0]) ** int(l[1])) * (int(l[2]) ** int(l[3])) *
		(int(l[4]) ** int(l[5])) * (int(l[6]) ** int(l[7]))
    function(N, 0)

for i in array:
    NFinder(i)
```

## Burak'ın Doğum Günü Hediyesi

Burak sıralı n pozitif sayısından oluşan bir doğum günü hediyesi alıyor. Sıralı altkümelerinin toplamları bu K sayısı ile bölünebilen altkümelere bayılıyor. Burak için bu sayıları sayan bir program yazmanızı istiyoruz.

[Soru metninin tamamı için tıklayınız.](/sorular/burakin-dogum-gunu-hediyesi.pdf)

```Python

T = int(input())
nklist = []
array = []

for i in range(0, T):
    nklist.append(input().split(" "))
    array.append(input().split(" "))

def hesapla(list, bolum):
    key = 0
    counter = 0
    for k in range(0, list.__len__()):
        key = 0
        for i in range(k, list.__len__()):
            key += int(list[i])
            if key % int(bolum) == 0:
                counter += 1
    return counter

for j in range(0,array.__len__()):
    counter = hesapla(array[j], nklist[j][1])
    print(counter)
```

## Haydi Sırala!

Size bir string verilmektedir. Bu string alfanümerik karakterlerden oluşur. Amacınız ise bu stringi bazı kurallar gereğinde sıraya dizmenizdir.( Alfanümerik, Latin alfabesindeki harfleri (A-Z, a-z) ve rakamları (0-9) kullanan karakter dizisini tanımlamakta kullanılan bir sıfat. )

- Küçük harfler büyük harflerden önce gelir.

- Büyük harfler rakamlardan önce gelir.

- Tek rakamlar çift rakamlara göre önce gelir.

[Soru metninin tamamı için tıklayınız.](/sorular/haydi-sirala.pdf)

```Python
Str = input()
str2=[]
liste=[]
temp=[]
temp2=[]
temp3=[]

for i in range(0,Str.__len__()):

    str2.append(ord(Str[i]))

str2.sort()
for i in range(0, str2.__len__()):
    liste.append(chr(str2[i]))

for i in range(0, liste.__len__()):
    if ord(liste[i]) >=65 and ord(liste[i]) <=90:
        temp.append(liste[i])

for i in range(0, temp.__len__()):
    liste.remove(temp[i])
    liste.append(temp[i])

for i in range(0, liste.__len__()):
    if ord(liste[i]) >=48 and ord(liste[i]) <=57:
        temp3.append(liste[i])

for i in range(0, temp3.__len__()):

    if (int(temp3[i])%2)==1:
        liste.remove(temp3[i])
        liste.append(temp3[i])
    else:
        liste.remove(temp3[i])
        temp2.append(temp3[i])


for i in range(0, temp2.__len__()):
    liste.append(temp2[i])
print("".join(liste))

```

## Madem Programcısınız Gösterin Hünerinizi

Madem programcısınız gösterin hünerinizi !! Size 2 adet rakam veriliyor. N ve K. N sayısı, basamaklı sayı sistemi kullanarak, (Taban değeri 1’den büyük olmalıdır.) verilen K rakamı uzunluğunda bir sayı ile elde edilebilir mi?

[Soru metninin tamamı için tıklayınız.](/sorular/madem-programcisiniz-gosterin-hunerinizi.pdf)

```Python
counter = int(input())
case = []
for i in range(0, counter):
    case.append(input().split(" "))

def tester(N, K):
    floor = 2
    while True:
        if floor**K > N >= floor**(K-1):
            print("YES " + str(floor))
            break
        elif floor <= 100:
            floor += 1
        else:
            print("NO")
            break

for i in case:
    tester(int(i[0]), int(i[1]))
```

## Üşengeç Acemi Şoför

Önal ehliyetini yeni almış acemi bir şofördür. Ehliyet sınavını geçmesine rağmen PARK etmekte hala eksiklikleri vardır. Önal park etme becerisini geliştirmek için her gün uygulamalı olarak aynı park yerinde çalışıyor. Çalıştığı park yerinde N adet park edebileceği yer bulunmaktadır. Ayrıca bu park yerinde M adet araba hali hazırda park edilmiş olduğunu biliyorsunuz. Önal pratik yapmayı sevmediğinden, belirli bir park boşluğunun olup olmadığını size soracaktır.

Önala yardım edebilmek için bu soruları cevaplayacak bir program yazın.

[Soru metninin tamamı için tıklayınız.](/sorular/usengec-acemi-sofor.pdf)

```Python
NMK = input().split(" ")
parkEdilmis = []
onalSordu = []
for i in range(0, int(NMK[1])):
    parkEdilmis.append(input())
for j in range(0, int(NMK[2])):
    onalSordu.append(input())

for o in onalSordu:
    if o in parkEdilmis:
        print(1)
    else:
        print(0)
```
