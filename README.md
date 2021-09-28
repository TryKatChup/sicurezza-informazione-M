# Sicurezza dell'informazione 2021-2022

## Introduzione (23/09/2021)

### Scopo della sicurezza informatica

La sicurezza informatica ha lo scopo di proteggere le risorse da accessi indesiderati, garantire la riservatezza delle informazioni, assicurare il funzionamento e la disponibilità dei servizi a fronte di eventi imprevedibili.
È l’insieme dei prodotti, dei servizi, delle regole organizzative e dei comportamenti individuali che proteggono i sistemi informatici di un’azienda.

### I tre caposaldi della sicurezza informatica (CIA Trade Triangle)
Le tre proprietà da garantire per la sicurezza dei dati sono:

- **Confidenzialità**: assicura che solo chi è autorizzato può accedere (in sola lettura) a risorse o sapere dove
sono;
- **Integrità**: solo chi è autorizzato può modificare, eliminare, creare risorse;
- **Disponibilità**: solo chi è autorizzato può accedere alle risorse senza interferenze ed
ostacoli.

### Qualche concetto (paragrafo da modificare)
- Analisi Valore: quanto valgono i miei dati?
- Analisi Rischio: Quanto valgono i danni(?)
- Modello di minaccia: dipende dall'analisi del valore, chi mi attacca e perché

### Poi ha detto qualche vulnerabilità a caso, spiegando bene solo l'IP spoofing e il SYN flooding, ma il resto le ha tralasciate perché sì.
da scrivere bene dopo

---

## Introduzione + bestemmie (27/09/2021)

### Calcolatori sicuri


slide 21
Un calcolatore per essere sicuro deve essere sicuro sia a livello hardware che a livello software.
In questo corso ci si focalizza principalmente sulla "sicurezza dei dati", che consiste nel garantire i seguenti requisiti fondamentali:

- confidenzialità;
- integrità;
- disponibilità;
- autenticazione;
- non ripudio.

Quando parliamo di sicurezza dei dati, in questo corso, faremo un'assunzione fondamentale: assumeremo che il nostro hardware, firmware e sistema operativo, siano **sicuri**.
Ovviamente questa ipotesi non è sempre verificata, ma in questo corso (quando studieremo i servizi e meccanismi di sicurezza) lo daremo per scontato.

NB: la sicurezza HW e FW non è argomento proprio del corso, ma la prof ci ha dato qualche info a riguardo per sapere giusto di cosa stiamo parlando.

### Sicurezza hardware

Soprattutto negli ultimi anni, la sicurezza hardware sta emergendo in maniera preponderante; si sono scoperte vulnerabilità a livello di componenti fisici, in particolare:

- Memorie
- Periferiche
- I/O
- linee di trasmissione)

L'ambito della sicurezza hardware si occupa di proteggere il calcolatore, ma anche altri dispositivi fisici, appunto, da minacce quali furto, danneggiamento o alterazione dei componenti.

### Sicurezza firmware

Così come l'hardware, anche il firmware deve essere sicuro: ci sono diverse vulnerabilità legate al FW, specialmente recenti (anche in questo caso ci troviamo in un'area in grande espansione, soprattutto nell'ultimo periodo).

Esistono diversi meccanismi di analisi del firmware, che si dividono in

- statici
- dinamici

e che permettono di verificare che il firmware si comporti correttamente.

Il motivo per cui è importante anche la sicurezza del firmware, è dato dal fatto che, partendo dal livello applicativo, per garantirne l'_autenticità_ (ovvero che sia stato sviluppato effettivamente dall'azienda o produttore che l'ha rilasciato) e che non sia stato compromesso (ovvero che non abbia subito modifiche, quali ad esempio iniezione di software malevolo, e quindi che funzioni correttamente), c'è una catena di sicurezza, che segue diversi check:

1) Il primo check che possiamo fare è quello "di più alto livello", che sfrutta l'utilizzo di software antimalware;
2) Chi garantisce che i software antimalware siano affidabili?
3) Chi mi garantisce che il sistema operativo non sia stato corrotto?
4) Prima ancora del sistema operativo viene eseguito il bootloader, che esegue dei controlli di verifica per garantire l'affidabilità del SO;
5) A loro volta i bootloader potrebbero essere compromessi, dunque serve ancora qualcosa che ci garantisca che la fase di boot sia avvenuta con successo.

Riassumendo (partendo da livello più alto):

- Livello applicativo
- Sistema operativo
- Boot
- Hardware

In linea di principio, per garantire che l'hardware non sia compromesso, tramite il boot, esistono due metodologie:

- **Trusted boot**: tutta la fase di inizializzazione è avvenuta usando piattaforme _trusted_ (ovvero che fanno anche utilizzo di componenti ad hoc (tra cui i processori) anche crittografici, che conservano delle chiavi crittografiche tramite le quali possiamo verificare che tutti i componenti, fra cui il firmware, siano autentici e vengano avviati correttamente.

- **Secure boot**: viene usata un'interfaccia standard UEFI (Unified Extensible Firmware Interface) che garantisce, più a livello software, che la fase di boot avvenga in maniera corretta.

Tre approcci per la rilevazione tempestiva degli errori hardware e firmware:

1) **Trusted computer platform**: grandi aziende (ad esempio IBM, Intel, ecc.) si sono riunite in un'iniziativa (TCPA - Trusted Computing Platform Alliance, che ora è diventata la TCG - Trusted Computing Group) che ha come obiettivo quello di definire degli standard, in grado di impedire tramite chip aggiuntivi (Fritz) e sistemi operativi ad hoc (Nexus) che garantiscono che le configurazioni hardware e software siano avviati correttamente. Ciò garantisce una piattaforma attivata.
2) **Funzioni e regole di sicurezza**: Come controparte della soluzione precedente, c'è il problema che l'architettura diventa blindata: si è vincolati all'utilizzo di quel particolare chip con quel particolare sistema operativo (Ad esempio Apple). Come possibile alternativa si può ricorrere ad un approccio che consiste nell'utilizzo di sistemi operativi con _estensioni_ di sicurezza (es Unix, SELinux).
3) **Coprocessori** - Una terza alternativa consiste nell'utilizzo di coprocessori dedicati (anche in ambiente di comunicazioni mobili). 
Si affida a processori specifici l'esecuzione di determinate funzioni di sicurezza.

### Valutazione, Certificazione, Enti
Per poter sapere che un componente di sicurezza sia sicuro, ci deve essere qualcuno che lo garantisca.
In questo caso, occorrono degli enti di certificazione e degli standard che definiscono delle metodologie con cui andare a verificare che un progetto sia effettivamente sicuro. Applicando questi standard, gli enti ci garantiscono la sicurezza del prodotto che installiamo.

Esempi di standard internazionali per valutazione e certificazione della sicurezza: Orange book del NCSC, ISO 17799, CINI, CERT, ecc.

### Terminologia

**Meccanismo di Sicurezza (Definizione)**: meccanismo progettato per rilevare/prevenire un attacco, risanare il sistema a seguito di un attacco.

**Servizio di Sicurezza (Definizione)**: servizio che migliora la sicurezza dell'elaborazione dei dati e del trasferimento delle informazioni. Un servizio di sicurezza utilizza uno o più meccanismi.

**Attacco**: azione mirata a compromettere una proprietà critica dell'informazione.

D'ora in poi per analizzare e studiare i meccanismi di sicurezza faremo riferimento ad un modello molto specifico, chiamato "modello del canale insicuro".

Modello del canale insicuro: è un modello che ha senso (ovviamente) se ci occupiamo di sicurezza dei dati. Prevede che ci sia una sorgente dei dati, una destinazione a cui sono rivolti, e che ci sia un canale che mette in comunicazione sorgente con destinazione.
Assumiamo che:
- la sorgente abbia un ambiente sicuro (hardware e sistema operativo sicuri);
- che la destinazione abbia un ambiente sicuro;
- ma che il canale sia insicuro (ovvero che sul canale si possono inserire degli intrusori e possono fare degli attacchi passivi e attivi su tale canale).

Definito un modello di questo genere, il nostro obbiettivo è garantire che la destinazione possa consumare correttamente ed interpretare correttamente i dati inviati dalla sorgente: se la sorgente produce dati con garanzia di autenticità, la destinazione deve poter verificare l'autenticità anche in seguito alla consumazione di tali (non ripudio).

Classificazione attacchi
Gli attacchi si classificano in 2 tipologie: attacco passivo e attacco attivo.

Passivo
L'intrusore si inserisce sul canale, ma l'unica cosa che può fare è intercettare i dati (li può osservare -io intrusore mi inserisco sul canale e monitoro i dati, ma non faccio alcuna azione che modifichi/alteri il flusso-).
Questo canale può essere un bus, un canale interno offline, ma ovviamente anche un canale diretto;

Attivo
L'intrusore può accedere al canale ed alteraattivamente il normale flusso dei dati, in che modo? diversi:
-modificare il flusso intenzionalmente, per minare il contenuto dei dati (attacco all' "integrità");
-aggiungere informazioni (inserite dall'intrusore) - sto come fabbricando dei nuovi dati - la falsificazione secondo questo tipo mina l' "autenticità". Faccio credere alla destinazione che i dati da me prodotti siano prodotti dalla sorgente legittima;
-interrompere il normale flusso, impedendo che i dati arrivino alla destinazione (minaccia il requisito di "disponibilità".

Diverse contromisure:

- Impedire l'accesso al canale. Controllo dell'accesso al canale. Soluzione non scalabile e non sostenibile.
In alcuni scenari applicativi si possono mettere dei cavi dedicati(???)

- Seconda soluzione: cifrare il canale, e rendere possibile che quello che sto trasmettendo venga capito soltanto dal legittimo destinatario.
In questo corso studieremo gli algoritmi crittografici, in modo da rendere incomprensibile per un intrusore la comprensione dei dati sul canale.

- Attacchi attivi. Proprietà a rischio: integrità, autenticità.
  - io ho il normale flusso di dati e aggiungo dati in più, in modo da sapere se il flusso di dati che arriva a destinazione sia integro o meno.


### Collocazione dei meccanismi e dei servizi per la sicurezza

- Autenticazione a livello di host

- Autenticazione mi sono persa. Basta

### Trasformazioni per la sicurezza

Abbiamo bisogno di costruire algoritmi/protocolli che permettano di trasformare l'informazione originaria in qualcos'altro (non comprensibile o qualcosa di ridondante)

- algoritmi (singola trasformazione che avviene prima di mandare i dati)
- protocolli (di una serie di trasformazioni)

Esempio: io sono.

Destinazione in bonafede.

Servono più trasformazioni, perché è pieno di malintenzionati

### Crittoanalisi

- Crittografia: studia come progettare le trasformazioni che mi permettono di proprietà di sicurezza dell'informazione
- Crittoanalisi: Studia le trasformazioni che permettono di rompere la sicurezza di informazioni

### I principi dell'informazione:

- Impossibilità di sapere:
- Impossibilità di indovinare
- Impossibilità di dedurre:

Le trasformazione deve essere segreta e i calcoli devono essere impossibili.

### Passo successivo: spararsi

### Primo requisito: riservatezza

La sorgente deve trasformare la rappresentazione originaria in una che la renda apparentemente incomprensibile, e il destinatario deve essere l'unico a sapere come ritornare a una info comprensibile.

- Cifratura: trasformo testo comprensibile in testo incomprensibile (cyphertext)
- Decifratura: l'esatto opposto

La sorgente trasforma la rappresentazione originaria delle informazioni riservitare in una rappresentazione che le rende apparentemente incomprensibili; la destinazione è l'unica a sapere eseguire la trasformazione inversa.

- Integrità: rilevazione di attacchi intenzionali
La sorgente deve affiancare al documento un riassunto che ne rappresenti in modo pressoché univoco il contenuto; la destinazione deve ricalcolare il riassunto e confrontare i due dati.

Come otteniamo il riassunto? Funzioni hash

Un hash è una funzione che costruisce un attestato d'integrità

Una funzione che in uscita produce un dato inferiore in ingresso?

# ORACOLO???

![zeus](./zeus.jpg)



Hash: resistente alle collisioni: individuazione di due messaggi con la stessa impronta deve essere un calcolo difficile.

Le collisioni esistono, deve essere però difficili trovare una coppia di messaggi avente la stessa impronta.

n bit di hash : 2^n valori di uscita


Oracolo casuale

### Attestato di integrità

`A -> B: m || H`

Supponiamo che A mandi a B un messaggio m. Sul canale viaggia m concatenato con H [H(m)].

- Prelevo il dato dal canale
- Ottengo una funzione hash
- Confronto l'impronta del canale con quella di destinazione(?). Se coincidono ok

La destinazione sarà in grado di vedere se il messaggio ha avuto modifiche?

### Come vengono combinate le trasformazioni E ed H?

---

![marco togni](./marco_togni.jpg)


---
![cyber sesso](https://user-images.githubusercontent.com/56556806/134823047-da26060a-3813-4e73-a13c-256bcd0483c4.png)

# How I Defeated Fascism with the Power of Love

## Chapter 1: The Power of Love

The first step in my journey was realizing that it is impossible to defeat
fascism with the power of love.

## Chapter 2: The Power of Incredible Violence
