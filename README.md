# Sprawozdanie: Laboratorium 12

## Cel zadania
Uruchomienie trzech serwerów Nginx (web1, web2, web3) w zdefiniowanej sieci mostkowej (`lab12net`), udostępnienie ich na zewnątrz oraz podłączenie wolumenów typu bind mount w celu serwowania wspólnej strony HTML (tylko do odczytu) i zapisu logów do dedykowanych katalogów na systemie macierzystym.

## 1. Przygotowanie struktury katalogów i pliku HTML
Utworzono dedykowane katalogi na logi oraz wygenerowano plik `index.html`.

<img width="940" height="47" alt="image" src="https://github.com/user-attachments/assets/08a56ae7-3b43-49cd-8373-85fe6f24ffc0" />

## 2. Utworzenie sieci mostkowej
Zdefiniowano nową sieć typu bridge dla kontenerów.


<img width="940" height="126" alt="image" src="https://github.com/user-attachments/assets/76132933-5aff-44ca-874a-1abad2c4250a" />

## 3. Uruchomienie kontenerów Nginx
Uruchomiono 3 kontenery. Zostały one podłączone do sieci lab12net, porty zmapowano odpowiednio na 8081, 8082, 8083, a wolumeny skonfigurowano przy użyciu zalecanej składni --mount type=bind. Wolumen HTML otrzymał flagę readonly.

<img width="940" height="628" alt="image" src="https://github.com/user-attachments/assets/9f38e67f-07bd-40d8-8ce3-3fc2c3e5e8a3" />

## 4. Weryfikacja działania środowiska
A. Weryfikacja dostępu do strony WWW
Sprawdzono poprawność dostarczania treści statycznej HTML ze wszystkich trzech zmapowanych portów serwerów nginx.

<img width="487" height="254" alt="image" src="https://github.com/user-attachments/assets/9d0bb9fb-19d9-4c46-9d3c-bdaf81ca9e95" />

B. Weryfikacja zapisu logów
Sprawdzono, czy serwery poprawnie generują pliki z logami w wydzielonych i podmontowanych katalogach na systemie macierzystym hosta.

<img width="940" height="395" alt="image" src="https://github.com/user-attachments/assets/8d2e914e-cdd1-441f-9ecf-4c58a8628762" />
