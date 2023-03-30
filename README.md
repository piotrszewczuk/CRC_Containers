# CRC 2023 - Konteneryzacja

## Instrukcja uruchomienia środowiska laboratoryjnego

1. **Wymagane komponenty**

Komputer PC z systemem operacyjnym MS Windows 10, Apple macOS lub Linux o następujących minimalnych parametrach:

- procesor min. 4 rdzeniowy lub 2 rdzeniowy z technologią Hyper-Threading i włączoną opcją wirtualizacji w BIOS / UEFI
- min. 16 GB pamięci RAM
- min. 40 GB wolnej przestrzeni dyskowej

Dodatkowo należy pobrać i zainstalować następujące oprogramowanie:

- Vagrant - narzędzie do automatyzacji uruchamiania środowisk wirtualnych https://www.vagrantup.com/downloads
- VirtualBox - środowisko wirtualizacyjne https://www.virtualbox.org/wiki/Downloads
- Git - narzędzie do kontroli wersji plików https://git-scm.com/downloads

> Instalacja powyższych komponentów wymaga posiadania uprawnień Administratora systemu operacyjnego. 

2. **Uruchomienie środowiska laboratoryjnego**

Po instalacji wymaganego oprogramowania należy należy utworzyć katalog np. "CRC2023-Konteneryzacja" w którym będzie znajdowała się konfiguracja środowiska laboratoryjnego, uruchomić terminal, przejść do utworzonego katalogu i za pomocą polecenia git zsynchronizować repozytorium wykonując następujące polecenie w terminalu:

> git clone https://github.com/piotrszewczuk/CRC_Containers.git
 
Po zsynchronizowaniu rapozytorium należy uruchomić w terminalu następujące polecenia: 

- w systemie MS Windows
  
  ```bash
  cd c:\CRC2023-Konteneryzacja
  vagrant up
  ```
- w systemach Apple macOS i Linux
  
  ```bash
  cd ~/CRC2023-Konteneryzacja
  vagrant up
  ```
  
  Poprawne inicjalizowanie środowiska laboratoryjnego powinno zakończyć się uruchomieniem 4 maszyn wirtualnych widocznych w programie VirtualBox, tak jak jest to widoczne na poniższym zrzucie ekranu.

![](https://github.com/piotrszewczuk/CRC_Containers/blob/main/Images/zz-crc-k8s.png)
