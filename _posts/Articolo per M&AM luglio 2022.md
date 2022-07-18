# La trasformazione digitale della manutenzione in Rai Way: un caso d’uso allo studio

> ### In un'economia dinamica, i fornitori di prodotti o di servizi riconoscono la necessità di trasformarsi “digitalmente”, richiedono la capacità di scalare, allineare e regolare le capacità produttive in tempi rapidi in risposta alle richieste del mercato.  

Collegare macchine o impianti precedentemente non connessi a sistemi di dati intelligenti e, a sua volta, utilizzare i dati generati per utilizzare meglio quelli esistenti, sono gli investimenti più produttivi perché sono visti come le fondamenta su cui avviare la modernizzazione della fabbrica o dell’azienda di servizi. 

Al centro della rivoluzione digitale della produzione ci sono diversi fattori abilitanti:
•	l’evoluzione aziendale della cultura “data-driven”: i Big Data e Analytics stanno cambiando il volto delle aziende, i fornitori di prodotti e servizi vogliono accedere ai dati generati dalle macchine per monitorare il controllo qualità in tempo reale, migliorare efficacia complessiva delle Operations (mantenendo sotto controllo i relativi KPI, primo fra tutti l’OEE, Overall Equipment Effectiveness cioè l’efficienza complessiva della risorsa produttiva, una metrica ben nota che può essere adottata, con le opportune similitudini, anche alle realtà delle aziende di servizi) 

<p align="center">
<img src="Images\Immagine1.png"
alt="drawing" width="300" />
</p>



•	la convergenza OT e IT: nell’ambiente operativo le tecnologie IT e OT tendono a convergere grazie all’utilizzo delle reti IP.

Anche Rai Way, nell’ottica della “digital transformation”, sta guardando al futuro con lo studio di tecniche predittive per la manutenzione.  Lo sviluppo di un programma di manutenzione predittiva nell’ottica “Industria 4.0” richiede una strategia ben progettata per valutare le condizioni di lavoro dell'apparecchiatura e rilevare guasti incipienti in modo tempestivo, che richiede un uso efficace sia delle misurazioni dei sensori disponibili sia della conoscenza del sistema.
 
<p align="center">
<img src="C:\Users\alber\Dropbox\Articoli\Immagine2.png"
alt="drawing" width="300" />
</p>

Il programma deve prendere in considerazione molti fattori, tra cui:

•	le fonti osservate di guasto e la loro frequenza relativa: tali fonti possono essere i componenti principali della macchina, i suoi attuatori o i suoi vari sensori
•	la disponibilità di misure di processo tramite sensori: il numero, il tipo e la posizione dei sensori
•	come le varie fonti di guasto si traducono in sintomi osservati: tale analisi causa-effetto può richiedere un'ampia elaborazione dei dati dai sensori disponibili
•	la conoscenza fisica della dinamica dei sistemi: questa conoscenza può derivare da simulazioni o dalla conoscenza degli esperti del dominio
•	l'obiettivo di manutenzione, quali il ripristino dei guasti o lo sviluppo di un programma di manutenzione.

Lo studio dell’algoritmo è basilare per la predizione dell’anomalia. 

<p align="center">
<img src="C:\Users\alber\Dropbox\Articoli\Immagine3.png"
alt="drawing" width="300" />
</p>
 

Partendo da dati che descrivono il sistema in una serie di condizioni sane e difettose, è necessario sviluppare un modello di rilevamento per il monitoraggio delle condizioni operative. Lo sviluppo di tale modello richiede l'identificazione di indicatori di condizione appropriati e la formazione di un modello per interpretarli. È molto probabile che tale processo sia iterativo per i diversi indicatori di condizione e diversi modelli fino a quando non viene trovato il modello migliore per l'applicazione. Infine, l'algoritmo può essere implementato nelle apparecchiature di campo per il monitoraggio e la manutenzione delle macchine.

La progettazione inizia con un corpo di dati provenienti da più sensori e più macchine in esecuzione in momenti diversi e in condizioni operative diverse. I dati a cui avere accesso sono dati reali dal normale funzionamento del sistema, in condizioni difettose e da guasti del sistema (dati RTF o run-to-failure, come indicati nella metodologia RCM).

Un passo fondamentale nello sviluppo di algoritmi di manutenzione predittiva è l'identificazione degli indicatori di condizione caratteristici del sistema, dati il cui comportamento cambia in modo prevedibile man mano che il sistema si degrada.  Ad esempio, è possibile monitorare le condizioni di un gruppo elettrogeno o di una pompa utilizzando il rumore operativo. L’incipit del guasto, identificabile del punto P della curva PF, provoca cambiamenti nella frequenza e nell'entità delle vibrazioni.

Il cuore dell'algoritmo di manutenzione predittiva è il modello di rilevamento o previsione. Questo modello analizza gli indicatori di condizione (features) estratti per determinare le condizioni attuali del sistema.

Una volta identificato un algoritmo funzionante ed elaborato in modo appropriato per la generazione di una previsione, è necessario distribuirlo ed integrarlo nella piattaforma IOT.  La tendenza del mercato IIOT è quella di eseguire l'algoritmo sull’ "edge", cioè su dispositivi embedded più vicini alla macchina da controllare.
 
 <p align="center">
<img src="C:\Users\alber\Dropbox\Articoli\Immagine4.png"
     alt="drawing" width="300" />
</p>

<p align="center">
Fonte: https://hackmd.io/@iotmic/tinyml1010
</p>

In questa modalità la quantità di informazioni inviate viene ridotta in modo drastico in quanto i dati sono trasmessi solo quando necessario e gli aggiornamenti sullo stato delle apparecchiature sono immediatamente disponibili senza alcun ritardo, eliminando la necessità di trasferire i dati tra il cloud e le apparecchiature locali che eseguono l'algoritmo di monitoraggio della prognostica, rendendo il processo di controllo più efficace, efficiente e soprattutto meno oneroso.

### Il caso d’uso Rai Way
Il caso d’uso analizzato fa riferimento all’analisi audiometrica delle condizioni di funzionamento di un sistema di raffreddamento a liquido di un sistema trasmittente DTT, composto da uno scambiatore acqua/glicole con un sistema ridondato di pompe, tramite un sistema IIOT dotato di microfono MEMS incorporato. L’idea nasce dalla collaborazione con un ingegnere indiano di Valeo e dalla collaborazione con il professor Emanuele della Valle durante il mio percorso di master in “Data Science & Business Analytics” presso la Graduate School of Management del Politecnico di Milano.

<p align="center">
<img src="C:\Users\alber\Dropbox\Articoli\Immagine5.png"
     alt="drawing" width="300" />
</p>

Per la raccolta e l’analisi dei dati è stato utilizzato un sistema a microprocessore equipaggiato con microfoni embedded.  I recenti progressi nell'architettura dei microprocessori, infatti, hanno reso possibile l'esecuzione di sofisticati carichi di lavoro di machine e deep learning anche sui microcontrollori più piccoli.  L'apprendimento «edge», noto anche come TinyML, è il campo dell'apprendimento automatico quando applicato a sistemi embedded e permette importanti vantaggi nella distribuzione di algoritmi di machine learning su tali dispositivi:

•	larghezza di banda: gli algoritmi sui dispositivi edge possono estrarre informazioni significative dai dati che potrebbero altrimenti essere inaccessibile a causa di vincoli di larghezza di banda
•	latenza: i modelli su dispositivo possono rispondere in tempo reale agli input, abilitando applicazioni che non sarebbero praticabili se dipendenti dalla latenza di rete
•	economia: elaborando i dati su dispositivo, i sistemi integrati evitano i costi di trasmissione dei dati su una rete con elaborazione nel cloud
•	affidabilità: i sistemi controllati da modelli on-device sono intrinsecamente più affidabili di quelli che dipendono da una connessione al cloud
•	privacy: quando i dati vengono elaborati su un sistema embedded e non vengono mai trasmessi al cloud, la privacy è protetta e ci sono meno possibilità di abuso

Il sistema IIOT scelto supporta il TinyML ed è l’ultimo nato della famiglia Arduino: è il Portenta H7 con un micro STM32H747 dual core Cortex M7 a 480 MHz e un core M4 a 240 MHz, equipaggiata con due microfoni MEMS con beamforming avente 64 dB di S/N e sensitività omnidirezionale, una videocamera con risoluzione fino a QVGA (320x240) e consumo minore di 2mW.

L’algoritmo è stato creato tramite la web app di Edge Impulse  (https://www.edgeimpulse.com/). Sono state considerate sequenze audio campionate a 16kHz di lunghezza temporale 10s.. L’applicazione web, per ogni campione, estrae uno spettrogramma dal segnale audio usando “key features” del tipo Mel-Filterbank Energy (MFE), usato per sistemi audio non vocali. In pratica il blocco MFE trasforma un campione audio in una tabella di dati di features in cui ogni riga rappresenta un intervallo di frequenze e ogni colonna rappresenta un arco di tempo. Il valore contenuto in ogni cella riflette il valore ampiezza della gamma di frequenze associata durante quell'intervallo di tempo. Lo spettrogramma mostra ogni cella come un blocco colorato, l'intensità che varia dipende dall'ampiezza. Le “features” tempo/frequenza MFE dal segnale considerato sono ricavate applicando una sequenza di filtri triangolari su una scala Mel, dove l’idea è quella di estrarre più features nelle frequenze più basse e meno nelle alte frequenze, adattandosi bene ai suoni che possono essere distinto dall'orecchio umano.

<p align="center">
<img src="C:\Users\alber\Dropbox\Articoli\Immagine6.png"
     alt="drawing" width="300" />
</p>

Una volta determinate le features caratteristiche, la web app le trasferisce alla rete neurale in configurazione deep learning. A tale scopo viene utilizzata una CNN a 4 livelli con convoluzione 2D seguita da un livello «flat» con in uscita un classificatore a due classi: normal, abnormal. Il classificatore produce una «confusion matrix» con accuracy pari a 98,3% e F1 pari a 0,98.
Dopo la fase di verifica di bontà del modello via software, l’algoritmo è stato caricato sul device IIOT e testato in campo con risultati soddisfacenti.

### La “lesson learned”
Con la sperimentazione illustrata le Operations di Rai Way hanno compiuto il primo del lungo cammino verso il percorso “data-driven company”. Il cammino tortuoso della digitalizzazione dei processi industriali si raggiunge comunque solo quando nello scenario evolutivo siano parte integrante le persone. Se lo scopo è rendere efficiente e flessibile l’intero sistema, allora è necessario che tutti gli elementi siano orchestrati in maniera opportuna, in modo particolare gli uomini, che non potranno essere sostituiti, ma piuttosto indotti a ricoprire ruoli diversi a patto di sviluppare nuove competenze per una diversa e ottimizzata interazione uomo-macchina.
