
<h1 align="center">📋SSH - Anycubic Kobra S1 (Rinkhals firmware)</h1>

Postaram sie przekazac fajne informacje na temat drukarki Anycubic Kobra S1 i kamerki FullHD zakupionej na Aliexpress.

Kamerka ma Auto fokus i tutaj nalezy o czyms wspomniec. Swego czasu dostalem pewne komentarze, ze taka kamerka jest do bani itp.

Nie nadaje sie do drukarki 3D bo autofokus nie bedzie nadazal za poruszajaca sie glowica itp. Takie typowe biadolenie :D

Ale wczoraj odkrylem cos bardzo fajnego, co tych, nazwijmy to "malkontentow" sprowadzi na parter :D

Cala zabawa sprowadzi sie do obslugi terminala SSH i dzieki temu bedziemy mieli dosyc spora kontrole nad parametrami naszej kamerki.

Kamerka kupiona na Aliexpress...FullHD@30FPS z katem 120 stopni. Link ponizej:

https://pl.aliexpress.com/item/1005007757639743.html

<img width="479" height="237" alt="obraz" src="https://github.com/user-attachments/assets/0025caa5-e4ac-4dc5-84dd-03e24fba9595" />

Zacznijmy wiec od poczatku. Opisze to na swoim przykladzie i nic pozatym. Uzywam telefonu z Androidem - Xiaomi 11T PRO.

Potrzebna bedzie aplikacja do SSH. Ja uzylem darmowej z F-Droida. F-Droid to taki nieoficjalny sklep z aplikacjami gdzie mozemy znalezc duzo perelek :)

Ponizej screen z sklepu F-Droid i aplikacja Haven SSH Client.

<img width="508" height="1143" alt="obraz" src="https://github.com/user-attachments/assets/0894b763-f36e-4ddc-88f0-37db3321d933" />

A tak wyglada sama aplikacja:

<img width="324" height="681" alt="obraz" src="https://github.com/user-attachments/assets/9b9a8a54-0d92-46e4-9112-c2f3922f83ee" />

Dane logowania do SSH dla Anycubic Kobra S1 z zainstalowanym rinkhalsem w wersji 2.7.0.9

```
username: root
password: rockchip
port: 22
hostname: twoj ip drukarki w sieci LAN (192.168.xxx.xxx)

```

Oczywiscie programow do SSH jest cala masa. Mozna korzystac na pc lub androidzie bez problemu. Wazne aby program SSH na androida pozwalal nam na wyjscie
z edytowanego pliku :)

Pokaze dwa warianty. Z korzystaniem na androidzie i z wtyczka na chromie czyli na PC. Najpierw android.

Po zalogowaniu do systemu mamy taki widok:

<img width="780" height="367" alt="obraz" src="https://github.com/user-attachments/assets/982aefc3-8a3a-4b18-a15c-a73df7a28707" />

Na poczatek prosta komenda do wylistowania katalogow czyli ls. Podajemy ja dokladnie tak:

```
ls /

```

W programie na androidzie pokaza sie takie informacje:

<img width="680" height="267" alt="obraz" src="https://github.com/user-attachments/assets/de016189-64a0-4327-bd0c-aae6371a25c4" />

Aby sprawdzic co jest folderem a co plikiem wpisujemy tak:

```
ls / -F

```

Otrzymamy taki widok: @- to sa pliki /- to sa foldery

<img width="680" height="202" alt="obraz" src="https://github.com/user-attachments/assets/3799401d-54e2-4dbb-a828-1c1296597cec" />





































