# Naloga: Python Intro

Ustvarite Jupyter Notebook ali klasično Python datoteko, kjer sprogramirate dva razreda: Serija in Razpredelnica. V naši nalogi se bomo omejili, da lahko Serija in Razpredelnica vsebujeta le števila (float ali int).

Prvi razred Serija predstavlja en stolpec v razpredelnici (predstavljajte si Excel, kjer en stolpec ponazarja Serijo) in naj vsebuje sledeče vrednosti:

naziv (str), ki pove naziv stolpca
vrednosti (list), ki vsebuje vse vrednosti tega stolpca (le int ali float, ni potrebno preverjanje)
Razred Serija naj ima sledeče metode:

konstruktor __init__(naziv, vrednosti=[]), ki prejme str (obvezno) za naziv stolpca in seznam (opcijsko) za vrednosti stolpca
prestej(), ki vrne število vseh elementov Serije (število elementov v seznamu vrednosti)
opisi(), ki vrne povprečje celotnega stolpca
glava(x=4), ki vrne prvih x (privzeto 4) elementov iz seznama vrednosti
rep(x=4), ki vrne zadnji x (privzeto 4) elementov iz seznama vrednosti
dodaj(vrednost, indeks=None), ki doda vrednost na indeks (privzeto None, kar pomeni, da doda na konec) v seznamu vrednosti
zbrisi(indeks), ki izbriše element na mestu indeks iz seznama vrednosti
Drugi razred Razpredelnica je sestavljena iz več Serij in naj vsebuje sledeče vrednosti:

stolpci (list), seznam vseh Serij
Razred Razpredelnica naj vsebuje sledeče metode:

konstruktor __init__(stolpci=[]), ki prejme seznam stolpcev (opcijsko), ki se nato zapišejo v vrednost stolpci v razredu
prestej(), ki vrne seznam dveh števil: prvo je število vrstic, drugo je število stolpcev v razpredelnici
opisi(), ki vrne povprečje vsakega stolpca posebej v slovarju (dict), kjer je ime Serije ključ in povprečje vrednost
glava(x=3), ki vrne prvih x (privzeto 3) vrstic
rep(x=3), ki vrne zadnji x (privzeto 3) vrstic
dodaj_vrstico(vrstica, indeks=None), doda vrstico (list), na mesto indeks (privzeto None, kar pomeni, da doda na konec); pazite, da doda posamezno vrednost v vsako Serijo posebej
zbrisi_vrstico(indeks), ki izbriše vrstico na mestu indeks; pazite, da izbriše vrednosti v vsaki Seriji posebej
dodaj_stolpec(stolpec, indeks=None), doda stolpec (tipa Serija) na mesto indeks (privzeto None, kar pomeni, da doda na konec) v seznam stoplci
zbrisi_stolpec(indeks), ki izbriše stolpec na mestu indeks iz seznama stolpci
Po zapisanih razredih zapišite sledečo kodo, da preverite delovanje:

s1 = Serija('visina', [1.5, 1.7, 1.4, 1.3, 1.9])
s2 = Serija('sirina', [5, 7, 4, 3, 9, 6])
s3 = Serija('starost', [15, 11, 10, 12])

print(s1.prestej()) # 5
print(s2.prestej()) # 6
print(s3.prestej()) # 4

s2.zbrisi(2)
s3.dodaj(13, indeks=1)

print(s1.prestej()) # 5
print(s2.prestej()) # 5
print(s3.prestej()) # 5

raz = Razpredelnica([s1, s2, s3])
print(raz.prestej()) # [5, 3]

raz.dodaj_vrstico([1.6, 8, 14])
raz.dodaj_stolpec(Serija('teza', [34, 21, 56, 43, 51, 28]))

print(raz.prestej()) # [6, 4]
print(raz.opisi()) # {'visina': 1.5667, 'sirina': 6.3333, 'starost': 12.5, 'teza': 38.8333}    zaokroževanja niso nujna točno taka kot so tukaj

raz.zbrisi_stolpec(0)
raz.zbrisi_vrstico(1)
print(raz.prestej()) # [5, 3]
