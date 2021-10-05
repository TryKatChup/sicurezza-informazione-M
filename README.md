# Sicurezza dell'informazione 2021-2022

<!--la data da togliereeeeee...tra due mesi viene l'angoscia di vedere quando il corso è iniziato-->
<!--Perfetto, da non modificare -->
## 01.Introduzione (23/09/2021)

### Scopo della sicurezza informatica

Il tema della sicurezza informatica è molto importante, in un mondo come quello di oggi, dove l'informatica domina buona parte delle relazioni sociali, lavorative, economiche e politiche. Questo tema è ancora più sentito con l'arrivo del COVID in cui il mondo si presta a digitalizzarsi.
La sicurezza informatica ha quindi lo scopo di proteggere le risorse da accessi indesiderati, garantire la riservatezza delle informazioni, assicurare il funzionamento e la disponibilità dei servizi a fronte di eventi imprevedibili.
Per essere più precisi, è l’insieme dei prodotti, dei servizi, delle regole organizzative e dei comportamenti individuali che proteggono i sistemi informatici di un’azienda.

### I tre caposaldi della sicurezza informatica (CIA Trade Triangle)

Le tre proprietà da garantire per la sicurezza dei dati sono:

- **Confidenzialità**: assicura che solo chi è autorizzato può accedere (in sola lettura) a risorse o sapere almeno che esse esistano;
- **Integrità**: solo chi è autorizzato può modificare, eliminare e creare risorse;
- **Disponibilità**: solo chi è autorizzato può accedere alle risorse senza interferenze ed ostacoli.

![cia](./img/img1.png)

### Terminologia

- **Vulnerabilità**: punto debole del sistema che può rendere realizzabile una minaccia;
- **Minaccia**: un atto ostile intenzionale o meno che ha un qualsiasi effetto negativo sulle risorse o sugli utenti del sistema;
- **Attacco**: qualsiasi azione che usa una vulnerabilità per concretizzare una minaccia;
- **Contromisura**: azione, dispositivo, procedura o tecnica che consente di rimuovere o ridurre una vulnerabilità.

Esempio: un ponte ha una crepa (vulnerabilità), rischia di crollare (minaccia), un peso totale eccessivo sul ponte (attacco), cercare di controllare il numero di veicoli sul ponte (contromisura).

- **Virus**: provoca danni e si replica propagato dagli umani (involontariamente);
- **Worm**: provoca danni perché si autoreplica (satura risorse) in maniera automatica, senza l'intervento dell'utente;
- **Trojan (horse)**: vettore di malware, contiene funzionalità aggiuntive impreviste;
- **Backdoor**: punto di accesso non autorizzato;
- **Rootkit**: strumenti per accesso privilegiato, nascosti (modifica di un programma, libreria, driver,
modulo kernel, hypervisor) ed invisibili.

<!-- dove c'è scritto questa roba kkkkk-->
### Qualche concetto (paragrafo da modificare)
<!--CANCELLEREI QUESTO PARAGRAFO :P-->
<!-- chi è che ha preso questi appunti? -->
- Analisi Valore: quanto valgono i miei dati?
- Analisi Rischio: Quanto valgono i danni(?)
- Modello di minaccia: dipende dall'analisi del valore, chi mi attacca e perché

<!-- dove c'è scritto questa roba kkkkk-->
### Poi ha detto qualche vulnerabilità a caso, spiegando bene solo l'IP spoofing e il SYN flooding, ma il resto le ha tralasciate perché sì.
da scrivere bene dopo <!--QUANDO VUOI...CANCELLEREI ANCHE QUESTO PARAGRAFO :P-->

---
<!-- TITOLO FAKE: non ne ho trovata manco una -->
<!-- da togliere per fare il blocco 1 tutto unito -->
## 27/09/2021

### Calcolatore sicuro

Un calcolatore per essere sicuro lo deve essere sia a livello hardware che a livello software. Ovviamente questa ipotesi non è sempre verificata, ma in questo corso quando studieremo i servizi e meccanismi di sicurezza lo daremo per scontato.

Quando parliamo di sicurezza dei dati faremo un'assunzione fondamentale: assumeremo che il nostro hardware, firmware e sistema operativo, siano **sicuri**.

In questo corso ci si focalizza principalmente sulla _sicurezza dei dati_, che consiste nel garantire i seguenti requisiti fondamentali:

- Confidenzialità;
- Integrità;
- Disponibilità;
- Autenticazione;
- Non ripudio.


<!--NB: la sicurezza HW e FW non è argomento proprio del corso, ma la prof ci ha dato qualche info a riguardo per sapere giusto di cosa stiamo parlando.-->

<!--Forse da togliere, non è importante: ci devo pensare (Karina) -->
### Sicurezza hardware

<!-- toglierei questa sezione: non viene trattata nel corso e non è oggetto di esame -->

Soprattutto negli ultimi anni, la sicurezza hardware sta emergendo in maniera preponderante; si sono scoperte vulnerabilità a livello di componenti fisici, in particolare:

- Memorie
- Periferiche
- I/O
- linee di trasmissione

L'ambito della sicurezza hardware si occupa di proteggere il calcolatore, ma anche altri dispositivi fisici, da minacce quali furto, danneggiamento o alterazione dei componenti.

### Sicurezza firmware

<!-- toglierei questa sezione: non viene trattata nel corso e non è oggetto di esame -->

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

**Meccanismo di Sicurezza**: meccanismo progettato per rilevare/prevenire un attacco, risanare il sistema a seguito di un attacco.

**Servizio di Sicurezza**: servizio che migliora la sicurezza dell'elaborazione dei dati e del trasferimento delle informazioni.

### Modello a canale insicuro

D'ora in poi per analizzare e studiare i meccanismi di sicurezza faremo riferimento ad un modello molto specifico, chiamato _modello del canale insicuro_.

Questo modello prevede che ci sia una sorgente dei dati, una destinazione a cui sono rivolti e che ci sia un canale che mette in comunicazione sorgente con destinazione.

Assumiamo che:

- La sorgente abbia un ambiente sicuro (hardware e sistema operativo sicuri);
- La destinazione abbia un ambiente sicuro (hardware e sistema operativo sicuri);
- Il canale sia insicuro, ovvero che sul canale si possano inserire degli intrusori e possono fare degli attacchi passivi e attivi su tale canale

Definito un modello di questo genere, il nostro obiettivo è garantire che la destinazione possa consumare ed interpretare correttamente i dati inviati dalla sorgente: se la sorgente produce dati con garanzia di autenticità, la destinazione deve poter verificare l'autenticità anche in seguito alla consumazione di tali (non ripudio).

**Mmmm non mi convince la def di non ripudio**

### Classificazione attacchi

Gli attacchi si classificano in due tipologie:

- **Passivo**: l'intrusore si inserisce sul canale, ma l'unica cosa che può fare è intercettare i dati senza alterarne il flusso. Questo canale può essere un bus, un canale interno offline, ma anche un canale diretto. Viene minato il requisito di _disponibilità_.
<!-- che cosa è un canale interno offline?-->
- **Attivo**: l'intrusore può accedere al canale ed alterare il normale flusso dei dati. Può:
  - Modificare/Aggiungere il flusso intenzionalmente per cambiare il contenuto dei dati. Viene minato il requisito dell'_integrità_;
  <!--- Aggiungere informazioni, in modo da evitare la falsificazione che mina all'integrità dei dati. La destinazione deve avere un controllo che garantisca la legittimità della fonte-->
  - Interrompere il normale flusso impedendo che i dati arrivino alla destinazione. Viene minato il requisito di _disponibilità_.
  - Venire a conoscenza del flusso di dati senza modificare il contenuto. È un attacco passivo. Viene minato il requisito della _confidenzialità_.

<!-- una volta basta e avanza metterlo-->
<!--Ricapitolando per tipo di attacco e proprietà che mette a rischio):

- **Attacchi passivi**: mina confidenzialità e autenticazione. Autenticazione? DA DOVE ESCE FUORI?
- **Attacchi attivi**: integrità, autenticità e disponibilità-->

### Contromisure
Esistono 3 tipologie di contromisure per gli attacchi:

- **Prevenzione**: tramite cui si previene la possibilità che un dato venga intercettato;
- **Rilevazione**: tramite cui si rileva un attacco in corso;
- **Reazione**: tramite cui si reagisce dopo che un attacco è già avvenuto.

Il tipo di contromisura da adottare va scelto anche in base al sistema e a cosa vogliamo proteggere (nel nostro caso ci interessano i dati). Se ad esempio i dati sono non confidenziali, non ci interessa che vengano intercettati. Invece, se i dati non sono riservati, non sarà necessaria la prevenzione.

Come ingegneri (LOL https://youtu.be/EOR8Uz27s3Y?t=420), il nostro obiettivo è capire a fronte di più possibilità progettuali, quale ha più senso per il nostro sistema ed i nostri dati da proteggere.

**Possibili contromisure per attacchi passivi**:

L’unica contromisura da utilizzare è la prevenzione. Non ha senso utilizzare la tecnica della rilevazione in quanto quando lo rilevo ormai è tardi e non ha più senso intervenire perché l’informazione è stata ormai violata.

- Impedire l'accesso al canale. Questo viene implementato tramite l'utilizzo o di canali dedicati, oppure mettendo in piedi meccanismi di controllo dell'accesso su larga scala, che fanno in modo che ogni volta che una sorgente accede al canale, il  meccanismo chiede di autenticasi. Per come è realizzata, questa soluzione non è tuttavia economicamente sostenibile né scalabile;
- Criptare i dati da inviare, ovvero rendere incomprensibili i dati trasmessi, tranne al destinatario legittimo.

**Possibili contromisure per attacchi attivi**:

Le contromisure da adottare sono rilevazione e reazione.

Contro gli attacchi attivi, in linea di principio avrebbe senso adottare una contromisura preventiva, in quanto protegge l'autenticità, l'integrità e la riservatezza, ma come si può prevenire un attacco al flusso di dati, che è in corso? Possibili modi:
- Controllo dell'accesso al canale, si può fare ma ovviamente ci sono sempre gli svantaggi specificati in precedenza;
- Attestazione di integrità e origine. Se è necessaria una contromisura di rilevazione, per permettere alla destinazione di sapere se quel flusso di dati è corretto o no, si può utilizzare un certificato di integrità/autenticità. In questo caso la rappresentazione dei dati non è incomprensibile, ma al normale flusso dei dati aggiungo dati in più che permettono alla destinazione di capire se il flusso è integro e autentico, oppure è stato manomesso. Esistono dei meccanismi crittografici che permettono di ottenerli.


Collocazione dei meccanismi e dei servizi per la sicurezza
se il meccanismo viene collocato a livello applicativo è molto personalizzabile ma richiede manutenzione

Trasporto è più trasparente alle applicazioni;

Livello di rete è completamente trasparente, ma è meno personalizzabile rispetto alle esigenze delle applicazioni

A seconda del livello avrò prestazioni, personalizzazione e trasparenza alle applicazioni diverse.

---
## 01.Dati Sicuri

Per proteggere i dati a fronte di possibili attacchi possiamo eseguire o delle singole trasformazioni usando degli _algoritmi_ o a volte è necessario un insieme di trasformazioni. In questo caso, ovviamente la sequenza delle operazioni da eseguire non può essere casuale ma ben precisa e parliamo di _protocollo_.

Quando progetto un protocollo mi devo chiedere sempre se la sorgente e destinazione siano stati compromessi però nel modello di minaccia più semplice che abbiamo assunto questo problema non c'è.

Ad esempio, compro una casa a 100mila euro. Per comprarla introduco un
protocollo di sicurezza per trasmettere l'informazione della compravendita. Se
sorgente e destinazione si comportano correttamente, mi basta un protocollo che
mi garantisca l'integrità di quel dato ma se la sorgente è compromessa, può
alterare il prezzo. In questo caso il protocollo di protezione deve diventare
più complesso affinché la sorgente e destinazione possano disconoscere
l'operazione.

Non è detto che ci sia sempre solo sorgente e destinazione ma in alcuni casi è
necessario l'intervento di una terza entità che fa da arbitro/giudice. La si può
usare quando sorgente e destinatari sono malintenzionati.

Per ottenere la sicurezza dei dati ho bisogno di **ridondanza** sia nello spazio
che nel tempo. Questo vuol dire che le trasformazioni hanno bisogno di bit in
più di quelli che servirebbero (ridondanza nello spazio) e la
sorgente e la destinazione hanno bisogno di più tempo per processarle, sia in
termini di banda che di calcolo computazionale (ridondanza nel tempo).

## Crittografia e Crittoanalisi

- **Crittografia**: è la disciplina che studia gli algoritmi che possiamo adottare per proteggere i dati in in termini di riservatezza, autenticità e integrità e per garantire l'identificazione;
- **Crittoanalisi**: è la disciplina che studia il modo in cui è possibile violare le trasformazioni che proteggono i dati

Nel corso studieremo solo la crittografia. Quando studieremo una trasformazione crittografica, dovremmo capire la sua:
- **Efficacia**: quanto è in grado la trasformazione di proteggere quel dato in termini di riservatezza, autenticità e integrità;
- **Efficienza**: l'overhead associato.

## I principi della difesa

Ci sono tre principi che guidano la progettazione delle trasformazioni:

- Deve essere impossibile _sapere_ che trasformazione è stata eseguita;
- Deve essere impossibile _dedurre_ qual è la trasformazione adottata;
- Deve essere impossibile _indovinare_ la trasformazione adottata.

Quando dobbiamo progettare una trasformazione bisogna fare in modo che essa sia
segreta e che l'intruso, che non conosce la trasformazione segreta, non possa
disporre di un algoritmo alternativo che sia in grado di eseguire la stessa
trasformazione in un tempo computazionalmente fattibile.

## Proteggere la proprietà di confidenzialità

Come facciamo a progettare una trasformazione capace di rendere confidenziali i dati? La trasformazione deve avere come caratteristica quella di trasformare le informazioni che noi vogliamo proteggere in una rappresentazione che la renda incomprensibile. L'unica identità che può eseguire l'operazione inversa, cioè dal dato incomprensibile al dato originale, è la destinazione. Dunque, la riservatezza la possiamo ottenere con una trasformazione di tipo preventivo in modo che se un intruso accede ai dati non li può capire.

![confidenzialità](./img/img2.png)

La sorgente `A` non può mettere i dati `m` sul canale insicuro per ovvi motivi
ma deve prima trasformarli tramite un'encryption `E`. Questa trasformazione la
conosce solo la sorgente `A` ed è l'unica in grado di eseguirla. Nell'esempio
della figura i dati `m`, vengono trasformati in dati incomprensibili `c`. Solo
la destinazione `B` li può comprendere perché quando li riceve, deve essere in
grado tramite la trasformazione di decryption, risalire al contenuto dei dati
`m`.

La coppia di encryption e decryption costituisce il **cifrario**. L'intruso `I`
non è in grado di risalire al contenuto per diversi motivi:
- non conosce la trasformazione di encryption;
- non conosce una trasformazione alternativa ed equivalente a quella di decryption;
- non può neanche indovinarla perché da un punto di vista computazionale è un'operazione molto costosa.

Altro punto importante è che bisogna produrre un **testo cifrato aleatorio**: l'intruso osservando `c` non deve imparare nulla di più di quello che sapeva già. Ad esempio, ho dei  messaggi strutturati che iniziano con "carissimi studenti, carissimi studentesse". Se applico una trasformazione che mi consente di ottenere in uscita la parola "carissimi" riesco a vedere che c'è un pattern tra tutti i messaggi e ciò mi rende il cifrato non perfetto perché io intruso ho un'informazione in più e potrei studiare come fare a capire il resto del messaggio.

Altre considerazioni:
- Lo schema della figura può essere applicato sia da A verso B che da B verso A (il flusso è bidirezionale);
- A e B possono essere online contemporaneamente oppure A online e B offline cioè i messaggi possono essere decifrati in momenti diversi;
- B = A. La sorgente potrebbe coincidere con la destinazione. Se voglio cifrare dei dati sul mio hard disk li cifro per me. Quando faccio il logout dal sistema, li voglio cifrare mentre quando faccio il login li decifro.

## Proteggere la proprietà di integrità

Quando si trasferiscono i dati sul canale, come visto in corsi precedenti, si sa che a causa di disturbi i bit possono mutare. In caso di disturbi, le alterazioni che si possono osservare sono la cancellazione e la modifica di bit. Ci sono dei disturbi che rendono più probabile certi tipi di alterazioni. Infatti, è possibile calcolare la probabilità.

Invece, nell'ambito della sicurezza informatica, non si parla di disturbo ma di attacco intenzionale attivo. Minare l'integrità significa fare un attacco attivo sul canale. L'attacco attivo condivide con i disturbi il fatto di poter modificare e cancellare i messaggi ma è diverso dal disturbo perché aggiunge il problema di alterare l'ordine dei bit.

Se nei disturbi c'è una probabilità di alterazione dei dati, ad esempio del 30%, nella sicurezza informatica tutti i bit hanno la stessa probabilità di essere cambiati.

Proteggere l'integrità vuol dire costruire delle trasformazioni in grado di rilevare modifiche al contenuto dei dati trasmessi. In questo caso, la contromisura da adottare è quella della rilevazione perché le modifiche ai messaggi sul canale non possono essere evitate ma apportando tecniche in grado di far dire alla destinazione che il messaggio sia stato davvero alterato si riesce a superare questo problema.

Se vogliamo costruire una trasformazione che protegga l'integrità, dobbiamo far si che la sorgente utilizzi ridondanza al messaggio e affianchi al dato iniziale un'informazione aggiuntiva che deve essere costruita opportunamente. Questa informazione aggiuntiva si chiama **riassunto** o **impronta**. La dimensione deve essere limitata perché la si deve poi trasmettere.

La sua caratteristica deve essere quella di rappresentare in modo pressocchè univoco il contenuto del messaggio. Al messaggio originale deve corrispondere un unico riassunto. Se i messaggi da inviare sono diversi ovviamente i riassunti devono essere anche loro diversi. La destinazione riceve il dato e il riassunto. Poi ha bisogno di ricalcolare sul dato ricevuto un nuovo riassunto e vede se coincide con quello ricevuto. Se coincidono vuol dire che il dato non è stato alterato.

E' importante che il riassunto debba avere delle caratteristiche specifiche. Esse si ottengono solo usando **funzioni hash crittograficamente sicure**.

In generale, una funzione hash (`H`) è una funzione che prende un dato `m` di lunghezza arbitraria e restituisce in uscita un'impronta `H(m)` di dimensione nettamente inferiore.

A noi non basta avere una qualunque funzione hash, ma è importante che abbia due caratteristiche:
- **Comportamento da "oracolo casuale"**: se decido che l'impronta sia costituita da `n` bit, le possibili uscite della funzione hash sono `2^n`. Preso il mio messaggio `m`, devo fare in modo che la probabilità che esca un uscita rispetto ad un'altra sia la stessa. Dato un messaggio, non devo sapere che ad esempio la probabilità che esca una determinata impronta sarà al 70% ma la probabilità che mi capiti una configurazione rispetto ad un'altra deve essere la stessa;
- **Resistente alle collisioni**: è inevitabile che due messaggi diversi abbiano in uscita la stessa impronta perché lo spazio di input è molto più grande dello spazio di output (`m > n`). L'importante è che per un intruso sia computazionalmente difficile individuare due messaggi che abbiano la stessa impronta.

![zeus](./img/zeus.jpg)

Queste caratteristiche le si ottengono solo usando **funzioni hash crittograficamente sicure**.

![integrità](./img/img3.png)

Se il mio obiettivo è rilevare i disturbi, posso usare delle funzioni hash che chiamiamo **funzioni hash semplici**. Invece, se il mio obiettivo è la sicurezza informatica, le funzioni hash devono essere crittograficamente sicure e prendono il nome di **funzioni hash sicure** (vedi proprietà scritte in alto).

#### Attestazione di Integrità

L'obiettivo di un intrusore è quello di trovare un messaggio `m'` che abbia
`H(m') = H(m)`. Dunque, è fondamentale usare una funzione hash
crittograficamente sicura che sia resistente alle collisioni.

`A -> B: m||H(M)`

Supponiamo che `A` metta sul canale insicuro un messaggio `m`, a partire dal
quale è stato costruito `H(m)` attraverso `H` (una funzione hash
crittograficamente sicura).\
`B` deve prendere il messaggio ricevuto, applicargli la funzione hash, che
conosce anche lui, e verificare che l'hash ricevuto coincida con quello ottenuto
applicando a sua volta la funzione hash.\
Se si equivalgono, il messaggio è stato trasmesso correttamente. In questo modo la
destinazione è in grado di rilevare se il messaggio ha subito modifiche.

![attestazioneIntegrità](./img/img4.png)

In questo scenario un intruso può sostituire il messaggio (`m`) con un altro
(`m'`). La sorgente deve utilizzare la funzione `H`, deve costruire il riassunto
univoco e consegnarlo su un canale sicuro. Ad esempio, un canale ad hoc. La
destinazione riceve `m'`, ricava `H(m')` e va a confrontare `H(m')` con `H(m)`
che ha ricevuto sul canale sicuro. Se i due valori di hash coincidono allora i
messaggi sono conformi.

## Esempio

Abbiamo quindi 2 tipi di trasformazioni, encryption ed hash, che possono anche essere combinate. Ad esempio, per garantire la riservatezza e l'integrità dei
dati è possibile utilizzarle entrambe in questo modo:

`p = m || H(m)` 

`c = E(p)`

`p* = D(c*) = m* || H*(m)`

`H*(m) =? H(m*)`

Dato che le proprietà da garantire sono due, ho bisogno di combinare più trasformazioni e le regole che devo usare devono essere precise. Per questo ho bisogno di un protocollo. Se hai dubbi, vedi la definizione scritta in precedenza.

Il seguente protocollo è costituito da tre passi:
- La sorgente esegue due trasformazioni:
  - Passo 1: la sorgente applica la funzione hash crittograficamente sicura e la concatena con il messaggio.
  - Passo 2: la sorgente applica la funzione di encryption. Sul canale insicuro viene trasferito c.
- La destinazione esegue una trasformazione:
  - Passo 3: la destinazione riceve c. c può essere o quello inviato dalla sorgente o un altro che è stato modificato dall'intruso. Per questo motivo, dato che non abbiamo una certezza, indicheremo c con c*. La destinazione applica la funzione D su c* ottenendo di nuovo `m* || H*(m)`.
  - Passo 4: Per vedere se il messaggio è integro, devo verificare che la funzione crittograficamente sicura di m* coincide con H*(m). Se non coincidono il messaggio viene scartato. L'intrusore può modificare a caso i bit del cifrato perchè se tutte le proprietà sono rispettate non può fare assolutamente nulla.

Alcune considerazioni:
- **Efficienza computazionale**: la sorgente effettua due trasformazioni (encryption e la funzione H). La destinazione esegue sempre due trasformazioni (decryption e la funzione H).

## Esempio 2

In questo caso, la proprietà di riservatezza non viene rispettata mentre quella di integrità si:

`p = m`

`c = E(p) || H(m)`

`p* = D(c*) = m* || H*(m)`

`H*(m) =? H(m*)`

Solo il messaggio viene encryptato mentre la funzione hash crittograficamente sicura è nota.

L'intrusore può:
- Vedendo la stessa H(m) sa che la sorgente sta ritrasmettendo più volte lo stesso messaggio. Dunque, si possono ricavare delle informazioni. Se ad esempio, due innamorati si inviano spesso dei messaggi si iniziano a fare previsioni su quello che si possono mandare;
- Dato lo stesso messaggio, l'impronta è sempre la stessa, quindi si possono fare dei tentativi. Se ad esempio, queste due persone, si incontrano un giorno in particolare, si può iniziare a calcolarsi la funzione hash crittograficamente sicura di lunedì, poi di martedì e confrontarla con H(m) inviata nel messaggio.

## Esempio 3

In questo caso, la proprietà di integrità non viene rispettata mentre quella di riservatezza si:

`p = m`

`c = E(p) || H(E(p))`

La riservatezza è rispettata perchè a fronte di messaggi uguali ho un H diverso perchè il cifrato è diverso.

In questo caso viene inviato sul canale il messaggio cifrato e l'impronta costruita sul messaggio cifrato.

Un intruso può:
- modificare E(p) e ottenere E*(p) e sostituire H(E(p)) con H(E*(p)). Se m è un messaggio senza un particolare significato (ad esempio un numero), D(E(p)) restituisce m* e la destinazione potrebbe non accorgersi che m* non è corretto. Se invece m è un messaggio dotato di significato la destinazione potrebbe accorgersi che m* non ha senso e quindi non accettarlo per buono.

Alcune considerazioni:
- **Efficienza computazionale**: la sorgente effettua due trasformazioni (encryption e la funzione H). La destinazione deve verificare l'integrità (la funzione H). Se non è integro non ha senso effettuare la decryption. Dunque, può risparmiare una trasformazione.

## Proteggere la proprietà di autenticazione (=autenticità?)

Chi riceve un dato è importante che possa sapere chi è stato ad originarlo. L'intruso può creare ad hoc un messaggio, inserirlo nel flusso normale dei dati e spacciarlo come se provenisse dalla sorgente originale. Questo attacco non lo si può prevenire ma solo rilevare. Per garantire l'autenticità di una sorgente, devo costruire una trasformazione `S` che dato un messaggio `m`, deve produrre in uscita un **attestato di autenticità** `c` che rappresenta in maniera non imitabile il messaggio `m` originale. Nessuno deve essere in grado di effettuare questa trasformazione.

La destinazione riceve sia il messaggio che l'attestato di autenticità ed effettua una trasformazione `V` sull'attestato di autenticità producendo in uscita una risposta che dice se il messaggio è autentico o no. In caso affermativo si recupera il messaggio `m` altrimenti lo si scarta.

![autenticazione](./img/img5.png)

La trasformazione `S` deve essere segreta perché altrimenti altri potrebbero spacciarsi per quella sorgente. I calcoli per costruire un messaggio autentico devono essere difficili da un punto di vista computazionale.
Invece, `V` può essere noto perché qualsiasi destinazione deve essere in grado di dirmi se l'attestato è autentico o no.

Alcune considerazioni:
- A e B non è detto che siano online: B non è detto che sia online perchè può verificarlo in un secondo momento;
- B = A. Se nel file system voglio che i file siano quelli che ho scritto. Quando faccio logout e login oltre a decryptarli verifico che siano anche autentici.

# 29/09/2021
<!-- Nooooooo abbiamo fatto una stessa parte! -->

<!-- Uguale -->
## Garantire la confidenzialità dell'informazione

Si cifra il codice con una funzione di Encryption ed una funzione successiva di Decryption.

`E -> Encryption`

`D -> Decryption`

`Plaintext -> E -> Chypertext -> D -> Plaintext`

L'operazione `D` deve essere computazionalmente difficile. L'intrusore non deve essere in grado di ricavare il testo in chiaro, poiché decifrare i dati deve essere computazionalmente difficile.
La sicurezza perfetta si ha quando, intercettato il chypertext, l’intrusore non riesce ad imparare nulla di più
rispetto a quello che conosce al momento dell’intercettazione del testo cifrato.

<!-- Uguale -->
## Garantire l'integrità dell'informazione

Bisogna garantire l’integrità (rilevazione e reazione)

Con un attacco attivo si possono cancellare e modificare i dati, oltre che modificarne anche l’ordine.

Il disturbo invece non cambia l’ordine dei dati dell’informazione. Tutte le alterazioni avvengono con uguale probabilità.

Proteggere l’integrità significa creare delle contromisure per la rilevazione di eventuali modifiche al contenuto del dato originale.

Si utilizza la ridondanza dei dati, cioè insieme all’informazione viene aggiunto un piccolo riassunto (un riassunto di grandi dimensioni causerebbe overhead) che identifica in maniera univoca possibilmente l’informazione. La destinazione riceverà l’informazione più il riassunto che la sorgente ha creato.

Grazie al _riassunto_, si può capire se l'informazione è corretta o se è stata modificata. Il riassunto viene creato con una funzione hash, e per riuscire ad identificare un’informazione in maniera univoca deve essere una funzione hash crittograficamente sicura.

Una funzione hash (M) prende in ingresso un messaggio `m` di lunghezza arbitraria e generano un’uscita chiamata _impronta_, detta anche `H(m)`.

Per essere _crittograficamente sicura_ una funzione hash deve avere due caratteristiche principali:

- Deve avere un comportamento da _oracolo casuale_, cioè rispondere a ogni domanda con una risposta casuale scelta uniformemente dal suo dominio di uscita. Se la domanda viene ripetuta, la risposta sarà la medesima, dato che è stata assegnata precedentemente dall'oracolo.

- Deve essere resistente alle collisioni. Se due messaggi `m1` e `m2` hanno la stessa impronta (cosa molto possibile poiché lo spazio di input è molto minore dello spazio di output), per un intruso deve essere computazionalmente difficile trovare un messaggio `m2` con impronta `H(m2)` uguale a quella di `m1`, cioè `H(m1)`.

<!-- Uguale -->
## Garantire autenticità

Per garantire autenticità si ricorre all'operazione di firma (Sign), che produce un certificato di autenticità e che viene inserito e inviato insieme al testo dell'informazione eventualmente cifrato. La destinazione avrà una funzione V di Verify (V) utilizzata per verificare se il certificato è effettivamente autentico e per ricavare il mittente.

Viene utilizzato per rilevare _fabrication_, un attacco attivo in cui l'intrusore crea un messaggio dichiarandolo come proveniente da una sorgente legittima.

Vengono quindi rispettati due principi:

- **Trasformazioni segrete**: in questo caso l'operazione di Sign. Nessun altro, oltre alla sorgente legittima, deve conoscere la trasformazione che è stata applicata, altrimenti chiunque può effettuare _fabrication attack_.
<!-- toglierei chiunque può effettuare _fabrication attack_. -->

- **Calcoli impossibili**: i calcoli per costruire un messaggio apparentemente autentico e senza conoscere la trasformazione della sorgente devono essere complessi.

Esistono 2 schemi alternativi per realizzare sign-verify: _la firma digitale_ e _hash_.

### Firma digitale

![firmadigitale](./img/img6.png)

La sorgente prende il messaggio `m` e lo sottopone a una trasformazione `H`, costruendo l’impronta `H(m)`, che garantisce l’integrità. <!--Ricordiamo che per garantire solo questa proprietà, l'attestato di integrità viene inviato su un canale sicuro. Però vogliamo garantire sia integrità che autenticazione.-->

La funzione `S` di _sign_ viene eseguita su `H(m)`, e sul canale di comunicazione insicuro viene trasmesso `m` concatenato con `S(H(m))`.

<!--aggiunto -->
La destinazione verifica tramite V che c proviene dalla sorgente leggittima. In questo modo verifico l'autenticità del messaggio. Dato che c contiene H(m) posso verificare anche la proprietà di integrità.
<!--aggiunto -->

<!--non ripudiabilità: la sorgente a è l'unica che esegue s e non può disconoscere in un secondo momento l'attestato di autenticità-->

<!--Sul canale insicuro possono viaggiare m || c-->

Il canale in questo modo viene reso sicuro e viene garantita anche la non ripudiabilità (la destinazione ottiene il messaggio dal canale non direttamente interpretabile). In questo caso la funzione `S` di Sign è segreta ed è conosciuta solamente dal mittente A che _firma_ il messaggio.

<!-- più corto il titolo secondo me-->
### Hash applicata al messaggio concatenato con un segreto S, condiviso tra sorgente e destinazione

![hashs](./img/img7.png)

Due entità `A` e `B` (mittente e destinatario) condividano un segreto `s`. `A` calcola `H(m || s)` a partire da `m`, cioè il messaggio che si vuole trasferire, e invia alla destinazione `m || H(m || s)`. 

La destinazione riceverà il messaggio `m*` e andrò a calcolare `H(m* || s)` e
se è uguale a quello ricevuto le due proprietà sono state garantite.

In questo caso non viene garantito il _non ripudio_, poiché la sorgente `A` potrebbe sospettare che la destinazione `B` si sia costruita da sola un segreto e che la sorgente `A` in realtà non abbia inviato nulla. Questo è dovuto al fatto che `A` e `B` condividono un segreto e quindi non si è in grado di risalire a
chi ha effettivamente generato il segreto.

Questo schema risulta essere più efficiente rispetto alla firma digitale, ma potrà essere usato solamente quando si è sicuri del corretto comportamento di `A` e `B`.
Può essere utilizzato ad esempio con sistemi IoT che richiedono consumi ridotti di batteria e alta efficienza.

Viceversa, la firma digitale è meno efficiente poiché ha anche la funzione di _sign_ (`S`) ma garantisce il _non ripudio_.

#### Esempi di applicazioni di procolli

- **SSL**: adotta le funzioni hash crittograficamente sicure con un segreto per costruire il certificato di autenticità. Il messaggio viene concatenato al certificato e cifrato dal client.
Si prende il messaggio, si cifra e si manda il cifrato concatenato con l'attestato di autenticità costruito sul messaggio.

- **SSL IPsec**: protocollo SSL a livello di trasporto (TCP). Vengono creati socket sicuri in cui i messaggi sono autenticati. In fase di invio, il messaggio viene cifrato e autenticato, mentre in fase di ricezione viene controllato l'attestato di autenticità e decifrato il messaggio.
La ricezione è efficiente: viene risparmiata una trasformazione una trasformazione. Se il cifrato ha subito delle modifiche, chi riceve verifica il certificato e, se qualche operazione illegale è avvenuta, si evita l'operazione di decifratura.

- **SSH**: permette di aprire shell remote sicure.
Si prende il messaggio, si cifra e si manda sul canale insicuro il cifrato concatenato con l'attestato di autenticità costruito sul messaggio.

### Esempio

slide 11

### Esempio 2

slide 12

## Anonimato/Identificazione

Altro requisito importante è l'anonimato, opposto all'identificazione.

Per _identificazione_ si intende un insieme di azioni che richiedono di identificare chi sta partecipando a un'interazione. Ad esempio, per un pagamento o quando si accede a certe risorse, in base alla persona si possono avere tipi di accesso diversi.

Il processo di identificazione ha le seguenti caratteristiche:

- **Efficienza**: l’identificazione di una entità deve avvenire in maniera _efficiente_;
- **real-time**: l'identificazione deve avvenire in un **preciso** istante e non in un instante successivo;
- **Sicurezza**: possono essere presenti:
  - **Falsi positivi**: una determinata persona ha diritti di accesso, ma non riesce ad accedere. Ciò causa inefficienza. Bisogna minimizzare questo numero;
  - **Falsi negativi**: l'accesso viene effettuato da persone non autorizzate (si spacciano per chi non sono xD). Non bisogna averli.

Un sistema di identificazione si può basare su:

- **Conoscenza**: sistemi che si basano sulla conoscenza di un'informazione. Ad esempio, password, pin, chiavi di sicurezza;
- **Possesso**: sistemi che si basano sul possesso di un oggetto che solo quella persona può avere. Ad esempio, carte magnetiche, token, smart card;
- **Conformità**: sistemi che si basano su una caratteristica di un'entità. Ad esempio, dati biometrici come impronte o analisi della retina.

E' possibile che un sistema abbia anche più sistemi di identificazione. Ad esempio, conoscenza e possesso oppure conoscenza, possesso e conformità.

E' importante ricorda che l'identificando e il verificatore debbano essere online: non posso identificare in un secondo momento perchè altrimenti come faccio ad accedere?

La robustezza di un sistema di identificazione è maggiore se vengono combinati più principi. A seconda dell'informazione che voglio proteggere si sceglierà il sitema più adatto perchè ci sarà un costo computazionale, di gestione etc.

<!-- anonimato: ad esempio, il voto elettronico o monete elettroniche-->

### Protocollo di identificazione

![kronk](/img/img8.png)

Qualunque protocollo di identificazione prevede:

- **Registrazione**: l'identificando condivide con il verificatore la prova d'identità. Il verificatore deve memorizzarla perchè quando l'identificando si dovrà identificare la dovrà confrontare. In questa fase, l'identificando dovrà scegliere un qualcosa che solo lui sa e deve usare una funzione F capace di prendere quel segreto che porta alla costruzione della prova d'identità. Il verificatore memorizza il _termine di paragone_ o _prova d'identità_ (F(s)). La funzione F cambia a seconda del modello di minaccia. Non è detto che identificando e verificatore abbiano la stessa funzione perchè il verificatore poi potrebbe spacciarsi per lui. Se il verificatore si comporta correttamente in questo caso identificando e verificatore condividono lo stesso segreto s. In caso contrario, l'identificando conoscerà solo lui il segreto e quello che fornirà sarà una prova d'identità che è solo l'identificando è in grado di produrre e il verificatore non potrà costruirne una nuova.
- **Identificazione**: l'identificando e il verificatore siano entrambi online. Univocità del tempo e dell'entità.
Questo processo può scomporsi in:
  - **Dichiarazione**: l'identificando dichiara chi è. L'identificando dovrà effettuare una trasformazione T1,1. Il verificatore eseguirà una trasformazione T1,2 e interroga.
  - **Interrogazione**: interroga l'identificando per dimostrare che sia davvero lui chi dice di essere
  - **Dimostrazione**: se l'identificando fornisce la stessa prova d'identità che aveva fornito in fase di registrazione vuol dire che è proprio lui.

![kronk](/img/kronk.jpeg)

Un intrusore può:

- Dedurre o indovinare la prova di identità;
- Rubare il dispositivo;
- Replicare una prova di identità che ha viaggiato sul canale in una legittima transizione di identificazione e riutilizzarla.

Modello di minaccia semplice: verificatore si comporta bene e in questo caso posso memorizzare il segreto
Modello di minaccia in cui il verificatore non si comporta correttamente: non vogliamo che conosca il segreto. Memorizza una trasformazione del segreto F(s).
Che caratteristiche deve avere la funzione F?
Non essere invertibile: l'identificando può generare F(s) mentre il verificatore non riesce a generare F^-1(s)

La trasformazione T3.1 deve essere segreta cioè solo l'identificando deve conoscerla altrimenti tutti si possono spacciarsi per l'identificando.

## Funzioni one-way

Una funzione f è detta unidirezionale se:
- è invertibile
- facile da calcolare. dato lo spazio di input x è facile calcolare f(x)
- è difficile dato f(x) risalire alla x che ha originato l'output

Ad esempio, sono funzioni unidirezionali:
- la funzione hash crittograficamente sicura;
- funzione di cifratura: chi non conosce la funzione D è difficile risalire al dato che è stato cifrato;
- funzione di verifica di firma digitale: la funzione V è facile da eseguire ma chi non conosce la funzione S non è in grado di generare un messaggio correttamente verificabile.

Un altro esempio è l'elenco telefonico: dato un cognome di una persona è facile risalire al numero telefonico. Il contrario invece è assolutamente difficile.

Per garantire alcune proprietà di sicurezza, abbiamo bisogno che le trasformazioni siano unidirezionali. Nella teoria matematica, non esiste una funzione che sia unidirezionale. Nella pratica, invece, sono state individuate molte funzioni che sono candidate ad avere un comportamento di unidirezionalità. Vengono chiamate pseudo-unidirezionali perchè se non si possiede un'informazione non è possibile trovare la funzione inversa.

## Trasformazioni segrete

- **Trasformazione segreta**: ad esempio, tutte quelle volte che vogliamo proteggere la riservatezza dei dati (E e D), la trasformazione della sorgente con cui autentico i dati (S), trasformazione con cui genero la prova d'identità. Possiamo avere tre approcci:
  - macchine a funzionamento segreto: non conoscere come è formata la macchina. Ad esempio, Macchina Enigma. 
  - Algoritmo: le operazioni stesse sono segrete. Ad esempio, gli algoritmi delle prime SIM, algoritmi USA durante la guerra fredda;
  - Parametro: la macchina e l'algoritmo sono noti ma un parametro di ingresso dell'algoritmo (chiave crittografica);

  I primi due approcci non funzionano molto bene:
  - No manutenibilità: è impossibile che non si possa violare la segretezza di una macchina o di un algoritmo. Non è immediato ripristinare la sua sicurezza perchè dovrei riprogettare tutto da zero.
  - No scalabile: non si può pensare questo approccio su grande scala come internet
  - No Certificazione: è bello avere in casa qualcosa di cui non si conosce nulla? Nessuno mi può garantire che quello che sto usando è sicuro

Dunque, l'approccio usato al giorno d'oggi è il terzo. D'ora in poi l'approccio che useremo è trasformazione nota con parametro segreto (chiave)

![chiave](/img/img9.png)

- Con T indicheremo la trasformazione che ha funzionamento pubblico (quindi anche l'intrusore) ma i parametri non sono noti (delle trasformazioni E, D e da S);
- Con k indichiamo la chiave cioè il parametro non noto ed è un parametro di ingresso;
- Con spazio delle chiavi intendiamo l'insieme delle 2^n possibili configurazioni dove n è il numero di bit. La chiave è costituita da una delle 2^n configurazioni. Più è grande n più è difficile per un intrusore indovinare la chiave.

## Algoritmo forza bruta

![intrusore](./img/img10.png)

Un intrusore può sempre disporre algoritmo di ricerca esauriente noto come algorimo forza bruta. Se io intrusore non conosco la configurazione scelta dalla sorgente leggittima per il segreto posso esplorare tutto lo spazio delle chiavi. Se n è il numero di bit della chiave e 2^n è il numero totale di configurazioni, dato che non so la chiave provo tutti i tentativi fino a quando non la indovino. Ovviamente devo conoscere la trasformata T. Se il cifrato che ottengo è uguale a quello sul canale vuol dire che sono riuscito a trovare la configurazione corretta.

## relazioni fra le chiavi

In base a come sono fatti i parametri che diamo in pasto agli algoritmi possiamo individuare due famiglie di cifrari:
- **cifrari a chiavi simmetriche**: le trasformazioni E(), S) e D(), V). La trasformazione E e D sono note. La trasformazione E deve prendere in ingresso il parametro ks mentre la trasformazione D prende come parametro di ingresso kd. Se le chiavi ks e kd sono uguali o sono o uguali o facilmente calcolabili una dall’altra: ks = kd.
Se prendiamo la coppia del cifrario E e D, quando cifro userò una chiave ks e quando decifro userò ks. Ciò implica che le due entità in gioco conoscano lo stesso segreto. Tuttavia, ks e kd deve essere *segreto*. Questo tipo di cifrario si usa per garantire riservatezza. Caso molto raro è quello di costruire un attestato di autenticità;
- **cifrari a chiave pubbliche**: le chiavi ks e kd sono diverse e una delle due è difficilemnte calcolabile dall'altra. Questo tipo di cifrario si usa per garantire riservatezza e autenticazione.
kd è facilmente calcolabile se conosco ks ma dalla chiave kd è difficile risalire alla chiave ks. Se uso un cifrario asimmetrico, la funzione F(kd) è facilmente calcolabile. ks è la chiave segreta e kd è la chiave pubblica.

---

![marco togni](./img/marco_togni.jpg)

---
![cyber sesso](https://user-images.githubusercontent.com/56556806/134823047-da26060a-3813-4e73-a13c-256bcd0483c4.png)

# How I Defeated Fascism with the Power of Love

## Chapter 1: The Power of Love

The first step in my journey was realizing that it is impossible to defeat
fascism with the power of love.

## Chapter 2: The Power of Incredible Violence
