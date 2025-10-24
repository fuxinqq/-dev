import random
import math


print("----sayı randomlama ve istatistiksel hesaplamalar------")

a=random.randint(1,1000)
b=random.randint(1,1000)
c=random.randint(1,1000)
d=random.randint(1,1000)
e=random.randint(1,1000)
f=random.randint(1,1000)
g=random.randint(1,1000)
h=random.randint(1,1000)
i=random.randint(1,1000)
j=random.randint(1,1000)
sayilar=[a,b,c,d,e,f,g,h,i,j]
print("rastgele sayılar:..",sayilar)
print("----toplam,ortalama,min,max hesaplama-----")
toplam=a+b+c+d+e+f+g+h+i+j
ortalama=toplam/10
minimum = sayilar[0]
maksimum = sayilar[0]
for sayi in sayilar:
    if sayi < minimum:
        minimum = sayi
    if sayi > maksimum:
        maksimum = sayi
print("toplam:...",toplam)
print("ortalama:...",ortalama)
print("minimum:...",minimum)
print("maksimum:...",maksimum)
print("----sıralama-----")
n =len(sayilar)
# Dış döngü
for i in range(n):
    degisim_yapildi = False
    for j in range(0, n - i - 1): 
        if sayilar[j] > sayilar[j + 1]:
            sayilar[j], sayilar[j + 1] = sayilar[j + 1], sayilar[j]
            degisim_yapildi = True
    if not degisim_yapildi: 
        break
        
print("sıralanmış liste:...",sayilar)
print("----medyan hesaplama-----")
n=len(sayilar)
if n%2 == 0 :
    eleman_5=n// 2-1
    eleman_6=n//2
    x=sayilar[eleman_5]
    y=sayilar[eleman_6]
    medyan = (x + y) / 2
else:
    orta_indis=n//2
    medyan=sayilar[orta_indis]
print("Medyan:..." ,medyan)

print("-----standart sapma-----")
farkların_karesi_toplamı=0
for sayi in sayilar:
    fark=sayi - ortalama
    fark_karesi=fark**2
    farkların_karesi_toplamı += fark_karesi
    varyans =farkların_karesi_toplamı / (n-1)
    standart_sapma=math.sqrt(varyans)
print("standart sapma:...",standart_sapma)
