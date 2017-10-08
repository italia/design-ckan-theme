RATIO:
Ho voluto impattare il meno possibile nei files del CKAN. Per cui ho lavorato su due files html, sul custom css che si gestisce dal backend grafico di CKAN come superadmin e infine ho usato i file del webkit AGID sul Design.


0) Istruzioni da dove iniziare su https://github.com/italia/dati-ckan-docker
1) Scaricare il Docker del TeamIT e modificarlo secondo i punti seguenti PRIMA di lanciare ./build_local.sh
2) Sostituire i files header.html e base.html in ckan/templates. Sono inseriti i link ai js del webkit del design e cambia il menu di navigazione. Introdotti "Enti" e "Temi" al posto di Organizzazioni e Gruppi
3) Opzionale sostituire la dir LC_MESSAGES in ckan/ckan/ckan/i18n/it. Corretti alcuni errori.
4) Modificare o sostituire il file layout2.html (cambia la classe "main" in "main2" del div) che si trova in templates/home/. Serve per avere solo una sezione e uno sfondo omogeneo. in home/snippets/ sostituire search.html
5) Copiare la cartella "build" in public/base/javascript/ . Contiene i files del webkit del Design dell'AGID.
4) Seguire il punto 1) digitando  ./build_local.sh ect.
5) Una volta che il Docker è attivo, entrare in localhost:5000 come ckanadmin e andare in configurazione, incollando nella sezione "custom css" il contenuto del file configurazione-custom-css.txt . L'utente cosi può modificare a piacimento colori ect. Nell'esempio c'è uno sfondo di Lecce.
6) Demo online su www.piersoft.it/ckan (aprirà un IP dinamico dove gira il CKAN Demo) oppure digitare piersoft.dtdns.net


Attenzione per gli sviluppatori che vogliano usare il Docker in produzione:
1) Il Docker del TeamIT se usato in produzione deve essere modificato per accettare di eseguire i previews dei dataset (csv, json ect). In particolare il file docker-compose.yml ha localhost:5000 che va sostituito. Nel mio caso è http://piersoft.dtdns.net
2) E' consigliato, come indicato nella issue https://github.com/italia/dati-ckan-docker/issues/6 , installare anche il plugin geoview.


Ringrazio il designer Salvatore COSTA che durante l'hackathon mi ha dato due dritte fondamentali.
