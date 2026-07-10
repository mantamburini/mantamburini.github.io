---
title: Il disegno che si scrive da solo
date: 2026-07-10
description: "Un diagramma dovrebbe essere facile da aggiornare quanto è facile da leggere. PlantUML, Mermaid e il caso a parte di BPMN."
draft: true
tags: [Editor, BPMN, "Sequence diagram", "Linguaggio dichiarativo", Mermaid, PlantUML]
aliases:
  - /posts/il-disegno-che-si-scrie-da-solo/
---

Chiedi a qualcuno di disegnare un flusso e aprirà PowerPoint, trascinerà rettangoli, li allineerà a occhio, li sposterà di due pixel altre dieci volte. Poi il processo cambia e quel disegno smette di essere vero, ma nessuno lo tocca più, perché rifarlo a mano è un pomeriggio perso.

Un diagramma dovrebbe essere facile da aggiornare quanto è facile da leggere. Se non lo è, prima o poi mentirà.

## Proviamo prima a scrivere

Uno dei difetti che abbiamo è che, quando capiamo che un flusso o un processo sarebbe più comprensibile se disegnato (che è generalmente sempre vero), cerchiamo, appunto, di disegnarlo subito. Mentre il più delle volte dovremmo semplicemente iniziare *descrivendolo*.

Vale, analogamente, quanto detto per gli strumenti di scrittura. Nell'articolo precedente si diceva che utilizzare un linguaggio strutturato come `markdown` costringe a pensare in maniera diversa, più strutturata, concentrandosi sul contenuto invece che sull'aspetto.

Per disegnare i processi è molto simile: se ci forziamo a *scrivere* il diagramma invece di disegnarlo, otteniamo gli stessi benefici.

## PlantUML — quello che uso io

```
@startuml
:Buonasera vorrei una pizza da asporto;
:Quale pizza?;
:Margherita;
:Per che ora?;
:Per le 19.00;
:Abbiamo libero solo le 22.00;

note
Tratto da una storia vera
end note
@enduml
```

![Pizza da asporto](https://kroki.io/plantuml/svg/eNoljkEOwjAMBO95hV-ASm-UA4U7Ekh8wKEWtZTGleNw6Otxym1Hs9LuWAzV6pLCcKuSsZAifEWVGGpGWHnbECYELKuoyTkMz4qJ_uLieEf9zKRs6PAghfdMILq7ht49ng5d53iNkXERSBxJBYokabrvdx2yGIWXopm0xTZfTJT9kL8KlCfYK6Mnf_wDewQ-xw==)

Sei righe di testo. Nessun rettangolo trascinato, nessun allineamento a pixel. Scrivi la sequenza degli eventi nell'ordine in cui accadono, il motore calcola il layout; certo bisogna imparare un po' di grammatica e questo per molti non è così immediato. Non decidi tu dove va la freccia -- decidi solo cosa succede dopo cosa. Questo è quello che si intende per linguaggio dichiarativo: descrivi il *cosa*, non il *dove sullo schermo*.

Il vantaggio pratico, oltre a quello concettuale: il sorgente è testo, si aggiorna cambiando una riga invece di ricostruire il disegno. Se il cliente vuole la pizza alle 20 invece che alle 19, cambio una riga e il diagramma si rigenera da solo.

Personalmente uso `PlantUML` (come nell'esempio sopra) perché ha diversi vantaggi. Normalmente si scrive il codice nel testo `markdown` e l'editor di solito può visualizzare l'immagine corrispondente. La maggior parte degli editor lo fanno nativamente oppure con poca configurazione. Per essere ancora più sicuri, come in questo blog, si può inserire il codice nell'editor di [Kroki](https://kroki.io) e ottenere un link che è di fatto l'immagine.

## Mermaid

Va detto tuttavia che lo *standard de facto* è Mermaid, molto più diffuso e interpretato nativamente da moltissimi editor. Il concetto però è uguale, si scrive, il motore disegna. Il focus non è su **quanto è bello quello che ho disegnato**, ma quanto si capisce.

```
sequenceDiagram
    Cliente->>Pizzeria: Vorrei una pizza da asporto
    Pizzeria->>Cliente: Quale pizza?
    Cliente->>Pizzeria: Margherita
    Pizzeria->>Cliente: Per che ora?
    Cliente->>Pizzeria: Per le 19:00
    Pizzeria->>Cliente: Abbiamo libero solo le 22:00
```

![Pizza da asporto](https://kroki.io/mermaid/svg/eNp9jTsOwjAMQHdO4QsglW5kKEKwIrULu1Os1lJaFydZenpcPmPwZFnvPUd6Zpp7ujIOitMObC6BaU60b5qW15WU0cFdVIkhzwiLHREeCBgX0SRv50ea9NUddBkDffBTMXxDHUZbExY7LSn0I4Hon84G2bfD0VVVsXT2nnESCOxJBaIE2aS6NukFcdRXEA==)

Non sono testi **immediatamente** comprensibili, mi rendo conto, ma una volta presa un po' di confidenza, è tutto molto semplice ed evidente. Il motivo per cui vale la pena conoscerlo, a prescindere da quale dei due si preferisca usare: Mermaid è integrato nativamente in GitHub, GitLab, Obsidian, Notion. Un lettore che apre un file `.md` con un blocco Mermaid dentro uno di questi strumenti lo vede già renderizzato, senza configurare niente.

## BPMN

C'è un'eccezione a tutto questo, ed è onesto ammetterla piuttosto che forzarla dentro la tesi.

**BPMN** (Business Process Model and Notation, [BPMN Specification](https://www.bpmn.org/)) non è un tool, è una metodologia, uno standard con una semantica precisa per rappresentare processi di business complessi: swim lane per separare le responsabilità tra ruoli o reparti, gateway per le decisioni condizionali, eventi di inizio, di fine, di errore, di timer. Copre casistiche che un diagramma di sequenza simile a quelli visti sopra non riesce a rappresentare bene. È in grado di poter rappresentare diagrammi anche estremamente complessi, con sottoprocessi annidati e un linguaggio visivo specifico per i momenti di attesa, per le informazioi in entrata, etc. ...

![Esempio di diagramma BPMN](https://github.com/bpmn-io/bpmn-js-examples/raw/main/bundling/resources/screenshot.png)
<small>Esempio tratto dal repository [bpmn-io/bpmn-js-examples](https://github.com/bpmn-io/bpmn-js-examples) su GitHub.</small>

La differenza sostanziale rispetto a `PlantUML` e `Mermaid`: BPMN non nasce come linguaggio testuale dichiarativo. Il formato di scambio è XML, e XML non lo scrive nessuno a mano, si costruisce il diagramma con un editor grafico dedicato (bpmn.io, Camunda Modeler e simili), che genera l'XML sotto. Questo richiede un po' di quelle attività di cui parlavamo all'inizio (PowerPoint), ma in un editor dedicato a questo, che fa solo questo e che è **nato** per questo.

Non è un'incoerenza rispetto a quanto detto finora, è il limite della tesi, ed è giusto segnarlo. Quando il dominio è abbastanza complesso da richiedere una notazione con semantica di business formale, riconosciuta e comprensibile anche a chi non è tecnico, lo strumento grafico dedicato resta la scelta giusta.

Va detto che esistono servizi su Internet che generano diagrammi BPMN da una descrizione testuale, ma in mezzo c'è iun layeri di IA che si porta dietro tutti i suoi limiti.

## Quando usare cosa

La maggior parte dei processi di cui parla questo blog, sequenze di passaggi con qualche condizione, sono ben rappresentati da `PlantUML` o `Mermaid`. Il vantaggio del testo vince nettamente, e non c'è ragione per complicarsi la vita con altro.

BPMN si giustifica quando il processo ha un livello di astrazione diverso, quando il livello di complessità aumenta particolarmente o quando, spesso, le azioni e le attività non sono per forza sequenziali o ci sono ritorni condizionati frequenti.
