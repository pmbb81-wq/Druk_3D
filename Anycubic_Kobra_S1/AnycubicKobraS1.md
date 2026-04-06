
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

Teraz wykonajmy inna operacje aby przejsc do ktoregos katalogo. Jak juz wiemy, komenda ls / z roota pokazujemy foldery i pliki.

Sprobujmy przejsc teraz do folderu useremain

```
cd /useremain
```

Widok:

<img width="680" height="381" alt="obraz" src="https://github.com/user-attachments/assets/69830020-d710-4769-bba4-b3952ead9c08" />

Komenda ls -F wylistujemy foldery i pliki.

Aby wrucic do poprzedniego folderu wykonujemy:

```
cd ..
```

Skoro mamy juz podstawy ogarniete to teraz pobawmy sie bardziej. Sprubuje wyszukac wszystkie urzadzenia ktore mam podpiete pod USB.

Teraz bede korzystal z terminala na PC czyli google chrome z wtyczka SSH. Bedzie latwiej to ogarniac. Wspomne o bardzo waznej rzeczy.

Bede sie wspomagal AI :) Nie uwazam sie za jakiegos GURU linuxowego wiec w tym przypadku bardzo mi to ulatwi prace z terminalem.

Zaczynamy :)

Na poczatek polacze sie z drukarka przez strone www tak aby miec dostep do kamerki. Wyglada to tak:

<img width="1801" height="604" alt="obraz" src="https://github.com/user-attachments/assets/0ee0d27c-2a62-4749-9c30-b90fff886ae9" />

Z poziomu tego interfejsu praktycznie nic nie zrobimy z nasza kamerka. Opcji jest jak na lekarstwo.

<img width="957" height="664" alt="obraz" src="https://github.com/user-attachments/assets/575dbef6-1021-4b92-a5f9-4e2d69c0dfe1" />

Zaczniemy z grubej rury. Kamerka posiada AF i jak ktos to mi pisal nie nadaje sie do drukarki 3D. BLAD! To nie jest prawda.

Zrobimy tak,ze wylaczymy AF i ustawimy odpowiednia ostrosc - stala ostrosc bez krecenia fizycznie obiektywem kamerki. 

Aby zmienic AF czyli np go wylaczyc wykonujemy taka komende:

```
v4l2-ctl -d /dev/video10 --set-ctrl=focus_auto=0
```

Aby wlaczyc AF wpisujemy:

```
v4l2-ctl -d /dev/video10 --set-ctrl=focus_auto=1
```

Teraz wisienka na torcie. Ustawiamy ostrosc kamerki! Cos pieknego. Nie musimy nic fizycznie niszczyc obiektywu. To jest mega plus.

Komenda to:

Zakres od 0 do 800.

```
v4l2-ctl -d /dev/video10 --set-ctrl=focus_absolute=200
```

Z presetem 800 obraz wyglada nastepujaco:

<img width="1274" height="469" alt="obraz" src="https://github.com/user-attachments/assets/acea3f4e-617d-46b9-a746-ead6d156fe46" />

Z presetem 400 obraz wyglada nastepujaco:

<img width="1302" height="409" alt="obraz" src="https://github.com/user-attachments/assets/6cc9b83d-bfb8-49c3-9c2e-7d130f451607" />

Z presetem 200:

<img width="1227" height="480" alt="obraz" src="https://github.com/user-attachments/assets/1cebe289-6fc2-4316-a3fd-bb4665a467e7" />






























































































