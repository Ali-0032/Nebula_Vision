SUPSI 2026  
Corso d’interaction design, CV429.01  
Docenti: A. Gysin, G. Profeta  

Progetto 1: La conquista dello spazio

# Nebula Vision
Autore: Alissa Bionda \
[Nebula Vision](https://ali-0032.github.io/Nebula_Vision/05_prototipo_3/)


## Introduzione e tema
Nebula Vision è un progetto web nato per supportare la lettura e la comprensione delle immagini di nebulose a infrarossi catturate dal telescopio spaziale Spitzer. Il sito si concentra su due tra le più rilevanti nebulose della Via Lattea, la Nebulosa Elica e la Nebulosa Aquila, il cui studio è fondamentale per comprendere le origini e il destino futuro del nostro Sistema Solare.


## Riferimenti progettuali
Il riferimento progettuale principale è Wikipedia, in particolare per quanto riguarda il sistema di interazione dei termini in evidenza. Questo modello è stato d’ispirazione per lo sviluppo delle interazioni sulle immagini delle nebulose, permettendo all'utente di approfondire elementi specifici attraverso un approccio dinamico.

<img width="1601" height="926" alt="wikipedia" src="https://github.com/user-attachments/assets/a5e4d740-3585-4350-9fc1-f1b656c9c4a6" />



## Design dell’interfaccia e modalità di interazione

### Design dell'interfaccia:
Il design dell'interfaccia è minimalista, scelta per lasciare spazio e rilevanza alle immagini, che costituiscono l'elemento principale e fondante del sito. Il font selezionato è il Roboto, utilizzato nelle versioni Regular e Condensed per garantire un'ottima leggibilità su schermo. Infine, la scelta di adottare uno sfondo nero richiama il concetto di spazio e universo, l'ambiente in cui si trovano le nebulose.

### Modalità di interazione:
L'esperienza utente inizia dalla Hero section della pagina home, la quale contiene un breve testo con lo scopo di contestualizzare gli obiettivi del sito. Subito sotto è presente una sezione introduttiva volta a spiegare in generale all'utente cos'è una nebulosa e a presentare il Telescopio Spaziale Spitzer. Per quanto riguarda la navigazione generale, questa è affidata a una header bar posizionata in alto, che permette di selezionare ed esplorare le due nebulose disponibili nel sito.

<img width="1728" height="995" alt="Screenshot 2026-06-16 alle 19 01 33" src="https://github.com/user-attachments/assets/7e38dab0-7504-4f1d-8e4a-8a8bfa5bb23a" />

Successivamente, una volta selezionata la nebulosa da esplorare, l'interfaccia presenta un sistema di navigazione a pulsanti posti direttamente sotto il titolo, che consente di passare fluidamente tra tre immagini della stessa nebulosa a diverse frequenze d'onda. Questa funzione permette all'utente di osservare l'oggetto celeste attraverso vari spettri infrarossi, offrendo una comparazione visiva immediata dello stesso soggetto.

Nello specifico, le tre opzioni di visualizzazione gestiscono i contenuti nel seguente modo:
- Frequenza in Luce Visibile: mostra l'immagine classica accompagnata da un breve testo di spiegazione riguardante la nebulosa e la sua specifica tipologia astronomica.
- Frequenza in Infrarosso Vicino e Medio: presentano un testo generale che racconta cosa sia possibile osservare di quella nebulosa grazie a quella determinata frequenza. In queste sezioni è inoltre integrato un breve testo esplicativo che descrive tutte le frequenze che compongono l'immagine e i dettagli scientifici visibili grazie a esse.

Infine, su alcune di queste immagini è prevista un'interazione diretta: la presenza di hotspot circolari grafici attiva, al clic dell'utente, un ingrandimento (zoom) dell'area selezionata. Questa azione è accompagnata dall'apertura di un box informativo specifico che approfondisce le caratteristiche fisiche e astronomiche della zona evidenziata.

<img width="1728" height="995" alt="Screenshot 2026-06-16 alle 19 03 39" src="https://github.com/user-attachments/assets/09a9dc32-6501-445d-b1c2-a2eadf8102b8" />



## Tecnologia usata
- HTML e CSS: stile e struttura.
- JavaScript (p5.js): interazioni.

## Target e contesto d’uso
Nebula Vision si rivolge a un’utenza generalista con un interesse per l’astronomia, alla ricerca di contenuti accessibili ma scientificamente rigorosi. Il progetto si colloca in un contesto d'uso di tipo divulgativo-educativo: attraverso l’esplorazione attiva delle immagini, l’utente viene guidato in un percorso di apprendimento dinamico, in cui l’intrattenimento visivo diventa lo strumento principale per la comprensione dei dati scientifici.
