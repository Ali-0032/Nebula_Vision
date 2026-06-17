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

Infine, su alcune di queste immagini è prevista un'interazione diretta: la presenza di hotspot circolari grafici attiva, al clic dell'utente, un ingrandimento dell'area selezionata. Questa azione è accompagnata dall'apertura di un box informativo specifico che approfondisce le caratteristiche fisiche e astronomiche della zona evidenziata.

<img width="1728" height="995" alt="Screenshot 2026-06-16 alle 19 03 39" src="https://github.com/user-attachments/assets/09a9dc32-6501-445d-b1c2-a2eadf8102b8" />



## Tecnologia usata
La tecnologia usata per creare il sito web è stata:
- HTML e CSS: struttura e stile del sito web
- JavaScript (p5.js): interazioni del sito.

Di seguito viene riportata la sezione di codice JavaScript che gestisce l'interazione tramite hotspot sulle immagini:

```JavaScript
let activeType = null;

function changeContent(tabNumber) {
  if (hStella) {
    hStella.style.display = 'none';
    hStella.style.width = '40px';
    hStella.style.height = '40px';
  }
  if (hPolvere) hPolvere.style.display = 'none';
  if (hNodi) hNodi.style.display = 'none';

  if (tabNumber === 2) {
    if (hStella) {
        hStella.style.display = 'block';
        hStella.style.width = '170px';
        hStella.style.height = '170px';
        hStella.style.top = '70%';
        hStella.style.left = '65%';
    }
  }
}

function togglePopup(type, show) {
    const popups = document.querySelectorAll('.popup-box');
    const svgContainer = document.getElementById('connection-svg');
    
    popups.forEach(p => p.style.display = 'none');
    
    if (show && type) {
        activeType = type;
        document.getElementById(`popup-${type}`).style.display = 'block';
        svgContainer.style.display = 'block';
        updateLine();
    } else {
        activeType = null;
        svgContainer.style.display = 'none';
    }
}

function updateLine() {
    if (!activeType) return;
    const popup = document.getElementById(`popup-${activeType}`);
    const hotspot = document.getElementById(`hotspot-${activeType}`);
    const svgLine = document.getElementById('svg-line');
    const wrapper = document.getElementById('interactive-wrapper');

    if (popup && hotspot && wrapper) {
        const wRect = wrapper.getBoundingClientRect();
        const hRect = hotspot.getBoundingClientRect();
        const pRect = popup.getBoundingClientRect();
        let x1, y1, x2, y2;
        
        if (activeType === 'stella') {
            x1 = hRect.right - wRect.left - 5;
            y1 = hRect.top + hRect.height / 2.6 - wRect.top;
            x2 = pRect.left - wRect.left + 130;
            y2 = pRect.top + pRect.height / 2 - wRect.top;
        } else {
            x1 = hRect.left - wRect.left;
            y1 = hRect.top + hRect.height / 2 - wRect.top;
            x2 = pRect.right - wRect.left - 130;
            y2 = pRect.top + pRect.height / 2 - wRect.top;
        }
        
        svgLine.setAttribute('x1', x1); svgLine.setAttribute('y1', y1);
        svgLine.setAttribute('x2', x2); svgLine.setAttribute('y2', y2);
    }
}

function windowResized() {
  resizeCanvas(windowWidth, windowHeight);
  updateLine();
}
```

## Target e contesto d’uso
Nebula Vision si rivolge a un’utenza generalista con un interesse per l’astronomia, alla ricerca di contenuti accessibili ma scientificamente rigorosi. Il progetto si colloca in un contesto d'uso di tipo divulgativo-educativo: attraverso l’esplorazione attiva delle immagini, l’utente viene guidato in un percorso di apprendimento dinamico, in cui l’intrattenimento visivo diventa lo strumento principale per la comprensione dei dati scientifici.
