# Creazione di un pacchetto conda da Pypi

Crea il pacchetto con:

    $ conda skeleton pypi <nomepacchetto-pipy> --version <la-versione-di-interesse>

Verrà creata una cartella <nomepacchetto-pipy> con dentro "meta.yaml". Aprire e verificare/aggiungere il seguente attributo:

    build:
        preserve_egg_dir: True

Controlla le dipendenze nel file meta.yaml (spesso problemi di nomi diversi ) e lancia con fiducia il comando:
  
    $ conda build miopacchetto

Se va tutto bene alla fine puoi fare l'upload seguendo le istruzioni che vengono stampate sullo schermo, qualcosa del tipo:

    $ anaconda upload \path\to\package.tar.bz2

Per creare il pacchetto per altre piattaforme puoi usare il comando convert:

    $ conda convert \path\to\package.tar.bz2 -p win-64

**NB**: il conda convert è valido solo per i pacchetti che non contengono compilati.
