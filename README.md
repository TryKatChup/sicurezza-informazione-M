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

Sicurezza dei dati in termini dei requisiti principali come:

- Confidenzialità
- Integrità
- Disponibilità
- Autenticazione
- Non ripudio

Sicurezza hardware: sempre di più si sono scoperte vulnerabilità a livello di componenti fisiche
Area di protezione delle vulnerabilità che vengono dai dispositivi fisici

- Memorie
- Periferiche
- I/O

Protezione dal furto o danneggiamento

Hardware sicuro + firmware sicuro. Vulnerabilità recenti del firmware.

Tecnologie statiche o dinamiche per vedere se il firmware si comporta correttamente.

Chi mi assicura che il software sia integro (software integro, e originale, no modifiche anomale) e autentico (sviluppato da chi ci aspettiamo che abbia fatto il software).

Ci possono essere due metodologie per vedere se il boot è andato a buon fine:

- Trusted boot: tutta la fase di inizializzazione è avvenuta mediante piattaforma trusted, con processori ad hoc che sfruttano la crittografia e chiavi crittografiche che garantiscano integrità del firmware. 
- Secure boot: Interfaccia standard che garantisce al livello software che tutto avvenga in maniera corretta.

- Coprocessori dedicati 


Ci vuole un ente di certificazione che mi garantisca che un prodotto sia sicuro. Esistono diversi standard, come ad esempio esistono delle normative di contromisure di sicurezza


CINI, CERT

Cosa è un attacco? Azione mirata a compromettere una proprietà critica dell'informazione


Prevede che ci sia una sorgente di dati e una destinazione.
Assumiamo che la sorgente abbia un hardware e un ambiente sicuro, che la destinazione abbia un ambiente sicuro, e che il canale di comunicazione sia sicuro.

Sul canale si possono fare diversi attacchi:

- Attacchi attivi: prevede che l'intrusore possa accedere al canale e viene alterato il normale flusso di dati, con le seguenti modalità:

  - Può modificare il normale flusso di dati per minare la sua integrità. Viene minato il contenuto
  - Aggiungere nuove informazioni, viene minata l'autenticità. I destinatari penseranno che il mittente abbia mandato il flusso di dati.
- Attacchi passivi: L'intrusore si inserisce sul canale, ma l'unica cosa che può essere fatta è intercettare i dati. I dati vengono solo osservati.
Non viene alterato il normale flusso di dati.

Sniffer di rete che può intercettare i pacchetti.

Possibili contrimisure di attacco:

- Attacchi passivi: 

  - preventive: azioni atte a minimizzare la probabilità di successo dell'attacco
  - Rilevazione: azioni atte ad individuare che l'attacco è in corso
  - Reazione: azioni atte ad annullare, o almeno a delimitare, gli effetti dell'attacco.

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
