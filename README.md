Wykonanie zadań postawionych przed grupą w ramach projektu nr 2.

# **Zadanie 1. *Dla podanych niżej hashy określ typ wykorzystanego algorytmu hashującego, a następnie złam hasło metodą brute-force.***
## 1. Każde hasło składa się z maksymalnie 5 znaków (tylko cyfry).

1. 81dc9bdb52d04dc20036dbd8313ed055
2. d8826bbd80b4233b7522d1c538aeaf66c64e259a
3. b021d0862bc76b0995927902ec697d97b5080341a53cd90b780f50fd5886f4160bbb9d4a573b76c23004c9b3a44ac95cfde45399e3357d1f651b556dfbd0d58f
4. 31bca02094eb78126a517b206a88c73cfa9ec6f704c7030d18212cace820f025f00bf0ea68dbf3f3a5436ca63b53bf7bf80ad8d5de7d8359d0b7fed9dbc3ab99


**Rozwiązanie**

Wykorzystałam **Hash-identifier** do określenia algorytmu hashującego.

![alt text](/screenshots/1_1.png)

Użyłam **Hashcat** do złamania haseł metodą **brute-force**

![alt text](/screenshots/1_1_1.PNG)

***Złamane hasła***
1. 81dc9bdb52d04dc20036dbd8313ed055 : **1234**
2. d8826bbd80b4233b7522d1c538aeaf66c64e259a : **4121**
3. b021d0862bc76b0995927902ec697d97b5080341a53cd90b780f50fd5886f4160bbb9d4a573b76c23004c9b3a44ac95cfde45399e3357d1f651b556dfbd0d58f : **6969**
4. 31bca02094eb78126a517b206a88c73cfa9ec6f704c7030d18212cace820f025f00bf0ea68dbf3f3a5436ca63b53bf7bf80ad8d5de7d8359d0b7fed9dbc3ab99 : **0**


## 2. Każde hasło składa się z maksymalnie 5 znaków (małe i wielkie litery).

1. 9e66d646cfb6c84d06a42ee1975ffaae90352bd016da18f51721e2042d9067dcb120accc574105b43139b6c9c887dda8202eff20cc4b98bad7b3be1e471b3aa5
2. 8a04bd2d079ee38f1af784317c4e2442625518780ccff3213feb2e207d2be42ca0760fd8476184a004b71bcb5841db5cd0a546b9b8870f1cafee57991077c4a9

**Rozwiązanie**

Wykorzystałam **Hash-identifier** do określenia algorytmu hashującego.

![alt text](/screenshots/1_2.PNG)

Użyłam **Hashcat** do złamania haseł metodą **brute-force**

![alt text](/screenshots/1_2_1.PNG)

***Złamane hasła***
1. 9e66d646cfb6c84d06a42ee1975ffaae90352bd016da18f51721e2042d9067dcb120accc574105b43139b6c9c887dda8202eff20cc4b98bad7b3be1e471b3aa5 : **sda**
2. 8a04bd2d079ee38f1af784317c4e2442625518780ccff3213feb2e207d2be42ca0760fd8476184a004b71bcb5841db5cd0a546b9b8870f1cafee57991077c4a9 : **Asia**

## 3. Hasło składa się z dokładnie z 6 znaków alfanumerycznych*.
*Wskazówka jest błędna, w haśle użyto również znaków specjalnych.

```console
┌──(kali㉿kali)-[~]
└─$ hash-identifier 44d9886c0a57ddbfdb31aa936bd498bf2ab70f741ee47047851e768db953fc4e43f92be953e205a3d1b3ab752ed90379444b651b582b0bc209a739a624e109da
   #########################################################################
   #     __  __                     __           ______    _____           #
   #    /\ \/\ \                   /\ \         /\__  _\  /\  _ `\         #
   #    \ \ \_\ \     __      ____ \ \ \___     \/_/\ \/  \ \ \/\ \        #
   #     \ \  _  \  /'__`\   / ,__\ \ \  _ `\      \ \ \   \ \ \ \ \       #
   #      \ \ \ \ \/\ \_\ \_/\__, `\ \ \ \ \ \      \_\ \__ \ \ \_\ \      #
   #       \ \_\ \_\ \___ \_\/\____/  \ \_\ \_\     /\_____\ \ \____/      #
   #        \/_/\/_/\/__/\/_/\/___/    \/_/\/_/     \/_____/  \/___/  v1.2 #
   #                                                             By Zion3R #
   #                                                    www.Blackploit.com #
   #                                                   Root@Blackploit.com #
   #########################################################################
--------------------------------------------------

Possible Hashs:
[+] SHA-512
[+] Whirlpool

Least Possible Hashs:
[+] SHA-512(HMAC)
[+] Whirlpool(HMAC)
--------------------------------------------------

┌──(kali㉿kali)-[~]
└─$ hashcat -m1700 -a3 44d9886c0a57ddbfdb31aa936bd498bf2ab70f741ee47047851e768db953fc4e43f92be953e205a3d1b3ab752ed90379444b651b582b0bc209a739a624e109da -1?a ?1?1?1?1?1?1 -O --show
44d9886c0a57ddbfdb31aa936bd498bf2ab70f741ee47047851e768db953fc4e43f92be953e205a3d1b3ab752ed90379444b651b582b0bc209a739a624e109da:T0^^3k
```


# **Zadanie 2. *Łamanie haseł (met. słownikowa).***
## 1. Dla podanych niżej hashy określ typ wykorzystanego algorytmu hashującego, a następnie złam hasło metodą słownikową.
Hasła pochodzą ze słownika *rockyou*.

1. 9fd8301ac24fb88e65d9d7cd1dd1b1ec
2. 7f9a6871b86f40c330132c4fc42cda59
3. 6104df369888589d6dbea304b59a32d4
4. 276f8db0b86edaa7fc805516c852c889
5. 04dac8afe0ca501587bad66f6b5ce5ad

**Rozwiązanie**

Podobnie jak w poprzednim zadaniu użyłam **Hash-identifier** do zidentyfikowania algorytmu hashującego.

Następnie zapisałam hashe do jednego pliku w związku z tym samym algorytmem hashującym. Przy pomocy **Hashcat** dokonałam złamania haseł **metodą słownikową**.

![alt text](/screenshots/2_1.png)

***Złamane hasła***
1. 9fd8301ac24fb88e65d9d7cd1dd1b1ec : **butterfly**
2. 7f9a6871b86f40c330132c4fc42cda59 : **tinkerbell**
3. 6104df369888589d6dbea304b59a32d4 : **blink182**
4. 276f8db0b86edaa7fc805516c852c889 : **baseball**
5. 04dac8afe0ca501587bad66f6b5ce5ad : **hellokitty**

## 2. Dla podanych niżej hashy określ typ wykorzystanego algorytmu hashującego, a następnie złam hasło metodą słownikową.
Hasła pochodzą ze słownika *rockyou*.

1. 7ab6888935567386376037e042524d27fc8a24ef87b1944449f6a0179991dbdbc481e98db4e70f6df0e04d1a69d8e7101d881379cf1966c992100389da7f3e9a
2. 470c62e301c771f12d91a242efbd41c5e467cba7419c664f784dbc8a20820abaf6ed43e09b0cda994824f14425db3e6d525a7aafa5d093a6a5f6bf7e3ec25dfa

**Rozwiązanie**

Wykonałam je podobnie jak poprzednie zadanie.

***Złamane hasła***

1. 7ab6888935567386376037e042524d27fc8a24ef87b1944449f6a0179991dbdbc481e98db4e70f6df0e04d1a69d8e7101d881379cf1966c992100389da7f3e9a : **spiderman**
2. 470c62e301c771f12d91a242efbd41c5e467cba7419c664f784dbc8a20820abaf6ed43e09b0cda994824f14425db3e6d525a7aafa5d093a6a5f6bf7e3ec25dfa : **rockstar**

# **Zadanie 3. *Analiza ruchu HTTP***
**Środowisko:** Kali Linux
1. Rozpocznij monitorowanie ruchu sieciowego (narzędziem Wireshark).
2. W przeglądarce nawiąż połączenie z http://testphp.vulnweb.com/login.php
3. Wykonaj próbę logowania (dowolne dane).
4. Odszukaj w zapisanym ruchu swoje dane logowania.

Dla porównania powtórz ćwiczenie z logowaniem np. do Facebooka (również dowolne,
nieprawdziwe dane logowania).

**Rozwiązanie**

Do śledzenia ruchu użyłam programu **Wireshark**. Przez nałożenie filtru http.request odnalazłam sekcję "POST" w której znalazłam zapis próby logowania wraz z wpisanym użytkownikiem i hasłem.

![alt text](/screenshots/3.png)

Powtórzenie zadania dla strony Facebook skończyło się niepowodzeniem w związku z szyfrowaniem strony https.

# **Zadanie 4. *Analiza ruchu SSH***
**Środowisko:** Kali Linux, maszyna SDA z projektu 1.

1. Rozpocznij monitorowanie ruchu sieciowego (narzędziem Wireshark).
2. Nawiąż połączenie pomiędzy Kalim a SDA po SSH.
3. Stwórz pliki sekret1.txt i sekret2.txt z tajnymi hasłami.
4. Edytuj konfigurację vsFTPd, żeby umożliwić wgrywanie plików po FTP.
5. Zakończ połączenie po SSH.
6. Spróbuj poszukać w zapisanym ruchu sieciowym zawartość plików sekret1.txt i sekret2.txt
Dane logowania do SDA: uranus/butterfly, root/666

**Rozwiązanie**

Za pomocą narzędzia **nmap** przeskanowałam własną sieć w poszukiwaniu innych urządzeń oraz otwartych portów.
```console
┌──(kali㉿kali)-[~]
└─$ sudo nmap -A 192.168.1.11/24 
```
W wyniku odnalazłam maszynę, która ma być celem.
![alt text](/screenshots/4_1.PNG)

Znając adres ip maszyny oraz login i hasło nawiązuję połączenie SSH.

```console
┌──(kali㉿kali)-[~]
└─$ ssh uranus@192.168.1.6                             
uranus@192.168.1.6's password: 
Welcome to Ubuntu 22.04 LTS (GNU/Linux 5.15.0-27-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Sun Nov  6 02:40:04 PM UTC 2022

  System load:  0.0009765625      Processes:               111
  Usage of /:   30.2% of 9.75GB   Users logged in:         1
  Memory usage: 3%                IPv4 address for enp0s3: 192.168.1.6
  Swap usage:   0%


12 updates can be applied immediately.
To see these additional updates run: apt list --upgradable


The list of available updates is more than a week old.
To check for new updates run: sudo apt update

Last login: Sat Nov  5 11:59:24 2022 from 192.168.1.11
uranus@vm-sda:~$ 

```
Następnie tworzę pliki dodając do nich zawartość za pomocą komendy ***nano***.

```console
uranus@vm-sda:~$ nano sekret1.txt
uranus@vm-sda:~$ nano sekret2.txt 
```

W Wireshark nakładam filtr aby zawęzić pole poszukiwań.
```console
ip.addr==[adres ip] || ssh
```
Niestety nie ma możliwości podejrzenia zawartości plików gdyż ruch ssh jest szyfrowany.

![alt text](/screenshots/4_2.png)

Dodatkowo konfiguruję vsftpd umożliwiając wgrywanie plików za pośrednictwem FTP (przygotowanie do kolejnego zadania).

![alt text](/screenshots/4_3.png)

# **Zadanie 5. *Analiza ruchu FTP***

Środowisko: Kali Linux, maszyna SDA z projektu 1
1. Rozpocznij monitorowanie ruchu sieciowego (narzędziem Wireshark).
2. Nawiąż połączenie pomiędzy Kalim a SDA po FTP.
3. Prześlij z Kaliego do SDA zwykły plik tekstowy (z własną zawartością).
4. Ściągnij z SDA do Kaliego pliki sekret1.txt i sekret2.txt
5. Zakończ połączenie.
6. Odszukaj w zapisanym ruchu sieciowym zawartość przesłanego i ściągniętych plików.
Dane logowania do SDA: uranus/butterfly, root/666


**Rozwiązanie**

Korzystając z wcześniej pozyskanego adresu ip łączę się za pomocą ftp.

![alt text](/screenshots/5_1.PNG)

Przesyłam utworzony wcześniej plik

![alt text](/screenshots/5_2.PNG)

oraz pobieram na swoją maszynę dwa utworzone wcześniej pliki.

![alt text](/screenshots/5_3.PNG)

Poprzez nałożenie w Wireshark filtru **ftp-data** zawężam pole poszukiwań do rekordów, w których jestem w stanie odczytać zawartość przesłanych plików.

![alt text](/screenshots/5_4.png)

# **Zadanie 6. *Eternal Blue***

**Atakujący:** Kali Linux | **Ofiara:** Windows 7
1. Przygotuj maszynę wirtualną z podatnością MS17-010 (np. Windows 7) i umieść ją w tej
samej sieci co Kali Linux.
Atakujący:
2. Wykryj i potwierdź podatność (np. nmapem).
3. Wykorzystaj podatność korzystając z frameworka Metasploit (nie jest wymagana
eskalacja uprawnień).

**Rozwiązanie**
Korzystając z narzędzia **nmap** skanuję ponownie sieć w poszukiwaniu podatnej maszyny.

![alt text](/screenshots/nmap_windows.PNG)

Korzystając z narzędzia **Metasploit** wyszukuję podatność *Eternal Blue*, którą potem wykorzystam.

![alt text](/screenshots/6_1.PNG)

Wywołuję interesujący mnie exploit i w opcjach ustawiam wymagane parametry. Następnie uruchamiam całość.

![alt text](/screenshots/6_2.PNG)

Po dostaniu się na maszynę tworzę nowy katalog na pulpicie.

![alt text](/screenshots/6_3.png)

# **Zadanie 7. *MITM przez ARP poisoning***

**Atakujący:** Kali Linux | **Ofiara:** Kali Linux "Ofiara"

**Atakujący:**
1. Wykonaj atak MITM techniką ARP poisoning (ARP spoofing).

**Ofiara:**
1. W przeglądarce nawiąż połączenie z http://testphp.vulnweb.com/login.php.
2. Wykonaj próbę logowania (dowolne dane).

**Atakujący:**
1. Odszukaj w zapisanym ruchu dane logowania ofiary.

Podobnie jak w poprzednich zadaniach przeszukuję narzędziem **Nmap** sięc w poszukiwaniu adresu ip ofiary. Następnie za pomocą narzędzia **Arpspoof** infekuję tablicę ARP.

![alt text](/screenshots/7_1.PNG)

Na maszynie "Ofiara" dokonuję logowania na stronę z zadania.
W narzędziu **Wireshark** ustawiam filtr adresu ip "Ofiary". Po odnalezieniu protokół HTTP jestem w stanie odczytać podane dane do logowania. 

![alt text](/screenshots/7_2.PNG)
