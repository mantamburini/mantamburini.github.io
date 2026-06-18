---
title: Struttura di un Processo
date: 2026-06-19 00:00
last-modified: 2026-06-15 12:55
description: Come impostare un documento di processo efficace
draft: true
tags: []
---

Ora siamo davanti al foglio (digitale) bianco. Panico dello scrittore. Possiamo però avere un "processo" per scrivere un "documento di processo", non sarebbe adeguato?

![Il vero processo per scrivere i processi](https://kroki.io/plantuml/svg/eNpdkk9PHDEMxe_5FNZeuiuViva4KxUQXLggJHrk4sl6M5YSe8ifQeLT1wksRZXmMJEdv_d-8XWpmGtL0VWukeA-wkpZYcnqqRSFI0PxmWttGfuhCRzVt0RSR_Hc6NyY5PY3S2bgCCcNkRUmRvF6cPtHFO4_jk-wnXFMqpSWiJWudlBnEtiK7hzA_payx68NUBqwVMpC9dA7HtSKps7oCcQMNNFRuCPPZsu-E1q3DVGozWoUC8G28M6RHPnkXKaFsPY7TxZwZdg8eV0sFMV_ETdj6B8G9F5zYPCz6Zl4sQQTmQCC14JQKK80mm8tMMWIJlurCb_rwOvMsRsgA8q-5SEU1eiaqAHg8h7_4ndho3Q2ZSQzFWPNAr8uIbG0avX9TQjcZBhCCRQ1wGa9_PETLuxJOCFM-vaGmw_eLw2j7yhMMFIIlPEbHHHtb_0__Mc2TZF9z5WavDT6_izW3518bkWn4FUqrviVrN3-9GUUZhrrwhgypoQ2J2FPb_AO51ewaIu7toPt4F8_k9us)

Non è un gioco di parole, ma è il modo giusto, in questo contesto, di iniziare e di affrontare il problema della scrittura. Il "processo" per scrivere questo tipo di documenti è quello che ci garantisce leggibilità, trasmissibilità, correttezza e completezza. Poi ogni documento va giustamente adattato al proprio contesto: il livello di dettaglio, per esempio, varia moltissimo da processo a processo; l'uditorio può influire sulla presenza o meno di un certo tipo di informazioni; e così via. 

Questo però non elimina mai il fatto che si possa partire da uno schema che aiuta a non dimenticare le parti importanti.

## I capitoli imprescindibili

Premessa. Un documento = un process, e viceversa. Difficilmente sarà efficace un documento che descrive più processi. Se ci fosse questa esigenza, potrebbe essere più efficace avere un documento "indice" per i processi che si vogliono descrivere. Questo per mantenere manutenibilità dei processi separatamente, che, mano a mano che il tempo passa, avranno vite sempre più distinte; perché un processo potrebbe andare deprecato e quindi uscire dal corpus oppure un processo potrebbe modificare la sua ownership.

Ci sono una serie di informazioni, che divideremo in capitoli, che sono *imprescindibili*, che sono la condizione di "comprensibilità" e "usabilità" di un documento che descriva un processo.

Riassumiamo in questa tabella le informazioni il contenuto tipico.

|                 Capitolo | Informazioni di base                                                                                           |
| ------------------------:| -------------------------------------------------------------------------------------------------------------- |
|             Intestazione | Nome del documento, autore, versione, data e oggetto.                                                          |
|                Changelog | Tabella con le varie edizioni del documento e quali sono, per ogni edizione, le principali modifiche apportate |
|      Scopo del documento | Breve descrizione del perché questo documento esista.                                                          |
|   Ruoli e responsabilità | Tabella con le persone di riferimento del processo.                                                            | 
| Descrizione del processo | Descrizione dei passaggi e grafico delle operazioni                                                            |

### Intestazione 

È il modo per identificare univocamente il documento. Che sia un numero, un codice, un nome, un elemento comunque che renda quel documento solo *quello*. Un documento ben fatto contiene anche data e versione che contribuiscono a capire se stiamo usando la versione corretta; questa sezione contiene anche l'autore del documento in modo che sia immediato risalire alla fonte della conoscenza.

### Changelog 

È indispensabile sapere quali modifiche sono state apportate al documento per 1) potersi concentrare solo sulle novità, nel caso il documento sia già ben noto e 2) per capire l'evoluzione e quindi il contesto operativo in cui il documento si muove. Inoltre, normalmente, le modifiche hanno sempre un autore e un approvatore, che potrebbero variare e quindi servono a identificare la fonte della conoscenza per quel documento o per quella sezione di documento.

### Scopo del documento 

Questa è forse la sezione più importante, ma spesso anche la più sottovalutata o disattesa. Si possono eseguire delle operazioni perché si sta seguendo una procedura di cui si ha una consapevolezza piccola a piacere oppure si può *capire* cosa si sta facendo. "Capire" significa avere consapevolezza dello scopo (cioè cosa si vuole ottenere) e del valore (cioè quale vantaggio porta questo processo nel momento del suo compimento).

Questa sezione del documento cerca infatti di far comprendere all'esecutore (o al controllare, perché un documento di processo può servire magari anche a chi deve controllare il processo, non solo eseguirlo) **perché** esiste quel processo, quale **esigenza** risolve e quale **vantaggio** porta alla fine della sua esecuzione. 

Molto spesso, l'individuazione di processi inutili (fatti solo per abitudine, ma che non portano nessun valore) o costruiti male (che utilizzano troppe risorse rispetto al vantaggio che portano) o non sicuri (che espongono a rischi non calcolati) passa da chi li esegue, cosciente dello scopo e del valore atteso; "ma perché facciamo questo processo attraverso due computer, quando basterebbe fare questa modifica per utilizzarne uno solo?", "qualcuno ha capito che facciamo queste operazioni ma il file finale è uguale a quello iniziale nella sostanza?"; etc. 

### Ruoli e responsabilità 

Uno dei problemi maggiori che si possono incontrare eseguendo un processo è che quando qualcosa va storto (e qualcosa, prima o poi, andrà storto!) non si sa a chi rivolgersi. Per questo occorre che il documento abbia un proprietario (*owner*) che è responsabile del suo aggiornamento (proprietario che - ci si augura - sia ancora in azienda, perché se il proprietario si licenzia, chi aggiorna i documenti?), ma anche chi ha accesso alle risorse (tecnologiche o economiche) per mandare avanti il processo; occorre sapere chi ha il potere di concedere determinate autorizzazioni formali, per esempio, o chi è responsabile della gestione del rischio. Anche solo il punto di escalation è fondamentale. 

Si può utilizzare anche una tabella [RACI](https://it.wikipedia.org/wiki/Matrice_di_assegnazione_responsabilit%C3%A0) per chiarire quali parti del processo sono a carico di chi. In contesti complessi una matrice di questo tipo è particolarmente utile. In contesti più semplice può essere sufficiente un elenco di responsabilità per le parti del processo e per le parti del documento. Al minimo può essere una persona (ruolo) sola a essere responsabile del processo e - di conseguenza - del documento.

### Descrizione del processo

Questo è ovviamente il cuore del documento. La descrizione può essere in varie forme, a seconda del tipo di processo, ma di solito un grafico BPMN o UML (con le azioni numerate) sono più che esplicativi. Attenzione: i grafici vanno fatti bene. 

Perché le azioni sono numerate? Perché poi ci sarà una tabella con il numero (per identificare il task), il nome, la descrizione, i **risultati attesi**.

## I capitoli facoltativi

### Cosa significa `facoltativo`

Bisogna chiarire un punto molto, molto importante, valido per un sacco di altri ambiti: "facoltativo" non significa "omissibile". Tante volte ho sentito dire "non serve metterlo, è facoltativo"; può essere vero, in alcuni casi, ma nella maggioranza dei casi, il contesto fa diventare obbligatoria una cosa facoltativa. 

### Allegati/Appendici

Un processo potrebbe prevedere di dover compilare un modulo, mandare una email preformattata, rispondere ad un utente con un testo concordato, etc. ... in questo caso potrebbero essere in allegato (o segnati con un link ad un documentale) dei documenti/templates utili allo svolgimento. In questo modo potrebbero anche avere un ciclo di aggiornamento diverso o potrebbero essere condivisi tra più processi diversi. Inoltre potrebbero essere accessibili a persone che non necessariamente vedono il documento di processo o potrebbero essere accessibili agli operatori in sola lettura.

### Riferimenti normativi e documenti collegati

Link a normative o policy aziendali interne che governano, spiegano o limitano il processo. Questi link potrebbero anche essere parte del *perché* viene fatto un processo.

### Glossario

In alcuni contesti potrebbe essere necessario spiegare acronimi che non sono di dominio pubblico o potenzialmente ambigui; oppure potrebbe essere necessario definire delle parole comuni che nel contesto hanno un significato specifico. Si pensi al termine "postazione di lavoro" che a seconda del contesto potrebbe includere o no certe periferiche, per esempio: in questo caso definire cosa si intende per "postazione di lavoro" sarebbe un modo molto efficace per togliere ambiguità.

### Metriche e KPI

Se il processo è misurato, magari addirittura con degli SLA, dal cliente, chi lo esegue deve essere consapevole sia per evitare di non rispettare gli SLA, sia anche per poter pianificare correttamente le attività a dispetto delle richieste esterne. "Ho fretta" non è un KPI.

### Gestione delle eccezioni

Un processo cerca di includere quante più casistiche possibili. Tendenzialmente esisterà sempre un caso che non è stato previsto. In questo caso è utile inserire _come_ vengono gestite le eccezioni; può anche essere semplicemente "decide lui", ma deve essere **esplicitato**. 

### Strumenti e sistemi utilizzati

Una sezione molto importante, nel momento in cui il contesto lo richiede, è quello degli strumenti. Le ragioni sono più d'una:

- Occorre formalizzare quali strumenti vengono utilizzati per fare quali cose. Da un lato un task potrebbe essere fatto solo con un certo tool, dall'altro *dovrebbe* per questioni di sicurezza, per esempio, essere fatto con un certo tool che garantisce standard più alti, non che garantisce la fattibilità.
- Occorre indicare come accedere ai tool utilizzati, senza mettere in chiaro password, ma indicando link, utenze, tipi di utenze, etc. o dove reperire le password o le modalità di accesso per accessi più forti 
- Potrebbe essere necessario chiarire anche chi amministra gli strumenti elencati in caso di necessità di supporto. 

### FAQ / errori comuni

Un'ottima pratica è quella, per i documenti più maturi, raccogliere quelle che - nel tempo - sono state le domande che chi esegue il processo si è posto più spesso. Questa sezione può anche essere un utile strumento di "disambiguazione" di certe terminologie e pratiche non completamente chiare o che possono risultare fuorvianti.

## Conclusione

Scrivere è utile, scrivere bene è difficile, ma scrivere per essere eseguiti, come si diceva prima, è complesso e richiede una pratica specifica. Purtroppo la documentazione, soprattutto quella di processo, è davvero sottovalutata e trascurata, ma ha un impatto enorme. Ricordo che anni fa, da consulente, ho avuto dei rapporti con il reparto IT di una grande azienda (solo nell'IT erano 1.000 persone) e mi hanno fatto vedere la documentazione del processo di *Incident Management*: si trattava di una policy e di tre documenti diversi, perché uno descriveva il processo dal punto di vista del service manager, l'altro dell'application manager e il terzo dal punto di vista dell'incident manager. Ognuno di questi documenti era due o tre pagine, ma la struttura era particolarmente efficace. Il livello di dettaglio era alto (c'erano anche le tabelle sulla scansione temporale dei trigger di avviso di avvicinamento della scadenza degli SLA), ma assolutamente disambiguo e senza fronzoli. Chiaro, semplice, non interpretabile, efficace. 
