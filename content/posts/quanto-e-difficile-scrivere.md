---
title: "Quanto è difficile scrivere!"
date: 2026-06-15
description: Un processo che non viene seguito è quasi sempre un problema di scrittura, non di compliance. La differenza tra scrivere per essere letti e scrivere per essere eseguiti.
draft: false
tags: ["metodologia", "processi", "scrittura"]
---

# Quanto è difficile scrivere!

Un collega apre il documento con la procedura di *escalation*, lo legge, e gestisce il ticket in modo diverso da come hai sempre fatto tu, eppure non ha sbagliato niente… semplicemente ha *interpretato* in maniera differente quello che c'è scritto. Non c'è qualcuno che ha **torto** e/o qualcuno che ha **ragione**, è che il documento, semplicemente, è scritto male, perché lascia spazio a interpretazioni.

Succede, purtroppo. Di solito, si attribuisce la cosa a distrazione, superficialità, o "tanto lo so già"; ma la realtà è che - spesso - i documenti sono scritti male, come dicevamo, dando per scontate troppe cose ("tanto questo lo sanno tutti") o usando parole troppo generiche. Quindi, l'ultimo che arriva, poraccio, è quello che ha torto. O semplicemente è quello grazie al quale il problema salta all'occhio.

## Il problema non è chi legge

Scrivere un processo o una procedura pensando a come lo eseguiresti tu è l'errore più comune e meno visibile nella documentazione. Chi scrive conosce già il contesto, i casi limite, le convenzioni implicite, quello che il cliente si aspetta, come il sistema dovrebbe funzionare o come invece funziona temporaneamente, ma "tanto poi torna come prima". Riempie i buchi senza accorgersene. Il testo che produce è completo per lui, ma ambiguo per chiunque altro.

Il risultato pratico è che lo stesso processo, dato a cinque persone diverse, produce cinque esecuzioni leggermente diverse (o sei, in alcuni casi!). Non per malafede. Per ambiguità.

![](https://kroki.io/plantuml/svg/eNptjzEOwkAMBPt7xYpnhIJI0FBQICR6684kFsk5cpy8iX_wMS5RGhCdtTu71tajk_nUd2E9QrU7d3CJT3bMwpkRW5lG3e1DVmeYNK1XONGiHwp-X6GGRxdXcHZTCJz7QTAYz1KMn_B1om5DlobbAmrkVH5pz0gEilEt_c9tXkkeW-GkIFzIRL_ZVcL7Bcl4sAmXfTqEmnMqYz8glFV7)

Per questo la documentazione non è solo un problema organizzativo, ma anche un problema di scrittura, cioè di "saper scrivere".

## Scrivere per essere eseguiti

Scrivere per essere letti e scrivere per essere eseguiti sono due cose diverse.

Una relazione o una email si leggono dall'inizio alla fine (di solito) e producono una comprensione generale. Qualche ambiguità è tollerabile, anzi potrebbe far parte del gioco: ci sono cose in quei tipi di documenti che volutamente vengono lasciate alla interpretazione di chi legge.

Un processo si esegue passo per passo, spesso sotto pressione, spesso da chi non ha tempo di chiedere. Ogni ambiguità è un punto in cui l'esecuzione può deviare (e di deviazione in deviazione, può diventare davvero qualcosa di molto diverso). Dietro ogni ambiguità non chiarita c'è il rischio che il lettore, magari inconsapevolmente, possa diventare creativo, magari anche per l'imbarazzo di chiedere.

Scrivere un processo in modo che venga eseguito come previsto richiede criteri diversi da quelli che bastano per una buona email. E richiede **tempo**, pazienza, immedesimazione, richiede che si pensi a tutti i casi limite o dubbi che sono già capitato o che potrebbero capitare. Oppure richiedere che venga scritto in maniera talmente rigorosa, che casi limite non possano esistere.

## I criteri che contano

**Completo.** Tutto quello che serve per eseguire il processo è nel documento. Nessuna conoscenza implicita, nessun rimando a "come si è sempre fatto", nessuna dipendenza da chi ha scritto il documento. Al limite rimandi ad altri documenti. Innanzitutto lo *scopo* del processo: "perché si fa questa cosa?"

**Chiaro.** Una frase, un'azione. Soggetto esplicito. Niente costruzioni passive che nascondono chi deve fare cosa. "Il ticket viene chiuso" non dice chi lo chiude—"Il responsabile del servizio chiude il ticket" sì.

**Essenziale.** Solo quello che serve per eseguire. Il contesto storico, le motivazioni, i retroscena della decisione appartengono altrove—in un documento di policy, in una nota a piè di pagina, non nel corpo del processo. Ogni riga in più è una riga che distrae.

**Non interpretabile.** Il testo produce un'unica esecuzione possibile. Se una frase può essere letta in due modi, verrà letta in due modi. Riscriverla non è un optional.

## Quando le parole non bastano

Ci sono parti di un processo che le parole descrivono male per natura: flussi con condizioni multiple, decisioni a cascata, interazioni tra ruoli diversi.

In questi casi un diagramma non è una decorazione, ma la versione più precisa del processo. Un lettore che non capisce il testo capisce spesso il diagramma. E anche chi capisce il testo usa il diagramma per verificare di aver capito la cosa giusta.

Non serve uno strumento particolare. Serve la disciplina di disegnare il flusso prima di scriverlo, e di aggiornare il disegno quando il processo cambia.

**Scrivere bene** non è una dote. È una *competenza* con criteri precisi, che si impara con la pratica e con l'abitudine a rileggere quello che si scrive come se non si sapesse già come va a finire.

È anche la competenza più sottovalutata nella documentazione tecnica. Perché tutti sanno scrivere, nel senso che tutti sanno mettere parole in fila. Ma mettere parole in fila in modo che qualcun altro esegua esattamente quello che avevi in mente è un'altra cosa.
