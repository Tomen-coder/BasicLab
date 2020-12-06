
>Projekt składa się z trzech plików Dockerfile, jednego Docker-compose i<br> 
> dodatkowych plików niezbędnych do poprawnej pracy każdej usługi cząstkowej.<br> 
## PHP
Osobny pool podłączony do portu 9009 dla aplikacji webowej. <br> 
Kontekst strony umieszczony został w katalogu /srv/app. <br> 
Aplikacja korzysta z aliasu dla kontenera z bazą danych. <br> 
Kontener podłączony do sieci backend.<br> 
## MySQL
Hasło do dla uzytkownika root jest ustawione w pliku Docker-compose. <br> 
MySQL jest podłaczony do sieci backend.<br> 
## HTTPD
Ponieważ standardowy config httpd nie pozwala na uzycie proxymatcha <br> 
oraz vhostów plik ten został zmieniony. <br> 
Dyrektywa ProxyPassMatch zapełnia prawidlowe proxowanie.<br> 
W pliku httpd.conf dodano załadowanie potrzebnych dla działania proxy <br> 
bibliotek i właczone zostały odpowiedznie rozszerzenia. Kontener jest podłaczony<br> 
do do sieci frontend i backend, z proxy PHP łaczy się za pomocą aliasu.<br> 
