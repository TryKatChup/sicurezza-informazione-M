# Sicurezza dell'informazione 2021-2022

<!--la data da togliereeeeee...tra due mesi viene l'angoscia di vedere quando il corso è iniziato-->
## 01.Introduzione (23/09/2021)

### Scopo della sicurezza informatica

Il tema della sicurezza informatica è molto importante, in un mondo come quello di oggi, dove l'informatica domina buona parte delle relazioni sociali, lavorative, economiche e politiche. Questo tema è ancora più sentito con l'arrivo del _COVID_ in cui il mondo si presta a digitalizzarsi.
La sicurezza informatica ha quindi lo scopo di proteggere le risorse da accessi indesiderati, garantire la riservatezza delle informazioni, assicurare il funzionamento e la disponibilità dei servizi a fronte di eventi imprevedibili.
Per essere più precisi, è l’insieme dei prodotti, dei servizi, delle regole organizzative e dei comportamenti individuali che proteggono i sistemi informatici di un’azienda.

### I tre capisaldi della sicurezza informatica (CIA Trade Triangle)

L'acronimo _CIA_ viene usato per rappresentare le tre proprietà fondamentali della sicurezza informatica:

- **Confidenzialità** (o **riservatezza**): assicura che solo chi è autorizzato può accedere (in sola lettura) a risorse o sapere almeno che esse esistano;
- **Integrità**: solo chi è autorizzato può modificare, eliminare e creare risorse;
- **Disponibilità**: solo chi è autorizzato può accedere alle risorse senza interferenze ed ostacoli.

![cia](./img/img1.png)

A queste proprietà se ne possono aggiungere altre come:

- **Autenticità**: si deve effettivamente dimostrare chi è stato a creare il dato o sapere da chi proviene;
- **Non ridupio**: quando una qualsiasi operazione sul dato è avvenuta, a posteriori, ad una terza parte si può dimostrare con certezza la paternità di quell'operazione (es. firma digitale).

### Terminologia

- **Vulnerabilità**: punto debole del sistema che può rendere realizzabile una minaccia;
- **Minaccia**: un atto ostile intenzionale o meno che ha un qualsiasi effetto negativo sulle risorse o sugli utenti del sistema;
- **Attacco**: qualsiasi azione che usa una vulnerabilità per concretizzare una minaccia;
- **Contromisura**: azione, dispositivo, procedura o tecnica che consente di rimuovere o ridurre una vulnerabilità.

Esempio: un ponte ha una crepa (vulnerabilità), rischia di crollare (minaccia), un peso totale eccessivo sul ponte (attacco), cercare di controllare il numero di veicoli sul ponte (contromisura).

<!-- toglierei questo paragrafo
- **Virus**: provoca danni e si replica propagato dagli umani (involontariamente);
- **Worm**: provoca danni perché si autoreplica (satura risorse) in maniera automatica, senza l'intervento dell'utente;
- **Trojan (horse)**: vettore di malware, contiene funzionalità aggiuntive impreviste;
- **Backdoor**: punto di accesso non autorizzato;
- **Rootkit**: strumenti per accesso privilegiato, nascosti (modifica di un programma, libreria, driver,
modulo kernel, hypervisor) ed invisibili.-->

<!--CANCELLEREI QUESTO PARAGRAFO :P
### Poi ha detto qualche vulnerabilità a caso, spiegando bene solo l'IP spoofing e il SYN flooding, ma il resto le ha tralasciate perché sì.
da scrivere bene dopo--!> <!--QUANDO VUOI...-->

---

<!-- da togliere per fare il blocco 1 tutto unito -->
## 27/09/2021

### Calcolatore sicuro

Un calcolatore per essere sicuro lo deve essere sia a livello hardware che a livello software. Ovviamente questa ipotesi non è sempre verificata, ma in questo corso quando studieremo i servizi e meccanismi di sicurezza lo daremo per scontato.

<!-- differenza tra servizi e meccanismo di sicurezza -->

Quando parliamo di sicurezza dei dati, faremo un'assunzione fondamentale: l'hardware, il firmware e il sistema operativo sono **sicuri**.

<!-- se è stato tolto il firmware toglierei anche questo-->
### Sicurezza hardware

Soprattutto negli ultimi anni, la sicurezza hardware sta emergendo in maniera preponderante; si sono scoperte vulnerabilità a livello di componenti fisici, in particolare:

- Memorie
- Periferiche
- I/O
- linee di trasmissione

L'ambito della sicurezza hardware si occupa di proteggere il calcolatore, ma anche altri dispositivi fisici, da minacce quali furto, danneggiamento o alterazione dei componenti. Questa parte non verrà trattata nel corso e non sarà oggetto di esame.
<!-- se è stato tolto il firmware toglierei anche questo-->

<!-- toglierei anche questo -->
### Valutazione, Certificazione, Enti

Per poter sapere se un prodotto software sia sicuro, ci deve essere qualcuno che lo garantisca.
In questo caso, occorrono degli enti di certificazione che definiscono delle metodologie con cui andare a verificare che un progetto sia effettivamente sicuro. Applicando questi standard, gli enti ci garantiscono la sicurezza del prodotto che installiamo.

Esempi di standard internazionali per valutazione e certificazione della sicurezza: Orange book del NCSC, ISO 17799, CINI, CERT, ecc.
<!-- toglierei anche questo -->

### Modello a canale insicuro

D'ora in poi per analizzare e studiare i meccanismi di sicurezza si farà riferimento ad un modello molto specifico, chiamato _modello a canale insicuro_.

Questo modello prevede che ci sia una sorgente dei dati, una destinazione a cui sono rivolti e che ci sia un canale che mette in comunicazione sorgente con destinazione.

Assumiamo che:

- La sorgente abbia un ambiente sicuro (hardware e sistema operativo sicuri);
- La destinazione abbia un ambiente sicuro (hardware e sistema operativo sicuri);
- Il canale sia insicuro, ovvero che sul canale si possano inserire degli intrusori e possono fare degli attacchi su tale canale.

Definito un modello di questo genere, l'obiettivo finale sarà di garantire che la destinazione possa consumare ed interpretare correttamente i dati inviati dalla sorgente.

### Classificazione attacchi

Gli attacchi si classificano in due tipologie:

- **Passivo**: l'intrusore si inserisce sul canale e osserva solo i dati trasmessi. Ad esempio, se il canale è un cavo di rete, si usa uno sniffer. Viene minato il requisito di _confidenzialità_;
- **Attivo**: l'intrusore si inserisce sul canale ed altera il normale flusso dei dati. Può:
  - **Modificare** il flusso intenzionalmente per cambiare il contenuto dei dati. Viene minato il requisito dell'_integrità_;
  - **Aggiungere** nuove informazioni facendo credere alla destinazione che siano state inviate dalla sorgente legittima. Viene minato il requisito dell'_autenticità_;
  - **Interrompere** il normale flusso impedendo che i dati arrivino alla destinazione. Viene minato il requisito di _disponibilità_.


<!-- Riassumendo:

non ha detto niente del genere 
- **Attacchi passivi**: mina confidenzialità e autenticazione (esempio: Man In The Middle);
- **Attacchi attivi**: integrità, autenticità e disponibilità.-->

### Contromisure
Esistono 3 tipologie di contromisure per gli attacchi:

- **Prevenzione**: si previene la possibilità di un attacco;
- **Rilevazione**: si rileva un attacco in corso;
- **Reazione**: si reagisce dopo che un attacco è avvenuto.

Il tipo di contromisura da adottare viene scelta anche in base al sistema e a cosa si vuole proteggere (nel corso il focus è incentrato sui dati).

La contromisura ha un costo in termini di soldi, di impegno delle risorse informatiche del sistema, di impatto sugli utenti, una sua efficacia (a fronte di una certa minaccia) e dei suoi effetti collaterali (la creazione di nuove vulnerabilità). Una certa contromisura, quindi, deve essere applicata attentamente, valutando sia la probabilità che si verifichi una certa minaccia in grado di sfruttare una certa vulnerabilità, sia il danno che ne discende. Questa attività è chiamata _analisi del rischio_.

Come ingegneri (LOL https://youtu.be/EOR8Uz27s3Y?t=420), l'obiettivo è capire a fronte di più possibilità progettuali quale risulti la migliore scelta per garantire la sicurezza del proprio sistema e dei propri dati.

#### Possibili contromisure per attacchi passivi

L’unica contromisura da utilizzare è la _prevenzione_. La _rilevazione_ e la _reazione_ risultano inutili dopo che l'attacco è avvenuto perchè ormai l'intrusore ha intercettato i messaggi.

Si può:
- **Impedire** l'accesso al canale. Ciò viene implementato tramite l'utilizzo o di canali dedicati, oppure progettando meccanismi di controllo dell'accesso, in modo che ogni volta che una sorgente accede al canale, il meccanismo chiede di autenticarsi. Questa soluzione non è tuttavia né economicamente sostenibile né scalabile;
- **Criptare** i dati da inviare, ovvero rendere incomprensibili i dati trasmessi, tranne al destinatario legittimo.

#### Possibili contromisure per attacchi attivi

Le contromisure da adottare, a differenza degli attacchi passivi, includono anche la _rilevazione_ e la _reazione_. L'unico modo per _prevenire_ un attacco attivo è quello di controllare l'accesso al canale, ma ovviamente è quasi impossibile per i motivi specificati in precedenza. Questa contromisura, quindi, non viene usata.

Si può:
- **Aggiungere** un attestato di integrità e di autenticità. Sul cananle, oltre al messaggio si inviano queste due informazioni in più che consentono alla destinazione di capire se il flusso dei messaggi è integro e autentico oppure se è stato manomesso (integrità e autenticità).
- **Impedire** l'interruzione del flusso di dati. Non sono meccanismi crittografici. Se la sorgente invia un numero di messaggi, la destinazione conteggia che sono arrivati effettivamente quel numero (disponibilità).

<!--### Servizi di sicurezza

Esistono protocolli che forniscono servizi di sicurezza, ma si collocano a livelli diversi:
- **IPsec**: livello di rete;
- **SSL**: livello di trasporto;
- **PGP**: livello applicativo.

A seconda del livello si avrà una prestazione, personalizzazione e trasparenza diverse. IPsec, PGP e SSL garantiscono tutti la sicurezza dei dati cioè garantiscono le proprietà _CIA_. A livello di IPsec si parla di autenticità a livello host, non posso dire quali client verranno autenticati.-->

## 01. Dati Sicuri

Per proteggere i dati a fronte di eventuali attacchi occorre utilizzare delle trasformazioni.

![cia](./img/img26.png)

L'_algoritmo_ è una singola trasformazione cioè è una sequenza di istruzioni. Ad esempio, il blocco Ts o Td.

![cia](./img/img27.png)

Nei casi complessi, è necessario che si eseguano più trasformazioni e la loro sequenza da eseguire deve essere ben precisa. In questo caso, si parla di _protocollo_.

Non è detto che ci sia sempre solo sorgente e destinazione, ma in alcuni casi è necessario l'intervento di una terza entità che fa da _arbitro_/_giudice_. La si usa quando una o tutte e due le due entità in gioco sono malintenzionate.

## Come rendere sicuri i dati

La tecnica che può rendere i dati sicuri è quella di impiegare una codifica ridondante ai dati. Ad esempio, quando bisogna rendere incomprensibili i dati, si paga un costo in più in termini di overhead sia di banda che di processamento (ridondanza temporale) e in alcuni casi, la trasformazione aggiunge bit in più rispetto alla lunghezza del messaggio originario (ridondanza spaziale). Se si usa un attestato di integrità o di originalità, si aggiunge sia ridondanza in termini di spazio che in termini di tempo.

<!--fine parte da correggere-->
## Crittografia e Crittoanalisi

La disciplina che studia gli algoritmi ed i protocolli da svolgere dal lato sorgente e lato destinatario di un canale insicuro è detta _crittologia_. A sua volta è formata da due distinte e correlate discipline:

- **Crittografia**: è la disciplina che studia gli algoritmi che possiamo adottare per proteggere i dati in in termini di riservatezza, autenticità e integrità;
- **Crittoanalisi**: è la disciplina che studia il modo in cui è possibile rompere le trasformazioni che proteggono i dati in in termini di riservatezza, autenticità e integrità.

Nel corso studieremo solo la crittografia.

## I principi della difesa

Ci sono tre principi che guidano la progettazione:

- **Deve essere impossibile _sapere_ la trasformata/i calcoli da parte dell'intrusore**;
- **Deve essere impossibile _dedurre_ la trasformata/i calcoli da parte dell'intrusore**;
- **Deve essere impossibile _indovinare_ la trasformata/i calcoli da parte dell'intrusore**.

## Proteggere la proprietà di confidenzialità

Per proteggere i dati, abbiamo bisogno di una trasformata che rende incomprensibile il loro contenuto. In questo modo, l'intrusore non sarà in grado di capire i messaggi. Dunque, la riservatezza la possiamo ottenere con una trasformazione di tipo _preventivo_ in modo che se un intrusore accede ai dati non li può capire.

![confidenzialità](./img/img2.png)

La sorgente `A` non può mettere i dati `m` sul canale insicuro per ovvi motivi
ma deve prima trasformarli tramite un'encryption `E`. Questa trasformazione la
conosce solo la sorgente `A` ed è l'unica in grado di eseguirla. Nell'esempio
della figura, i dati `m` vengono trasformati in dati incomprensibili `c`. La destinazione `B` riceve `c` e tramite la trasformazione di decryption `D`, risalire al contenuto dei dati `m`.

Devono essere rispettate le seguenti proprietà:

- **Segretezza**: la trasformazione `E` e `D` sono conosciute solo rispettivamente dalla sorgente e dal destinatario quindi per i tre principi di difesa, non è possibile risalire al messaggio in chiaro;
- **Calcoli difficili**: i calcoli per mettere in chiaro il messaggio senza conoscere l'algoritmo devono essere da un punto di vista computazionale un'operazione molto onerosa.

Altre considerazioni:
- **Il flusso è bidirezionale**: lo schema della figura può essere applicato sia da `A` verso B che da `B` verso `A`. Ovviamente `B` avrà l'encryption mentre `A` la decryption;
- **A e B non è detto che siano entrambi online**: possono essere online contemporaneamente oppure A online e B offline cioè i messaggi possono essere decifrati in momenti diversi;
- **B = A**: la sorgente potrebbe coincidere con la destinazione. Ad esempio, vogliamo cifrare dei dati che abbiamo sul nostro hard disk. Quando effettuiamo il logout dal sistema essi vengo cifrati mentre quando facciamo il login li decifriamo.

## Proteggere la proprietà di integrità

Proteggere l'integrità vuol dire costruire delle trasformazioni in grado di rilevare modifiche al contenuto dei dati trasmessi. In questo caso, la contromisura da adottare è quella della _rilevazione_ perché le modifiche ai messaggi sul canale non possono essere evitate a priori.

Se vogliamo costruire una trasformazione che protegga l'integrità, dobbiamo far si che la sorgente utilizzi ridondanza al messaggio e affianchi al dato iniziale un'informazione aggiuntiva che deve essere costruita opportunamente. Questa informazione si chiama _riassunto_ o _impronta_. La sua dimensione deve essere inferiore perché la si deve poi trasmettere sul canale.

Il riassunto non è altro che una _funzione hash crittograficamente sicura_.

![integrità](./img/img3.png)

In generale, una funzione hash `H` è una funzione che prende un dato `m` di lunghezza arbitraria e restituisce in uscita un'impronta `H(m)`.

A noi non basta avere una qualunque funzione hash, ma è importante che abbia due proprietà:

- **Calcoli difficili**: dato il messaggio `m` deve essere facile calcolare la sua impronta. L'operazione inversa invece non è fattibile;
- **Comportamento da "oracolo casuale"**: se decidiamo che l'impronta sia costituita da `n` bit, le possibili uscite della funzione hash sono `2^n`. Preso il nostro messaggio `m`, dobbiamo fare in modo che la probabilità che esca un uscita rispetto ad un'altra sia la stessa.
![zeus](./img/zeus.jpg)
- **Resistente alle collisioni**: è inevitabile che due messaggi diversi possano avere in uscita la stessa impronta perché lo spazio di input è molto più grande dello spazio di output (`m > n`). Ad esempio, se i messaggi sono dieci e il numero di bit è tre, le possibili uscite della funzione hash sono otto e alcuni messaggi avranno sicuramente la stessa impronta. L'importante è che per un intrusore sia difficilissimo individuare due messaggi che abbiano la stessa impronta.

Queste caratteristiche le si ottengono **solo** usando _funzioni hash crittograficamente sicure_.

Le funzioni hash possono essere classificate in due categorie:

- **Funzioni hash semplici**: l’individuazione di due messaggi con la stessa impronta è un calcolo facile. Questo è il caso dei disturbi. Come visto nel corso di Fondamenti di Telecomunicazioni T, in presenza di certi disturbi, è più probabile che i bit che cambino siano sempre gli stessi, per cui è possibile calcolare la probabilità;
- **Funzioni hash sicure**: se le funzioni hash sono crittograficamente sicure (vedi proprietà scritte in alto).

![attestazioneIntegrità](./img/img4.png)

La sorgente `A` mette sul canale insicuro un messaggio `m` mentre l'impronta `H(m)` deve viaggiare su un canale sicuro per evitare che un intrusore possa sostituire `m` con un altro messaggio `m'` e di conseguenza ricalcolare `H(m')`. `B` deve prendere il messaggio ricevuto, applicargli la funzione hash, che conosce anche lui, e verificare che l'hash ricevuto coincida con quello ottenuto.
Se si equivalgono, il messaggio è stato trasmesso correttamente. In questo modo la
destinazione è in grado di rilevare se il messaggio ha subito modifiche.

### Esempio

Le trasformazioni possono essere combinate fra di loro. Ad esempio, per garantire la riservatezza e l'integrità dei dati le possiamo usare in questo modo:

`p = m || H(m)` 

`c = E(p)`

`p* = D(c*) = m* || H*(m)`

`H*(m) =? H(m*)`

Dato che le proprietà da garantire sono due, abbiamo bisogno di combinare più trasformazioni e le regole che devo usare devono essere precise. Per questo ci serve un protocollo.

Il seguente protocollo è costituito dai seguenti passi:
- La sorgente esegue due trasformazioni:
  - **Passo 1**: la sorgente applica la funzione hash crittograficamente sicura e la concatena con il messaggio;
  - **Passo 2**: la sorgente applica la funzione di encryption. Dato che il messaggio `c` è cifrato, lo si può inviare direttamente sul canale insicuro.
- La destinazione esegue una trasformazione:
  - **Passo 3**: la destinazione riceve `c` che può essere, o quello inviato dalla sorgente o un altro che è stato modificato dall'intrusore. Per questo motivo, dato che non abbiamo una certezza, indicheremo il messaggio `c` con `c*`. La destinazione applica la funzione `D` su `c*` ottenendo di nuovo `m* || H*(m)`;
  - **Passo 4**: Per vedere se il messaggio sia integro, dobbiamo verificare che la funzione crittograficamente sicura `H(m*)` coincida con `H*(m)`. Se non coincidono il messaggio viene scartato.

Alcune considerazioni:
- L'intrusore può modificare solo a caso i bit del cifrato perchè se tutte le proprietà sono rispettate (comportamento da "oracolo casuale", resistente alle collisioni, testo cifrato aleatorio) non può fare assolutamente nulla;
- Da un punto di vista computazionale, la sorgente effettua due trasformazioni (encryption e la funzione `H`). La destinazione esegue sempre due trasformazioni (decryption e la funzione `H`).

### Esempio 2

In questo caso, l'integrità è rispettata mentre la riservatezza no:

`p = m`

`c = E(p) || H(m)`

`p* = D(c*) = m* || H*(m)`

`H*(m) =? H(m*)`

L'integrità è rispettata. perchè:
- **Modificare bit di E(p)**: se si cambiano dei bit di E(p) a caso è difficile che corrisponda la stessa impronta per la proprietà alla _resistenza alle collisioni_;
- **Modificare i bit H(m)**: H(m) corrisponde poi ad un altro messaggio per la resistenza alle collisioni;
- **Modificare E(p) e H(m)**: la probabilità è bassissima che il messaggio modificato corrisponda proprio a quell'impronta che è anch'essa modificata.

La riservatezza, invece, non è rispettata perchè:
- Ad esempio, l'intrusore sa che Rebecca Montanari sta trasmettendo dei dati a un'altra persona. Ha a disposizione tantissime informazioni di contesto. Dato che E(m) è impossibile che lo sappia, da un messaggio in chiaro riesce a calcolarsi l'impronta H(m). Se nota che l'impronta è la stessa, la riservatezza del messaggio è violata.

### Esempio 3

In questo caso, la proprietà di integrità non viene rispettata mentre quella di riservatezza si:

`p = m`

`c = E(p) || H(E(p))`

La riservatezza è verificata perchè:
- Da E(p) non si può risalire alla trasformata originale
- La funzione H non è invertibile e anche se lo fosse non si riuscirebbe poi a confrontare l'impronta m scelta dall'intrusore con quella H(E(p)) perchè manca la parte di cifratura del messaggio.

L'integrità non è garantita:
- L'intrusore può modificare E(p) e ottenere E*(p) e sostituire H(E(p)) con H(E*(p)). Se m è un messaggio senza un particolare significato (ad esempio un numero), D(E(p)) restituisce m* e la destinazione potrebbe non accorgersi che m* non sia corretto. Se invece m è un messaggio dotato di significato la destinazione potrebbe accorgersi che m* non ha senso e quindi non accettarlo per buono.

Alcune considerazioni:
- Da un punto di vista computazionale, la sorgente effettua due trasformazioni (encryption e la funzione H). La destinazione deve verificare l'integrità (la funzione H). Se il messaggio non è integro non ha senso effettuare la decryption. Dunque, può risparmiare una trasformazione.

## Proteggere la proprietà di autenticazione (=autenticità?)

Chi riceve un dato è importante che sappia chi è stato ad originarlo. L'intrusore può creare ad hoc un messaggio, inserirlo nel normale flusso dei dati e spacciarlo come se provenisse dalla sorgente originale. Questo attacco lo si può solo _rilevare_.

![autenticazione](./img/img5.png)

Per garantire l'autenticità di una sorgente, dobbiamo costruire una trasformazione `S` che dato un messaggio `m`, deve produrre in uscita un _attestato di autenticità_ `c` che rappresenta in maniera non imitabile il messaggio `m` originale. Nessuno deve essere in grado di effettuare questa trasformazione.

La destinazione riceve sia il messaggio che l'attestato di autenticità ed effettua una trasformazione `V` sull'attestato di autenticità producendo in uscita una risposta che dice se il messaggio è autentico o no. In caso affermativo si recupera il messaggio `m` altrimenti lo si scarta.

Devono essere rispettate le seguenti proprietà:

- **Calcoli difficili**: dato il messaggio `m` deve essere facile calcolare l'attestato di integrità. L'operazione inversa invece non è fattibile;
- **Segretezza**: la trasformazione `S` deve essere segreta per la sorgente perché altrimenti altri l'intrusore potrebbe effettuare lui la trasformazione. Invece, `V` può essere noto perché qualsiasi destinazione deve essere in grado di dire se l'attestato è autentico o no;
- **Calcoli impossibili**: i calcoli per costruire un messaggio autentico senza conoscere la sorgente devono essere difficili da un punto di vista computazionale.

Alcune considerazioni:

- **A e B non è detto che siano entrambi online**: B può verificare l'autenticità in un secondo momento;
- **B = A**: se nel file system vogliamo che i file siano davvero quelli che abbiamo scritto, durante la fase di logout e login oltre a decifrarli, verifichiamo che siano anche autentici.

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

- **Calcoli impossibili**: i calcoli per costruire un messaggio apparentemente autentico e senza conoscere la trasformazione della sorgente devono essere complessi.

Esistono 2 schemi alternativi per realizzare sign-verify: _la firma digitale_ e _hash_.

### Firma digitale

![firmadigitale](./img/img6.png)

La sorgente `A` prende il messaggio `m` e lo sottopone a una trasformazione `H`, costruendo l’impronta `H(m)`, che garantisce l’integrità. La funzione `S` di _sign_ viene eseguita su `H(m)`, e sul canale di comunicazione insicuro viene trasmesso `m` concatenato con `S(H(m))`.

<!--aggiunto -->
La destinazione `B` verifica tramite `V` che `c` proviene dalla sorgente leggittima. In questo modo verifico l'autenticità del messaggio. Dato che `c` contiene `H(m)` possiamo verificare anche la proprietà di integrità.
<!--aggiunto -->

Questo schema ha due vantaggi:
- **Efficienza**: la funzione di sign `S` è una trasformazione costosa. Anzichè applicare `m` direttamente a sign, l'applico a `H(m)` che è più piccola di `m`. Si può applicare anche all'impronta perchè è univoca per la proprietà di resistenza alle collisioni;
- **Avere subito la disponibilità del dato**: La funzione di `V` è onerosa. In questo schema rispetto al precedente, posso prendere direttamente `m` e a mio rischio e pericolo, verifico l'autenticità in un secondo momento.

Questo schema mi assicura anche la proprietà di:
- **Non ripudio**: dato che la sorgente `A` è l'unica che esegue `S` non può disconoscere in un secondo momento l'attestato di autenticità.

<!-- Il canale in questo modo viene reso sicuro e viene garantita anche la non ripudiabilità (la destinazione ottiene il messaggio dal canale non direttamente interpretabile). In questo caso la funzione `S` di Sign è segreta ed è conosciuta solamente dal mittente `A` che _firma_ il messaggio. -->

<!-- più corto il titolo secondo me-->
<!-- Hash del messaggio e di un segreto -->
### Hash applicata al messaggio concatenato con un segreto S, condiviso tra sorgente e destinazione

![hashs](./img/img7.png)

Due entità `A` e `B` (mittente e destinatario) condividono un segreto `s`. `A` calcola `H(m || s)` a partire da `m`, cioè il messaggio che si vuole trasferire, e invia alla destinazione `m || H(m || s)`.

Dato che il messaggio viaggia sul canale insicuro, l'intrusore può aver modificato il messaggio. Per questo motivo `m` si indica con `m*`.

La destinazione riceverà il messaggio `m*` e andrà a calcolare `H(m* || s)` e se è uguale a quello ricevuto le due proprietà sono state garantite (integrità e autenticità).

In questo caso **non** viene garantito il _non ripudio_, poiché la sorgente `A` potrebbe sospettare che la destinazione `B` si sia costruito un `H(m || s)` e la sorgente `A` in realtà non abbia inviato nulla. Questo è dovuto al fatto che `A` e `B` condividono un segreto e quindi non si è in grado di risalire a chi è effettivamente l'autore del messaggio inviato.

Questo schema risulta essere più efficiente rispetto alla _firma digitale_, ma potrà essere usato solamente quando si è sicuri del corretto comportamento di `A` e `B`.
Può essere utilizzato, ad esempio, con sistemi IoT che richiedono consumi ridotti di batteria e alta efficienza.

Viceversa, la firma digitale è meno efficiente poiché ha anche la funzione di _sign_ (`S`) ma garantisce il _non ripudio_.

Perchè questo schema è robusto:
- la funzione H non è invertibile quindi nessuno a parte A o B conosce s. Se fosse invertibile, l'intrusore ricaverebbe s e costruirebbe un attestato di autenticità valido.

### Esempio

In questo caso, si invia un messaggio che rispetta le proprietà di riservatezza e autenticazione:

`p = m || H(m || s)`

`c = E(p)`

`p* = D(c*) = m* || H*(m || s)`

`H*(m || s) =? H(m* || s)`

Il messaggio viene concatenato al certificato e cifrato dal client.
Si prende il messaggio, si cifra e si manda il cifrato concatenato con l'attestato di autenticità costruito sul messaggio.

Questo schema è usato dal protocollo SSL il quale adotta le funzioni hash crittograficamente sicure con un segreto per costruire il certificato di autenticità.

Da un punto di vista di efficienza, le trasformazioni in fase di ricezione sono due: decifrare ed autenticare.

### Esempio 2

In questo caso, si invia un messaggio che rispetta le proprietà di riservatezza e autenticazione:

`p=m`

`c = E(p), H(m || s)`

Si prende il messaggio `m`, si cifra `m` e si manda sul canale insicuro il cifrato concatenato con l'attestato di autenticità costruito sul messaggio.

Questo schema viene usato dal protocollo SSH. Permette di aprire shell remote sicure.

Da un punto di vista di efficienza, le trasformazioni in fase di ricezione sono due: decifrare ed autenticare.

### Esempio 3

In questo caso, si invia un messaggio che rispetta le proprietà di riservatezza e autenticazione:

`p=m`

`c = E(p), H((E(p) || s)`

In fase di invio, il messaggio viene cifrato e autenticato, mentre in fase di ricezione viene controllato l'attestato di autenticità e decifrato il messaggio.

Questo schema viene usato dal protocollo IPsec. E' un protocollo SSL a livello di trasporto (TCP). Vengono creati socket sicuri in cui i messaggi sono autenticati.

La ricezione è efficiente: viene risparmiata una trasformazione. Se il cifrato ha subito delle modifiche, chi riceve verifica il certificato e, se qualche operazione illegale è avvenuta, si evita l'operazione di decifratura.

<!-- testo spostato negli esempi di sopra :) -->
<!--### Esempi di applicazioni di procolli

- **SSL**: adotta le funzioni hash crittograficamente sicure con un segreto per costruire il certificato di autenticità. Il messaggio viene concatenato al certificato e cifrato dal client.
Si prende il messaggio, si cifra e si manda il cifrato concatenato con l'attestato di autenticità costruito sul messaggio;
- **SSL IPsec**: protocollo SSL a livello di trasporto (TCP). Vengono creati socket sicuri in cui i messaggi sono autenticati. In fase di invio, il messaggio viene cifrato e autenticato, mentre in fase di ricezione viene controllato l'attestato di autenticità e decifrato il messaggio;
La ricezione è efficiente: viene risparmiata una trasformazione. Se il cifrato ha subito delle modifiche, chi riceve verifica il certificato e, se qualche operazione illegale è avvenuta, si evita l'operazione di decifratura;
- **SSH**: permette di aprire shell remote sicure.
Si prende il messaggio, si cifra e si manda sul canale insicuro il cifrato concatenato con l'attestato di autenticità costruito sul messaggio.-->

## Anonimato/Identificazione

Per _identificazione_ si intende un insieme di azioni che richiedono di identificare chi sta partecipando a un'interazione. Ad esempio, quando effettuiamo un pagamento o quando si vuole accedere a certe risorse. L'opposto dell'identificazione è l'anonimato. Si usa, ad esempio con le monete elettroniche o con il voto elettrinico.

Il processo di identificazione ha le seguenti caratteristiche:

- **Real-time**: l'identificazione deve avvenire in un **preciso** istante e non in un secondo momento. Non posso identificare in un secondo momento perchè altrimenti come si fa a sapere che l'identificando è davvero lui? L'unico modo sarebbe quello di prolungare la procedura nel tempo;
- **Efficienza**: l’identificazione di una entità deve avvenire in maniera _efficiente_ proprio perchè avviene in real-time;
- **Sicurezza**: possono essere presenti:
  - **Falsi positivi**: una determinata persona ha diritti di accesso, ma non riesce ad accedere. Ciò causa inefficienza. Bisogna minimizzare questo numero;
  - **Falsi negativi**: l'accesso viene effettuato da persone non autorizzate (si spacciano per chi non sono xD). Non bisogna avere questi casi.

Un sistema di identificazione si può basare su:

- **Conoscenza**: sistemi che si basano sulla conoscenza di un'informazione. Ad esempio, password, pin, chiavi di sicurezza;
- **Possesso**: sistemi che si basano sul possesso di un oggetto che solo quella persona può avere. Ad esempio, carte magnetiche, token, smart card;
- **Conformità**: sistemi che si basano su una caratteristica di un'entità. Ad esempio, dati biometrici come impronte o analisi della retina, dati comportamentali come quanti login fa durante il giorno, quante volte entra ed esce dall'ufficio etc.

E' possibile che un sistema abbia anche più sistemi di identificazione. Ad esempio, conoscenza e possesso oppure conoscenza, possesso e conformità. A seconda dell'informazione che vogliamo proteggere si sceglierà il sistema più adatto perchè ci sarà un costo computazionale, di gestione etc.

### Protocollo di identificazione

![kronk](/img/img8.png)

Qualunque protocollo di identificazione prevede:

- **Registrazione**: durante la registrazione, l’identificando ed il verificatore concordano e memorizzano rispettivamente il dato segreto S con cui l'identificando si farà riconoscere ed il t_ermine di paragone_ T=H(S) che consentirà al verificatore di accertare che l'identificando conosce S.
- **Identificazione**: l'identificando e il verificatore devono essere entrambi online (univocità del tempo).
Questo processo può scomporsi in:
  - **Dichiarazione**: l'identificando dichiara chi è;
  - **Interrogazione**: il verificatore interroga l'identificando che deve dimostrare che sia davvero lui chi dice di essere;
  - **Dimostrazione**: l'identificando deve fornire la stessa prova che aveva fornito in fase di registrazione. La dimostrazione deve essere facile per chi è il legittimo identificando mentre difficile per l'intrusore.

![kronk](/img/kronk.jpeg)

Un intrusore può:

- Dedurre o indovinare la prova (il segreto);
- Rubare il dispositivo (smartcard, occhio etc.);
- Replicare una prova che ha viaggiato sul canale in una legittima transizione di identificazione e riutilizzarla.

## Funzioni one-way

Una funzione `f` è detta unidirezionale se:

- è invertibile (anche se il nome inganna);
- è facile da calcolare: dato lo spazio di input `x` è facile calcolare l'uscita `f(x)`;
- è difficile dato `f(x)` risalire alla `x` che ha originato l'output.

Ad esempio, sono funzioni unidirezionali la:
- **Funzione hash crittograficamente sicura**;
- **Funzione di cifratura**: chi non conosce la funzione `D` è difficile che possa risalire al dato in chiaro;
- **Funzione di autenticazione**: la funzione `S` non è in grado di generare un messaggio correttamente verificabile.

Nella teoria matematica, non esistono funzioni che siano unidirezionali. Nella pratica, invece, sono state individuate molte funzioni che sono candidate ad avere un comportamento di unidirezionalità. Vengono chiamate _pseudo-unidirezionali_ perchè se non si possiede un'informazione, non è possibile trovare la funzione inversa.

## Trasformazioni segrete

Possiamo avere tre approcci:
- **Macchine a funzionamento segreto**: non conoscere come è formata la macchina. Ad esempio, la Macchina Enigma;
- **Algoritmo**: le operazioni sono segrete. Ad esempio, gli algoritmi delle prime SIM, algoritmi USA durante la guerra fredda;
- **Parametro**: la macchina e l'algoritmo sono noti ma un parametro di ingresso dell'algoritmo è segreto (chiave crittografica).

I primi due approcci non funzionano molto bene perchè:
- **No manutenibilità**: è impossibile che non si possa violare la segretezza di una macchina o di un algoritmo. Non è immediato ripristinare la sua sicurezza perchè si dovrebbe riprogettare tutto da zero;
- **No scalabilità**: non si può pensare questo approccio su grande scala come internet. Cosa succede se una macchina segreta viene violata?;
- **No Certificazione**: chi è che mi garantisce che quello che stiamo usando è davvero sicuro se nessuno conosce come è stato costruito?

L'approccio usato al giorno d'oggi, quindi, è il terzo.

![chiave](/img/img9.png)

- Con `T` si indica la trasformazione nota (quindi la conosce anche l'intrusore);
- Con `k` indichiamo la _chiave_ cioè il parametro non noto ed è un parametro di ingresso;
- Con _spazio delle chiavi_ si intende l'insieme delle `2^n` possibili configurazioni dove `n` è il numero di bit della chiave. La chiave è costituita da una delle `2^n` configurazioni. Più è grande `n` più è difficile per un intrusore indovinare la chiave.

## Algoritmo forza bruta

![intrusore](./img/img10.png)

Un intrusore può sempre disporre di un _algoritmo di ricerca esauriente_ noto come _algorimo di forza bruta_. Se l'intrusore non conosce la chiave, può esplorare tutto lo spazio delle chiavi. Se `n` è il numero di bit della chiave e `2^n` è il numero totale di configurazioni, prova tutti i tentativi fino a quando non la indovina. Ovviamente deve conoscere la trasformata `T`. Se il cifrato che ottiene è uguale a quello sul canale, vuol dire che è riuscito a trovare la configurazione corretta.

## Relazioni fra le chiavi

Si possono individuare due famiglie di cifrari:

- **Cifrari a chiavi simmetriche**: le chiavi `ks` e `kd` o sono uguali o facilmente calcolabili una dall’altra. Le chiavi sono le stesse quindi devono essere tenute segrete.
- **Cifrari a chiave pubbliche**: le chiavi `ks` e `kd` sono diverse e una delle due è difficilmente calcolabile dall'altra. Ogni entità dispone di una coppia di chiave `ks` e `kd` di cui `ks` è segreta mentre `kd` pubblica. Dalla conoscenza della chiave pubblica non è possibile risalire alla conoscenza della corrispondente chiave segreta.

### Proprietà delle chiavi simmetriche

Le chiavi simmetriche devono avere le seguenti proprietà:

- **Robustezza**: un intrusore non deve essere in grado facilmente di individuare la chiave. Se una chiave è formata da `n` bit, più grande è lo spazio delle chiavi più è difficile individuare i bit corretti;
- **Riservatezza**: il sistema deve garantire la riservatezza della chiave perchè le chiavi `ks` e `kd` devono essere segrete;
- **Integrità**: quando si decifrano i dati, si deve essere sicuri che la chiave non sia stata alterata altrimenti non è possibile decifrarli;
- **Autenticità**: la chiave è conosciuta solo dalla sorgente autentica e dalla destinazione autentica.

### Proprietà delle chiavi asimmetriche

Le chiavi asimmetriche devono avere le seguenti proprietà:

- **Riservatezza**: la riservatezza è legata alla chiave `ks` privata;
- **Integrità**: è importante che la chiave privata `ks` che si sta utilizzando sia quella corretta e non modificata. Lo stesso vale per la chiave pubblica `kd`;
- **Autenticità**: per quanto riguarda la chiave pubblica `kd`, si deve sapere con certezza a chi appartiene. Se non si è certi, vuol dire che non si sa a chi sta inviando i dati.

## Crittanalisi

Come detto in precedenza, la crittanalisi si occupa di progettare tutte quelle trasformazioni che minano le proprietà di sicurezza.
Ci sono diversi criteri da seguire per non far risalire all'intrusore la chiave:

- **Indovinarla**;
- **Intercettarla**;
- **Dedurla**.

### Indovinare la chiave

E' sempre possibile risalire alla chiave perchè esiste l'attacco con _forza bruta_. Per ridurre questo attacco si devono adottare alcuni accorgimenti:
- **Lo spazio delle chiavi deve essere molto grande**: se `n` è il numero di bit che rappresenta la chiave, `2^n` è l'insieme delle possibili configurazioni. Più è grande `n` più è difficile per un intrusore indovinare la chiave;
- **I bit devono essere casuali**: i bit possono essere anche tanti ma devono essere anche scelti a caso. Non ci deve essere un pattern;
- **Limitare il numero di prove che l'intrusore ha a dispoziione**: ad esempio il pin del bancomat. Dopo tre accessi si disabilita l'accesso;
- **Cambiare frequentemente la chiave**: quando si sceglie una chiave, ci si deve chiedere sempre per quanto tempo viene utilizzata per cifrare i dati. Se i dati devono essere mantenuti per un periodo molto lungo, bisogna cambiare frequentemente la chiave. In questo modo, si riducono le probabilità di individuarla da parte dell'intrusore.

### Intercettare la chiave

La chiave se è un parametro può essere intercettata. Ogni volta che si deve eseguire l'algoritmo, vuol dire che bisogna mettere in RAM l'algoritmo e i parametri. Il parametro sicuramente deve essere memorizzato in maniera sicura (cifrato) e solo il proprietario deve avere accesso alla cella in cui è memorizzata la chiave.

Si deve evitare anche che quando si mette il parametro sul bus non ci sia modo di intercettarlo. Ci deve essere anche un supporto alla sicurezza che protegga la RAM.

Inoltre, l’unità di elaborazione dopo aver eseguito l'algoritmo deve cancellare poi accuratamente il dato dalla memoria.

Nel corso, l'hardware è sicuro ma non è detto che lo sia.

Esistono diverse celle di memoria dove può risiedere la chiave:
- **Soluzione meno robusta**: calcolatore costituito da HDD, CPU e RAM;
- **Soluzione intermedia**: supporto di memorizzazione come ad esempio, smart card passiva in cui si conserva solo il segreto. Si ha bisogno di un pc per poter eleborare. Quindi il segreto passa per la RAM;
- **Soluzione sicura**: smart card attiva in cui c'è anche una CPU e RAM. Nulla viene eseguito all'interno di un calcolatore.

I motivi per cui la soluzione viene classificata come sicura, intermedia e meno robusta si intuiscono leggendo la parte iniziale del paragrafo.

## Esempio

Un sistema di memorizzazione che salva una chiave su file system prende il nome di _portachiavi_. Tutti i segreti vengono salvati a partire da una passphrase definita dall'utente.

C'è un problema: se si perde la passphrase? Serve un sistema di recovery.

## Dedurre la chiave

Esistono diverse tipologie di attacco:

- **Attacco con solo testo cifrato**: l'intrusore dispone esclusivamente di testo cifrato che lo preleva dal canale insicuro. L'intrusore può sfruttare conoscenze, ipotesi sul linguaggio di origine che è stato usato per scrivere il messaggio cifrato, può disporre di tecniche e statistiche per effettuare determinati attacchi. Avendo il testo cifrato e queste tecniche può dedurre delle informazioni sul testo originario o sulla chiave stessa;
- **Attacco con testo in chiaro noto**: l'intrusore ha la fortuna di avere il testo in chiaro del messaggio e il suo cifrato;
- **Attacco con testo in chiaro scelto**: l'intrusore sceglie un testo in chiaro e ha la possibilità di cifrare il messaggio;
- **Attacco con testo cifrato scelto**: l'intrusore riesce a farsi decifrare un testo cifrato da lui scelto dalla sorgente legittima.

La contromisura da adottare è quella _preventiva_: bisogna fare in modo che l'uscita di un algortimo crittografico debba essere assolutamente aleatoria cioè la probabilità che una variabile assuma un valore sia la stessa. Purtroppo, non è sempre vero perchè ci sono alcuni algoritmi che impiegati in un certe modalità producono determinismo.

## Teoria della complessità

Finora si è sempre usato i termini di _calcolo facile_. E’ però utile avere a disposizione una definizione rigorosa: per questo motivo si fa riferimento alla _Teoria della complessità_.

La complessità computazionale può essere determinata con una serie di indicatori:

- **Tempo di esecuzione**: ovviamente non è un tempo _vero_ perchè ogni tecnologia ha un concetto di tempo diverso. Per misurare il tempo di esecuzione si fa riferimento al numero di operazioni eseguite dall'algoritmo per terminare;
- **Memoria occupata dal programma**
- **Memoria occupata dai dati**

Negli algoritmi di crittografia gli ultimi due parametri non sono presi in considerazione.

### Definizioni

- **Tempo disecuzione di un algoritmo**: si intende il numero di operazioni `N` che occorre eseguire per terminare l'algoritmo quando il dato d’ingresso è rappresentato da una stringa di `n` bit (`n = log [valore del dato]`).\
\
Il numero `n` (dimensione input) incide sul numero di operazioni richieste, in alcuni casi, anche il valore stesso può incidere sul numero di passi da eseguire. Dunque, a parità di `n`, si hanno diversi valori di `N`.

- **Tempo di esecuzione nel caso peggiore**: si intende il numero massimo di operazioni `N_max` che occorre eseguire per qualsiasi dato d’ingresso di `n` bit.\
\
La notazione che si usa è _O grande_ perchè evidenzia come proprio si incrementa il tempo di esecuzione al crescere senza limiti. Se `n` non è esprimibile analiticamente, bisogna trovare una funzione che approssima l'andamento della funzione. 

### Classificazione degli algoritmi

Gli algoritmi possono essere classificati in due categorie:

- **Tempo polinomiale**: algoritmo in grado di completare l'elaborazione di una dimensione `n` di dati in ingresso in un tempo di esecuzione pari a `O(n^k)` dove `k` è un numero intero positivo;
- **Tempo esponenziale**: algoritmo in grado di completare l'elaborazione di una dimensione `n` di dati in ingresso in un tempo di esecuzione pari a `O(exp(n))` dove `n` è la dimensione `n` di dati in ingresso.

### Classificazione dei problemi

Un problema si può classificare in:

- **Facile**: se esiste un algoritmo polinomiale in grado di risolverlo su una macchina di Turing deterministica;
- **Difficile**: se non sono stati fino ad ora individuati
(e probabilmente non saranno mai individuati) algoritmi che lo risolvono in tempo polinomiale.

### Complessità e Sicurezza

Per ottenere sicurezza non ci interessa sapere l'andamento al crescere senza misura di n ma interessa:

- Trovare il valore n al di sopra del quale l'andamento diventa esponenziale. Se l'andamento è polinomiale l'intrusore è capace di entrare nel sistema. Nel nostro caso la chiave dovrà essere di un numero di bit in modo tale che la ricerca nello spazio delle chiavi diventi esponenziale;
- Non ci interessa difenderci dal caso peggiore ma dal caso migliore. L'intrusore non deve entrare nel sistema facilmente. L'intrusore non si deve trovare di fronte ad istanze del problema di facile soluzione. Ad esempio, i bit della chiave devono essere aleatori.

Le unità di misura da adottare sono:

- **Anno MIPS**: parametro che dipende dalla tecnologia. Il tempo di esecuzione di un attacco è espresso in anni MIPS. Questa unità di misura fa riferimento a quante istruzioni può elaborare un calcolatore e con il passare degli anni il numero di riferimento aumenta. Attualmente un calcolatore in grado di eseguire un milione di istruzioni al secondo;
- **Livello di sicurezza**: parametro indipendente dalla tecnologia. L'algoritmo di _ricerca esauriente_ risolve ogni problema perchè esplorare lo spazio totale degli input è sempre possibile. Bisogna individuare qual è il numero di bit della chiave tale per cui l'andamento diventa esponenziale.

![dedurre](./img/img13.png)

Quanto deve essere grande una chiave?
- In una chiave simmetrica: attacchi possibili: forza bruta. con le tecnologie attuali, siamo quasi certi che l'intrusore usando una chiave a 128 bit non riesce a trovarla
- In una chiave asimmetrica: attacchi possibili: forza bruta sulla chiave privata o un algoritmo di fattorizzazione della chiave pubblica risalire alla chiave privata. Forza bruta: La chiave segreta deve essere maggiore a 128 bit.
Algoritmo sub-esponenziale: > 2000 bit

# 02.Dati Sicuri 2 (07-10-2021)

Adesso dobbiamo capire come sono realizzate le scatole nere del capitolo precedente.

Per generare una chiave crittografica è importante che abbia due determinate caratteristiche:
- Ogni valore deve avere la stessa probabilità di verificarsi;
- Ogni valore deve essere indipendente dal punto di vista statistico dal precedente e successivo.

Dobbiamo evitare che un intrusore possa riuscire ad ipotizzare come sono fatti i bit.

## True Random Number Generator

Per poter rispettare le proprietà appena citate, abbiamo bisogno di due componenti che si chiamano _Generatori di Numeri Random_. Per testare se davvero questi componenti hanno generato una sequenza di numeri casuali, si usa lo _standard FIPS 140-2_.

Non si possono usare questi generatori per generare gradi quantità di chiavi crittografiche per due motivi:
- **Bassa frequenza di generazione**: se bisogna generare grandi quantità di chiavi in un tempo brevissimo non è adatto;
- **Non riproducibilità**: mittente e destinazione devono disporre dello stesso segreto per applicare una determinata trasformazione che protegge una proprietà della sicurezza. Se il mittente genera una chiave deve passarla al destinatario assolutamente altrimenti se il destinatario provasse a generare una chiave non otterrebbe mai la stessa

## Pseudo Random Number Generator

Per superare principalmente il problema della _Non riproducibilità_ si usano questo altro tipo di generatori.
Componenti che consentono di generare lunghe sequenze di numeri casuali in modo deterministico a partire da un dato iniziale che chiamiamo _seme_. Se il dato iniziale è uguale sia dalla sorgente che dalla destinazione, viene riprodotta la stessa sequenza di bit.

Per generare questa sequenza di numeri possiamo usare degli automi a stati finiti.

Questi generatori ci consentono di avere le seguenti proprietà:
- **Casualità**: i bit vengono generati casualmente (vedi proprietà in alto)
- **Riproducibilità**: dallo stesso seme otteniamo la stessa sequenza

Problemi:
- **Imprevedibilità**: dopo un certo numero di bit è possibile individuare ogni successivo valore.

## Cryptographically Secure PseudoRandom Bit Generator

Nella sicurezza informatica, abbiamo bisogno di _Generatori Pseudo Casuali Crittograficamente Sicuri_.

- **Casualità**: i bit devono essere casuali
- **Imprevedibilità**: esiste un test Next-bit test che consente di verificare se esiste un algoritmo polinomiale in grado di predire il bit L+1-esimo con probabilità > 0,5.
- **Indeducibilità**: il seme non deve essere individuato e neanche osservando i bit dell'uscita risalire al seme iniziale. Dunque, è importante che le funzioni siano unidirezionali.

Esistono diversi componenti che sfruttano gli algoritmi di crittografia per produrre in uscita questi bit casuali:
- Crittografia simmetrica: le proprietà sono solo sperimentalmente verificabili ma hanno alta velocità di generazione delle sequenze di uscita
- Crittografia asimetrica: si può dimostrare che l'uscita è casuale, imprevedibile e indeducibile ma hanno prestazioni più basse.

## PRNG

E' lo standard di riferimento per la costruzione di _Generatori Pseudo Casuali Crittograficamente Sicuri_. Esso prevede che il seme sia generato da un True Number Generator una tantum. A questo punto il seme viene dato in pasto ad un PRNG (automa a stati finiti) e la funzione deve essere unidirezionale.

## Algoritmi di hash

Le proprietà devono essere:
- **Efficienza**: deve essere facile da calcolare anche se il messaggio in ingresso è molto lungo
- Robustezza: possiamo avere due tipi di robustezza:
  - **Robustezza debole**: dato un input x a cui corrisponde un'impronta H(x), deve essere computazionalmente difficile per l'intrusore trovare un y != x tale per cui H(y) = H(x);
  - **Robustezza forte**: deve essere difficile trovare una coppia di sua scelta x e y tale per cui abbiamo l'impronta identica H(y) = H(x).
- **Unidirezionalità**: data un'impronta deve essere computazionalmente difficile risalire al messaggio originario che l'ha generata.

![dedurre](./img/img14.png)

Per garantire efficienza, la maggior parte degli algoritmi utilizzano uno schema di Merkle-Damgard (compressione iterata). Consiste nel prendere il messaggio di lunghezza arbitraria e suddividerlo in blocchi prefissata a seconda dello specifico algoritmo di implementazione di f. Al primo blocco viene applicato a m0 una funzione unidirezionale con le caratteristiche di robustezza, debole e forte alle collisioni e unidirezionalità, applico a m0 di r bit (r>n) al primo passo la funzione f e un vettore di inizializzazione che avrà un valore iniziale. In pipeline, viene poi elaborato il secondo blocco m1 concatenato all'impronta generata al passo precedente. L'impronta h-iesma al passo i-esimo è ottenuta applicando una funzione unidirezionale e resistente alle collisioni, all'impronta ottenuta al passo ottenuto i-1 e al blocco i-1.
L'impronta finale corrisponde con l'ultima impronta generata dall'ultimo blocco.

Questo schema è soggetto ad un attacco che si chiama _attacco con estensione_.

![dedurre](./img/img15.png)

Dalla sorgente A inviamo un messaggio m concatenato al suo attestato di autenticità costruito con la funzione hash H(s||m) dove s è il segreto condiviso tra mittente e destinatario. Se la funzione hash è implementata secondo lo schema di Merkle-Damgard, l'implementazione è vulnerabile ad un attacco. L'intrusore aggiunge un messaggio m' a quello già esistente. Ora ha bisogno di calcolare il nuovo attestato di autenticitò. L'intrusore sfrutta l'impronta H(s||m) che viene mandata sul canale e anche se non conosce s, riesce ad usare H(s||m) come input dei blocchi f che mi elaborano le impronte sulla parte restante del messaggio m'.

Come si evita il problema:
- Compressione iterata: l'ultimo blocco prende delle informazioni aggiuntive ad esempio qual è la lunghezza del messaggio. Tuttavia, non è sempre robusto. Se il messaggio non è dotato di significato, l'attacco ha successo.

<!--esempio? -->

![dedurre](./img/img16.png)

Le funzioni non garantiscono sempre la resistenza alle collisioni. Per ridurre questi attacchi, non ci si limita a comprire solo una volta ma lo si fa più volte. La doppia compressione consente alle funzioni hash di avere un comportamento aleatorio.

La resistenza alle collisione è importante:
- Firma digitale: la firma la si da alla trasformazione S ma all'impronta del messaggio. Se esiste un m' tale per cui H(m) = H(m') non è più valido oppure ?!?!?!?

L'unidirezionalità è importante in due scenari:
- Firma digitale: un intrusore potrebbe generare tramite un PRNG un r. L'intrusore può sempre calcolare V(r). V è nota a tutti e può calcolare tramite una PU x. L'intrusore vuole generare un r come se fosse stato firmato da una determinata persona. facendo H^-1(x) riesco a trovare un y!?!?!??!?

## Dimensionamento dell'impronta

Quanti bit deve avere un'impronta per essere sicura? Le funzioni devono avere un comportamento aleatorio cioè deve restituire una delle 2^n configurazioni casuali. Quanto tempo ci mette un intrusore per trovare una collisione? Con P1(2^n, 1) = 2^-n la probabilità di un tentativo di trovare una collisione. Se ho k tentativi P1(2^n, k) = 1 - (1-2^-n)^k. Si dimostra che la probabilità dopo k tentativi è proporzionale a k*2^-n. Questo vuol dire che k=S.2^n. L'n per essere esponenziale è 128. Dunque, l'impronta deve essere almeno 128 bit.

Per garantire la resistenza forte non bastano 128 bit. Il numero di bit deve essere il doppio. In realtà, serve quando abbiamo a che fare con la firma digitale, o nel seguente scenario:
- L'intrusore prepara 2 versioni di un contratto: M-M' in cui collidono. Alla persona fa firmare M che è quello favorevole e l'intrusore cambia contratto con M' tanto hanno la stessa impronta. Per la resistenza forte vedremo che ci vogliono 2^(n/2) tentativi (più facile della debole.)

# 03.Meccanismi Simmetrici

**Sicurezza computazionale**: un cifrario è detto computazionalmente sicuro se è possibile risalre dal testo cifrato corrispondente al testo in chiaro ma richiede una potenza di elaborazione superiore a quella a disposizione dell'intrusore.

D'ora in poi abbiamo a che fare con cifrari computazionalmente sicuri (e non perfetti che significa?).

Per la teoria dellinformazione sviluppata da Shannon, il cifrario è computazionalmente sicuro se adotta i criteri di:
- **Confusione**: la relazione tra la chiave e il testo cifrato è più il possibile complessa e scorrelata. L'uscita del cifrario è aleatorio e l'aleatorietà non permette di individuare la relazione tra testo cifrato e la chiave usata.
- **Diffusione**: la capacità di un algoritmo di nascondere la ridondanza del testo il più possibile nell'uscita dell'algoritmo di cifratura. Se si riesce a nascondere la ridondanza del testo nel cifrato, viene impedito all'intrusore di usare tecniche basate sull'analisi statistica.

Se costruisco un cifrario che usa il principio della confusione, il messaggio cifrato non fornisce informazioni sulla chiave.

Se costruisco un cifrario che usa il principio della diffusione, so che se modifico solo un carattere del messaggio in chiaro, questa modifica sul singolo carattere non si ripercuote nel corrispondente carattere del messaggio cifrato ma provoca una modifica spalmata su tutto il cifrato.

- Tecnica di sostituzione: tecnica che garantisce la confusione.
- Tecnica di trasposizione: tecninca che garantisce la diffusione.

## Cifrario simmetrico

Dalla teoria di Shannon discende che un cifrario simmerico è computazionalmente sicuro se usa diffusione e sostituzione.

Il cifrario simmetrico vengono utilizzati per garantire riservatezza. In rari casi, viene usato per garantire autenticazione, generatori di numeri pseudo-casuali crittograficamente sicuri e dei protocolli di identificazione.

Esistono come cifrari simmetrici due famiglie distinte:
- **Cifrario a flusso**: si rifà al cifrario perfetto (one time pad). E' un cifrario che opera su uno o pochi bit alla volta con una regola variabile al progreddire del testo. garantisce la  protezione dei singoli bit di una trasmissione seriale. Ad esempio, nel settore della telefonia, applicazione web etc.
- **Cifrario a blocchi**: si rifà al cifrario poligrafico composto visto nella teoria di Shannon. trasforma con una regola fissa ed uno alla volta, blocchi di messaggio formati da molti bit. Ad esempio, protezione di pacchetti, di file, posta elettronica etc.

Un cifrario a flusso, è più veloce di un cifrario a blocchi e non introduce rallentamenti. Se impiegato non correttamente, è meno sicuro di un cifrario a blocchi non impiegato correttamente.

## Cifrario a flusso

Si rifà ad un cifrario one-time pad, prende un bit chiaro, fa l'operazione di encryption e somma modulo 2 con un bit di chiave aleatoria e produce in uscita un bit cifrato.

Encryption e Decryption sono implementati con degli XOR. prendo un bit di testo in chiaro e lo metto in XOR con un bit di chiave. Ad esempio, se il messaggio è lungo 1000 bit, la chiave è lunga 1000 bit. Lo stesso flusso di chiave non può essere impiegato su messaggi diversi. Il flusso di chiave lo genero con un PRNG. In decifrazione, al bit i-esimo del messaggio, deve essere sommato modulo 2 la corrispondente k-iesmo usata in cifratura. Per questo motivo ci deve essere sincronismo tra flusso di chiave tra livello sorgente e livello di chiave.

Perchè non è perfetto?
Non si può generare un flusso completamente casuale ma dopo un periodo di tempo si ripete. Il seme mi permette di scegliere una sottosequenza a caso all'interno di questo periodo lunghissimo. Il periodo per quanto lungo se si esaurisce si ripete. Per questo motivo è computazionalmente sicuro e non perfetto.

Flusso di chiave: la chiave deve essere lunga quanto il testo, formato da bit psuedo-casuali e la sottosequenza scelta in segreto e a caso all'interno di un periodo lunghissimo.

I cifrari a flusso sincrono si suddividono in:
- **Cifrario a flusso sincrono**: il flusso di chiave dipende solo dal seme 
- **Cifrario a flusso autosincronizzante**: lo stato futuro dipende dal seme ma anche dai bit di testo cifrato precedente

Nel flusso sincrono, l'attaccante può effettuare attacchi attivi: modificare, cancellarli o aggiungere bit di testo cifrato.

Caso cifrario a flusso sincrono
-Se si modifica un bit del cifrato: la destinazione non decifra correttamente un bit perchè è stato cambiato. Si dice che non si ha perdita di sincronismo perchè ki è sempre lo stesso ma la decifrazione non è corretta.
- Se si cancella un bit: dal punto in poi in cui è stato cancellato il bit, non corrisponderà mai a quelli inviati. Si dice che si ha perdita di sincronismo.

Caso cifrario a flusso autosincronizzante
- Se si modifica, cancella o elimina un bit del cifrato: si ha una perdita di sincronismo non permanete ma solo di un transitorio. E' il transitorio legato alla dimensione del registro di scorrimento (SHIFT) e quanto il bit modificato/cancellato/inserito rimane dentro a questo registro.

I più usati sono quelli a flusso sincrono perchè i componenti a cifrario a flusso autosincronizzante sono più costosi.

Se si usa lo stesso flusso di chiave su messaggi distinti si possono fare attacchi di analisi sui cifrati perchè si sfrutta la proprietà dell'OXR.
Ad esempio, si consideri:
m1 XOR k = c1
m2 XOR k = c2
c1 XOR c2 è come fare l'XOR su due messaggi in chiaro:
m1 XOR m2

Alcune volte, nei protocolli ci si accorge che è possibile sfruttare questa proprietà dell'XOR ed effettuare gli attacchi (es. WEP).

![marco togni](./img/img17.png)

Il vettore di inizializzazione ha una dimensione limitata (24 bit). Dopo 2^24 generazioni, si ha che la chiave si ripete. Inoltre, quando si spegneva, il vettore si inizializzava a zero e poi funzionava ad incremento. Il comportamente è molto prevedibile.

# 11/10/2021

## Malleabilità

La proprietà di malleabilità consiste nella possibilità di alterare il cifrato in modo da produrre un effetto desiderato sul testo in chiaro originario. Purtroppo, i cifrari a flusso sono vulnerabili a questa proprietà. L'attaccante conosce qualcosa M o una sua parte, il mittente fa M XOR k, l'attaccante prende (M XOR k) XOR p (è scelto dall'attaccante) e sostituisce a quello che viaggiava prima, il nuovo messaggio cifrato cifrato. La destinazione, decifra ((M XOR k) XOR p)) XOR k e quindi si ottiene m XOR p.

E' importante per aver successo, che l'attaccante conosca almeno una parte del messaggio.

Ad esempio, il mittente sta cifrando dei dati strutturati. All'inizio dei questi dati c'è sempre "From". L'attaccante, conosce che il flusso è strutturato. Il suo obiettivo è quello di far spacciare i dati provenienti da un altro mittente.

![marco togni](./img/img25.png)

Ipotiziamo che l'inizio del messaggio sia "From Bob" con rappresentazione esadecimale "42 6F 62". L'obiettivo dell'intrusore è ottenere "From Eve" con rappresentazione esadecimale 45 76 65. Bisogna trovare quel p tale per cui m XOR p = Eve. Dunque, p deve essere "07 19 07".
Basta osservare solo il comportamento dell'XOR senza sapere niente sulla chiave.

## Modalità di cifratura

Nei cifrari a blocco, l'attacco forza bruta a senso perchè è sempre la stessa. Dunque, bisogna dimensionare la chiave almeno con 128 bit.

Si prende un messaggio e lo si suddividono in blocchi.
La lunghezza del blocco dipende dallo specifico algoritmo per cifrare/decifrare i blocchi. L'ultimo blocco contiene i bit del testo in chiaro originario. Se lo contiene completamente viene aggiunto un blocco in più detto blocco di padding. Se i bit del messaggio originario non lo riempono completamente, si arriva a completamento del blocco riempendo opportunamente i restanti bit con tecniche standard. Nella modalità base ECB (Electronic Code Book) prevede di elaborare in parallelo i blocchi m1....mn. Ogni blocco viene dato in pasto alla funzione di encryption e quindi il cifrato non è altro che la concatenazione dei cifrati ottenuti sui singoli blocchi. Tale modalità di cifratura è fortemente deterministica: a blocchi in chiaro identici corrispondono blocchi cifrati assolutamente identici. I pattern non sono una buona cosa nella sicurezza informatica perchè sono tutte possibili vulnerabilità.
Altro problema è quello della maleabilità: un intrusore è in grado di modificare il testo cifrato in modo tale che la destinazione quando lo decifra ottiene un testo arbitrario da lui scelto? si. ECB è malleabile.

Pro:
- grande efficienza: CPU parallela
- se l'intrusore modifica a caso un bit, si dice che la propagazione dell'errore rimane confinata al cifrato. Chi decifra avrà solo un blocco "sbagliato".

Questa modalità si conserva solo in casi specifici: ad esempio, cifrare delle informazioni che sono già per natura aleatoria (es. chiave di sessione).

L'obiettivo, quindi, è quello di trovare modalità di cifrature aleatori. Ad esempio, esistono le modalità CBC, CFB, OFB, CTR.

### Cipher Block Chaining (CBC)

![marco togni](./img/img18.png)

La modalità CBC prende il messaggio in chiaro, lo suddivide in blocchi, l'ultimo blocco sottoposto a padding. Per ogni blocco, il testo in chiaro viene messo in XOR con un altro dato e sottoposto poi alla funzione di cifratura E ottenendo un testo cifrato ci. Solo per quanto riguarda il blocco 1, il testo in chiaro viene dato in XOR con quello che si chiama vettore di inizializzazione. E' un insieme di bit, grande quanto il blocco. Tutti gli altri blocchi al posto del vettore di inizializzazione usano l'uscita del blocco precedente. Per ottenere aleatorietà la si ottine grazie al vettore di inizializzazione.

Le caratteristiche di questo vettore sono:
- Deve essere casuale;
- Imprevedibile;
- Usato una e una sola volta: perchè se ripeto il vettore e si hanno due messaggi uguali, si ottiene lo stesso cifrato.

Se come intrusore, modifica un qualcunque bit di un blocco, l'errore si propaga nei blocchi precedenti. Se questa modalità usata correttamente si ottiene aleatorietà, stessa occupazione di banda ma si perde efficienza perchè si perde il parallelismo. Invece, il parallelismo lo si ottiene in fase di decifrazione se si hanno già tutti i pezzi di cifrato che costituiscono.

### Chipher Feedback (CFB)

![marco togni](./img/img19.png)

Questo schema ricorda un cifrario a flusso. E' come convertire una cifratura a blocchi a una di flusso. Ciò consente di evitare il padding. Si usa, ad esempio, quando si ha una trasmissione carattere per carattere (8 bit alla volta) orientata al flusso di carattere.

Si parte da un vettore di inizializzazione, non è necessariamente segreto, imprevedibile e usato una sola volta. Serve per inizializzare lo stato di un registro a scorrimento che è costituito da due parti: una parte formata dagli s bit meno significativi e l'altra dai b-s bit più significativi. Il registro a scorrimento viene sottoposto ad una cifratura grazie ad un algoritmo a blocchi (es. ECB) e con la rispettiva chiave. Il cifrato finale è ottenuto mettendo in OXR s bit del testo in chiaro con gli s bit più significati dell'operazione di cifratura. Il risultato è il cifrato costituito da s bit.

Il registro è a scorrimento e lo si fa scorrere di s bit e quindi scorrendo a sinistra deve metterne nel registro altri s. I nuovi bit sono quelli del cifrato del passo precedente. Al passo 2, i b-s bit contengono ancora alcuni vecchi bit del vettore di inizializzazione ma prima o poi i bit di questo vettore vengono buttati fuori.

Questo schema ricorda lo schema a flusso autosincronizzante.

![marco togni](./img/img20.png)

In decifrazione, si procede analogamente. Per decifrare il primo blocco di testo in chiaro bisogna avere il cifrato ottenuto al passo precedente vuol dire scorrere indietro. La prima cosa da fare è partire dall'ultimo blocco e recuperare a ritroso.

In fase di decifrazione, si usa sempre la stessa funzione E cioè l'implementazione dell'algoritmo è la stessa. Non è detto che sia sempre così perchè l'algoritmo D potrebbe essere diverso. In questo caso, si usano circuiti diversi.

### Output Feedback (OFB)

![marco togni](./img/img21.png)

Questo schema ricorda un cifrario a flusso sincrono. E' come convertire una cifratura a blocchi a una di flusso. Ciò consente di evitare il padding. Si usa, ad esempio, in una trasmissione di caratteri orientato ad un flusso di dati tipicamente rumorosi come i satelliti.

Si parte da un vettore di inizializzazione che serve sempre per inizializzare lo stato di un registro. Il registro a scorrimento viene cifrato e gli s bit più significativi dell'output vengono messi in XOR con gli s bit del testo in chiaro. Nel registro a scorrimento va a finire nei bit meno significativi, gli s bit più significativi della funzione di cifratura.

![marco togni](./img/img22.png)

In decifrazione, non si usa la funzione inversa ma si continua ad usare la funzione di encryption.

L'OFB si preferisce ad usare quando i canali sono rumorosi perchè la modifica di un cifrato non si propaga sul blocco successivo.

### Counter (CTR)

C'è sempre la suddivisione dei blocchi e ogni blocco viene potenzialmente lavorato indipendentemente dagli altri. I bit di testo in chiaro di ogni singolo blocco vengono messi in XOR all'uscita di un cifrario a blocchi che cifra il valore casuale ed imprevedibile do un contatore. Tutti i blocchi successivi, partono dal valore del contatore iniziale incrementato di 1. I blocchi possono lavorare in parallelo sia in fase di E che di D.
Ad esempio, viene usata su reti ATM.

### Beast Attack (Browser Exploit Against SSL/TLS)

![marco togni](./img/img23.png)

Attacco molto difficile da realizzare. Questo attacco prevede che all'inizio di una connessione TCP, le due parti negozino gli algoritmi di cifratura, le chiave della sessione e i parametri che vengono usati dai cifrari come il vettore di inizializzazione e anche la modalità di cifratura da usare. I dati a livello applicativo ha una certa dimensione viene suddivisa in blocchi perchè va a finire in un pacchetto TCP. Ogni pacchetto poi viene concatenato a quello successivo. Se si usa un cifrario a blocchi CBC, a livello applicativo si avranno vettori di una certa dimensione.

![marco togni](./img/img24.png)

Si vuole osservare le comunicazioni tra due partecipanti e si vuole capire se il mittente vuole.

---

![marco togni](./img/marco_togni.jpg)

---
![cyber sesso](https://user-images.githubusercontent.com/56556806/134823047-da26060a-3813-4e73-a13c-256bcd0483c4.png)

# How I Defeated Fascism with the Power of Love

## Chapter 1: The Power of Love

The first step in my journey was realizing that it is impossible to defeat
fascism with the power of love.

## Chapter 2: The Power of Incredible Violence
