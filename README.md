# Sicurezza dell'informazione 2021-2022

<!-- chi è che ha preso questi appunti sulla lezione del 23? Mi sono venuti i brividi-->

<!--la data da togliereeeeee...tra due mesi viene l'angoscia di vedere quando il corso è iniziato-->
## 01.Introduzione (23/09/2021)

### Scopo della sicurezza informatica

Il tema della sicurezza informatica è molto importante, in un mondo come quello di oggi, dove l'informatica domina buona parte delle relazioni sociali, lavorative, economiche e politiche. Questo tema è ancora più sentito con l'arrivo del COVID in cui il mondo si presta a digitalizzarsi.
Dunque, la sicurezza informatica ha lo scopo di proteggere le risorse da accessi indesiderati, garantire la riservatezza delle informazioni, assicurare il funzionamento e la disponibilità dei servizi a fronte di eventi imprevedibili.
Per essere più precisi, è l’insieme dei prodotti, dei servizi, delle regole organizzative e dei comportamenti individuali che proteggono i sistemi informatici di un’azienda.

### I tre caposaldi della sicurezza informatica (CIA Trade Triangle)

Le tre proprietà da garantire per la sicurezza dei dati sono:

- **Confidenzialità**: assicura che solo chi è autorizzato può accedere (in sola lettura) a risorse o sapere almeno che esse esistano;
- **Integrità**: solo chi è autorizzato può modificare, eliminare e creare risorse;
- **Disponibilità**: solo chi è autorizzato può accedere alle risorse senza interferenze ed ostacoli.

![cia](./img/cia.png)

### Terminologia

- **Vulnerabilità**: punto debole del sistema che può rendere realizzabile una minaccia;
- **Minaccia**: un atto ostile intenzionale o meno che ha un qualsiasi effetto negativo sulle risorse o sugli utenti del sistema;
- **Attacco**: qualsiasi azione che usa una vulnerabilità per concretizzare una minaccia
- **Contromisura**: azione, dispositivo, procedura o tecnica che consente di rimuovere o ridurre una vulnerabilità

Esempio: un ponte ha una crepa (vulnerabilità), rischia di crollare (minaccia), un peso totale eccessivo sul ponte (attacco), cercare di controllare il numero di veicoli sul ponte (contromisura)

<!-- la tabella a pagina 9 secondo me è utile ma devo ancora capirla-->

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
## Introduzione + bestemmie (27/09/2021)

### Calcolatore sicuro

Un calcolatore per essere sicuro lo deve essere sia a livello hardware che a livello software.
<!--In questo corso ci si focalizza principalmente sulla "sicurezza dei dati", che consiste nel garantire i seguenti requisiti fondamentali:

- confidenzialità;
- integrità;
- disponibilità;
- autenticazione;
- non ripudio.!-->

Quando parliamo di sicurezza dei dati, in questo corso, faremo un'assunzione fondamentale: assumeremo che il nostro hardware, firmware e sistema operativo, siano **sicuri**.

Ovviamente questa ipotesi non è sempre verificata, ma in questo corso quando studieremo i servizi e meccanismi di sicurezza lo daremo per scontato.

<!--NB: la sicurezza HW e FW non è argomento proprio del corso, ma la prof ci ha dato qualche info a riguardo per sapere giusto di cosa stiamo parlando.-->

### Sicurezza hardware

<!-- toglierei questa sezione: non viene trattata nel corso e non è oggetto di esame -->

Soprattutto negli ultimi anni, la sicurezza hardware sta emergendo in maniera preponderante; si sono scoperte vulnerabilità a livello di componenti fisici, in particolare:

- Memorie
- Periferiche
- I/O
- linee di trasmissione

L'ambito della sicurezza hardware si occupa di proteggere il calcolatore, ma anche altri dispositivi fisici, appunto, da minacce quali furto, danneggiamento o alterazione dei componenti.

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

<!-- non ho capito di cosa si parla. prodotto fisico?!?-->
Per poter sapere che un componente di sicurezza sia sicuro, ci deve essere qualcuno che lo garantisca.
In questo caso, occorrono degli enti di certificazione e degli standard che definiscono delle metodologie con cui andare a verificare che un progetto sia effettivamente sicuro. Applicando questi standard, gli enti ci garantiscono la sicurezza del prodotto che installiamo.

Esempi di standard internazionali per valutazione e certificazione della sicurezza: Orange book del NCSC, ISO 17799, CINI, CERT, ecc.

### Terminologia

**Meccanismo di Sicurezza**: meccanismo progettato per rilevare/prevenire un attacco, risanare il sistema a seguito di un attacco.

**Servizio di Sicurezza**: servizio che migliora la sicurezza dell'elaborazione dei dati e del trasferimento delle informazioni.

<!-- l'attacco è stato scritto in alto!-->
**Attacco**: azione mirata a compromettere una proprietà critica dell'informazione.

### Modello a canale insicuro

D'ora in poi per analizzare e studiare i meccanismi di sicurezza faremo riferimento ad un modello molto specifico, chiamato *modello del canale insicuro*.

Questo modello prevede che ci sia una sorgente dei dati, una destinazione a cui sono rivolti e che ci sia un canale che mette in comunicazione sorgente con destinazione.

Assumiamo che:

- La sorgente abbia un ambiente sicuro (hardware e sistema operativo sicuri);
- La destinazione abbia un ambiente sicuro (hardware e sistema operativo sicuri);
- Il canale sia insicuro ovvero che sul canale si possono inserire degli intrusori e possono fare degli attacchi passivi e attivi su tale canale

Definito un modello di questo genere, il nostro obiettivo è garantire che la destinazione possa consumare ed interpretare correttamente i dati inviati dalla sorgente: se la sorgente produce dati con garanzia di autenticità, la destinazione deve poter verificare l'autenticità anche in seguito alla consumazione di tali (non ripudio).

Mmmm non mi convince la def di non ripudio

### Classificazione attacchi

Gli attacchi si classificano in 2 tipologie:

- **Passivo**: l'intrusore si inserisce sul canale ma l'unica cosa che può fare è intercettare i dati senza alterarne il flusso. Questo canale può essere un bus, un canale interno offline, ma anche un canale diretto. Viene minato il requisito di _disponibilità_.
<!-- che cosa è un canale interno offline?-->
- **Attivo**: l'intrusore può accedere al canale ed alterare il normale flusso dei dati. Può:
  - Modificare/Aggiungere il flusso intenzionalmente per cambiare il contenuto dei dati. Viene minato il requisito dell'_integrità_;
  <!--- Aggiungere informazioni, in modo da evitare la falsificazione che mina all'integrità dei dati. La destinazione deve avere un controllo che garantisca la legittimità della fonte-->
  - Interrompere il normale flusso impedendo che i dati arrivino alla destinazione. Viene minato il requisito di _disponibilità_.
  - Venire a conoscenza del flusso di dati senza modificare il contenuto. E' un attacco passivo. Viene minato il requisito della _confidenzialità_.

<!-- una volta basta e avanza metterlo-->
<!--Ricapitolando per tipo di attacco e proprietà che mette a rischio):

- **Attacchi passivi**: mina confidenzialità e autenticazione. Autenticazione? DA DOVE ESCE FUORI?
- **Attacchi attivi**: integrità, autenticità e disponibilità-->

### Contromisure
Esistono 3 tipologie di contromisure per gli attacchi:

- **Prevenzione**: tramite cui si previene la possibilità che un dato venga intercettato;
- **Rilevazione**: tramite cui si rileva un attacco in corso;
- **Reazione**: tramite cui si reagisce dopo che un attacco è già avvenuto.

Il tipo di contromisura da adottare, va scelto anche in base al sistema e a cosa vogliamo proteggere (nel nostro caso ci interessano i dati). Se ad esempio i dati sono non confidenziali, non ci interessa che vengano intercettati. Invece, se i dati non sono riservati, non sarà necessaria la prevenzione.

Come ingegneri, il nostro obiettivo è capire a fronte di più possibilità progettuali, quale ha più senso per il nostro sistema ed i nostri dati da proteggere.

**Possibili contromisure per attacchi passivi**:

L’unica contromisura da utilizzare è la prevenzione. Non ha senso utilizzare la tecnica della rilevazione in quanto quando lo rilevo ormai è tardi e non ha più senso intervenire perché l’informazione è stata ormai violata.

- Impedire l'accesso al canale. Questo viene implementato tramite l'utilizzo o di canali dedicati, oppure mettendo in piedi meccanismi di controllo dell'accesso su larga scala, che fanno in modo che ogni volta che una sorgente accede al canale, il  meccanismo chiede di autenticasi. Per come è realizzata, questa soluzione non è tuttavia economicamente sostenibile né scalabile;
- Criptare i dati da inviare, ovvero rendere incomprensibili i dati trasmessi, tranne al destinatario legittimo.

**Possibili contromisure per attacchi attivi**:

Le contromisure da adottare sono rilevazione e reazione.

Contro gli attacchi attivi, in linea di principio avrebbe senso adottare una contromisura preventiva, in quanto protegge l'autenticità, l'integrità e la riservatezza, ma come si può prevenire un attacco al flusso di dati, che è in corso? Possibili modi:
- Controllo dell'accesso al canale, si può fare ma ovviamente ci sono sempre gli svantaggi specificati in precedenza;
- Attestato di integrità e origine. Se è necessaria una contromisura di rilevazione, per permettere alla destinazione di sapere se quel flusso di dati è corretto o no, si può utilizzare un certificato di integrità/autenticità. In questo caso la rappresentazione dei dati non è incomprensibile, ma al normale flusso dei dati aggiungo dati in più che permettono alla destinazione di capire se il flusso è integro e autentico, oppure è stato manomesso. Esistono dei meccanismi crittografici che permettono di ottenerli.

<!-- nuovo blocco -->
---
NUOVO BLOCCO

Collocazione dei meccanismi e dei servizi per la sicurezza
se il meccanismo viene collocato a livello applicativo è molto personalizzabile ma richiede manutenzione

Trasporto è più trasparente alle applicazioni;

Livello di rete è completamente trasparente, ma è meno personalizzabile rispetto alle esigenze delle applicazioni

A seconda del livello avrò prestazioni, personalizzabilità e trasparenza alle applicazioni diverse.

Trasformazioni di sicurezza -> dobbiamo costruire degli algoritmi o protocolli (sequenza di azioni ordinate, che mi permettano di trasformare l'informazione orginaria in qualcos'altro (qualcosa di incomprensibile o qualcosa di ridondante che aggiunga alle informazioni gli attestati)

trasformazioni: algotirmi o protocolli

algoritmi = prima trasformazione T1 (trasformazione dei dati prima di metterli sul canale insicuro)
seconda trasformazione T2 (per risalire al contenuto dei dati)

Nonn sempre una singola trasformazione è sufficiente.

- A volte c'è bisogno di un protocollo (serie di trasformazioni che sorgente e destinazione devono fare, perché noi nel modello di minaccia più semplice assumiamo che la sorgente si comporti bene e la destinazione si comportano bene, ma a volte potrebbero a loro volta essere compromesse o malintenzionate)

mmh dimmi come fai a fare la fede che ti viene buona esagerata

Vedremo vari protocolli: alcuni richiedono l'intervento di una terza entità (oltre a sorgente/destinatario), che fa da arbitro/giudice

Caratteristica di tutte queste trasformazioni: ridondanza in termini di codifica e di tempo

Caratteristica comune alle trasformazioni per la sicurezza è la ridondanza.
È fondamentale. Perché impiegando più bit di rappresentazione, ha un overhead nel sistema, se non altro in termini di occupazione di banda, di memorizzazione del dato.

- **Crittografia**: studia come progettare le trasformazioni che mi permettono di proprietà di sicurezza dell'informazione
- **Crittoanalisi**: Studia le trasformazioni che permettono di rompere la sicurezza di informazioni

Ci sono tre principi della difesa che guidano la progettazione delle trasformazioni:

- Deve essere impossbile _sapere_ che trasformazione è stata eseguita;
- Impossibile _dedurre_ qual è la trasformazione adottata;
- Deve essere impossibile _indovinare_ la trasformazione adottata.

Per ora parliamo di impossibilità, poi arriveremo alla difficoltà

Se la trasformazione è segreta è chiaro che diventa impossibile dedurre e indovinare

Devo far sì che il calcolo di sapere, dedurre o indovinare, sia impossibile.

Difficili per chi conosce il segreto, impossibili per chi non lo conosce.

- Trasformazione diretta (di encryption): prendo il mio dato in chiaro (plain text) in qualcosa di non comprensibile (cypher text)
- Trasformazione inversa (di decryption): prende dal canale il cypher text e lo trasforma in plain text

Un intrusore si può intromettere, ma non riesce a capire quale sia il testo in chiaro

Questa trasformazione è bidirezionale: uno cripta, l'altro decripta e viceversa.
Questo schema funziona se entrambi sono online/solo uno dei due? Questo schema va bene in tutte le situazioni (se ad esempio A è online e cripta e invia, ma B è offline, quando torna online lo decripta, easy pez)

I calcoli per mettere in chiaro un testo cifrato, senza conoscere la trasformazione di decription devono essere facili per chi conosce

Confronto:

Deve poter vedere se a quel dato corrisponde quel riassunto

Se il confronto ha successo => la destinazione può dire che il dato ricevuto è integro.

Significa che sul canale, in qualche modo sono stati inviati entrambi (dati originali e riassunto) - in qualche modo l'intrusore può attaccare entrambe o solo una delle due -

Di sicuro la destinazione deve riceverle entrambe e deve confrontarle.

Quali sono le caratteristiche.

Come otteniamo il riassunto:
esistono le funzioni hash (funzioni che dato un input producono un input molto più piccolo, un'impronta)

Non ci vanno bene tutte le funzioni hash, ma abbiamo bisogno di una funzione che chiamiamo "crittograficamente sicura", ovvero con 2 caratteristiche fondamentali:

- "facilità di esecuzione"
- "comportamento da oracolo casuale".

Una funzione hash crittograficamente sicura è tale se il suo comportamento è apparentemente aleatorio.

Se io fornisco in ingresso a tale funzione un messaggio di cui non conosco ancora l'impronta, si riscrontra in uscita uno dei qualsiasi dei 2^n valori possibili dove n è il numero di bit dell'impronta.

Se io do in input un messaggio di dimensione m, non so con quale probabilità avrò quell'impronta.

Non posso prevedere con certezza quale valore avrà in uscita.

Questa è una caratteristica fondamentale;

Altra caratteristica necessaria: resistenza alle collisioni, ovvero se una funzione hash è critt sicura, l'individuazione di due messaggi con la stessa impronta da parte di un intrusore dev'essere difficile

Se ho 2^m valori di ingresso con m > n, ovviamente ci sono delle collisioni, è inevitabile, ma dev'essere difficile per un intrusore trovare quella coppia di messaggi con la stessa impronta.

Funzioni hash impiegate soprattutto per rilevare i disturbi (check sum)

Per ora non ci interessa di com'è fatta o qual è l'algoritmo che useremo, ma sappiamo che per costruire un certificato di autenticità abbiamo bisogno di una funzione hash con certe caratteristiche (definite in precedenza).

Esempio:
(slide) attestazione ed accertamento dell'integrità

Supponiamo che A metta sul canale insicuro -> un messaggio m, affiancato da H (funzione hash crittograficamente sicura), a partire da m è stata costruita H(m)

B deve prendere il messaggio ricevuto, applicargli la funzione hash, che conosce anche lui, e verificare che l'hash ricevuto coincida con quello ottenuto applicando a sua volta la funzione hash.
Se equivalgono è tutto ok (tutto trasmesso correttamente).

La destinazione è in grado di rilevare se il messaggio ha subito modifiche

Mettiamoci nei panni dell'intrusore:
se l'intrusore conosce la funzione hash può mettere un nuovo messaggio con hash allegato

abbiamo quindi 2 tipi di trasformazioni: Encryption, Hash

possiamo anche combinarle

e se volessimo garantire la riservatezza e l'integrità dei dati

Diverse contromisure:

- Controllo dell'accesso al canale. Soluzione non scalabile e non sostenibile.
In alcuni scenari applicativi di facile realizzazione si possono mettere dei cavi appositi.

- Cifrare il canale, e rendere possibile che quello che sto trasmettendo venga capito soltanto dal legittimo destinatario.
In questo corso studieremo gli algoritmi di crittogragia, in modo da rendere incomprensibile per un intrusore la comprensione dei dati sul canale.

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

![zeus](./img/zeus.jpg)



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

---

## 29/09/2021

### Protocollo per la difesa di riservatezza e integrità

Bisogna garantire l’integrità (rilevazione e reazione)

Con un attacco attivo si possono cancellare e modificare i dati, oltre che modificarne anche l’ordine.

Il disturbo invece non cambia l’ordine dei dati dell’informazione. Tutte le alterazioni avvengono con uguale probabilità.

Proteggere l’integrità significa creare delle contromisure per la rilevazione di eventuali modifiche al contenuto del dato originale.

Si utilizza la ridondanza dei dati, cioè insieme all’informazione viene aggiunto un piccolo riassunto (un riassunto di grandi dimensioni causerebbe overhead) che identifica in maniera univoca possibilmente l’informazione. La destinazione riceverà l’informazione più il riassunto che la sorgente ha creato.
 
Utilizzando il riassunto, va ad applicarlo sull’informazione e sarà in grado di rilevare se l’informazione è corretta oppure è stata modificata. Il riassunto viene creato con una funzione hash, e per riuscire ad identificare
un’informazione in maniera univoca deve essere una funzione hash criptograficamente sicura. Una funzione
hash (M) prende in ingresso un messaggio m di lunghezza arbitraria e generano un’uscita chiamata impronta

H(m) con una lunghezza del messaggio molto minore. Per essere criptograficamente sicura una funzione hash

Deve avere due caratteristiche principali:


Deve avere un comportamento da oracolo casuale, cioè se ho un’impronta di n bit con un numero di
impronte possibili è 2n, nel momento in cui prendo m e gli applico la funzione hash H(m), la probabilità
di ottenere una delle possibili 2n impronte è equivalente a quella di ottenere una qualsiasi delle altre
2n-1 impronte.
Deve essere resistente alle collisioni, cioè se due messaggi m1 e m2 hanno la stessa impronta (cosa
molto possibile poiché lo spazio di input è molto minore dello spazio di output), per un intruso deve
essere computazionalmente difficile trovare un messaggio m2 con impronta H(m2) uguale a quella di
m1, cioè H(m1).




### Come vengono combinate le trasformazioni E ed H?

---

![marco togni](./img/marco_togni.jpg)


---
![cyber sesso](https://user-images.githubusercontent.com/56556806/134823047-da26060a-3813-4e73-a13c-256bcd0483c4.png)

# How I Defeated Fascism with the Power of Love

## Chapter 1: The Power of Love

The first step in my journey was realizing that it is impossible to defeat
fascism with the power of love.

## Chapter 2: The Power of Incredible Violence
