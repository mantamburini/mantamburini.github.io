---
title: "Chiedi a Mario"
date: 2026-05-31
draft: false
tags: ["metodologia", "processi"]
description: "In ogni reparto c'è qualcuno che sa tutto. Il problema non è lui, è che quella conoscenza non è mai stata scritta da nessuna parte."
---

Lunedì mattina. Un collega si ferma alla tua scrivania o ti manda un messaggio su Teams.

>"Come si fa questa cosa?"  
>"Chi se ne occupa?"  
>"Che passaggi devo seguire?"  
>"Come sono gli accordi con il fornitore?"

La risposta di solito è: "Chiedi a Mario."

## Mario funziona, fino a quando non funziona più

Mario è il collega che c'è da quindici anni. Ha visto arrivare tre CTO, due migrazioni di datacenter e un progetto ERP che nessuno vuole ricordare. Sa come funziona tutto, risponde sempre, raramente sbaglia.

Il problema non è Mario. Il problema è che quella conoscenza esiste solo nella sua testa.

Funziona finché Mario è alla scrivania. Smette di funzionare quando Mario va in ferie, si ammala, cambia lavoro, o — nel caso migliore — viene promosso e smette di occuparsi delle cose operative che gestiva prima.

A quel punto le quattro domande di lunedì mattina non hanno risposta. O peggio: hanno risposte diverse a seconda di chi si chiede.

## Cosa succede

Quando non c'è un processo documentato, la conoscenza non sparisce, ma viene reinterpretata, riscritta (non scritta, ma "me l'ha detto Giulio, il cugino di Mario"), modificata a seconda delle necessità individuali. Si frammenta tra le persone che erano in sala quando si è deciso qualcosa, nelle email di tre anni fa che nessuno riesce a trovare, nei file su *SharePoint* che hanno nomi tipo `procedura_DEFINITIVA_v3_USARE_QUESTA.docx` e che, essendo un file Word, tutti si sentiranno autorizzati ad editare. 

![Mario lo sa, se c'è](https://kroki.io/plantuml/svg/eNpFkE1uAjEMhfc5hcVq2HCAmQUgpEosQPQIVsYBq4mN8tMFJ2LRW3CxOlOJrl70_Pm9yLtSMdeWolsebvxsGH0TBX9jmglWB00EhSHgdjU5DjCcMLPC6wks0EJgz7pdQ72RwFBeP2sHMB76NgPCAk_d-mjyYBWcHMVCMIgu5JlK6X1RoWAHg-YvMP1PsZ4rZ30P8Yosf8RRvknqskcy96kz5eDGS7aP18pgAbP6ljqXaXKilQw_q7x9yshmJeSNyWl_3PQUWMhxHyPCPWspnHB0dorMXhOLZ-stVe9uZ7Td8Be-bGx0)

Chi arriva nuovo non sa dove cercare. Chi c'è da poco sa che esiste qualcosa ma non sa se è aggiornato. Chi c'è da tanto sa come funziona ma non l'ha mai scritto perché "si sa come funziona, figurati se mi metto a scriverlo".

Il risultato: ogni volta che qualcuno fa una cosa per la prima volta, riparte quasi da zero. Chiede in giro, riceve risposte parziali, ricostruisce il percorso per tentativi. Poi lo dimentica, perché non lo ha scritto da nessuna parte. E il ciclo ricomincia spesso dopo che è stato eseguito male o sbagliato.

## Sembra che evitare un'attività come la scrittura costi meno

Non è un problema astratto di "gestione della conoscenza". Non scrivere ha un costo concreto.

Ogni volta che qualcuno passa un'ora a ricostruire qualcosa che esiste già nella testa di un collega, quella è un'ora persa (persa per chi sta ricostruendo e persa per Mario, che deve interrompersi). Ogni volta che un processo viene eseguito in modo diverso da due persone diverse perché nessuno ha mai scritto qual è il modo corretto, si introduce variabilità che prima o poi produce un errore. Ogni volta che un nuovo collega impiega tre mesi invece di tre settimane per diventare operativo, il delta è in gran parte spiegato dall'assenza di documentazione.

Un reparto che dipende da Mario per funzionare non scala. Non regge il turnover. Non sopravvive alla crescita.

## Documentare non è produrre carta

La reazione comune a questo punto è: "Sì, ma scrivere i processi richiede tempo, nessuno li aggiorna, finiscono nel cassetto. E nessuno li guarda."

È vero. Succede spesso. Ma non è un problema della documentazione, è un problema di metodo.

Un documento di processo che finisce nel cassetto ha quasi sempre uno di questi difetti: è scritto al livello sbagliato di dettaglio, non ha un owner chiaro, non è stato pensato per il pubblico che dovrebbe usarlo, oppure è stato prodotto una volta sola come esercizio burocratico senza nessun piano di manutenzione. Spesso nessuno ha negli obiettivi personali l'aggiornamento della documentazione.

Documentare un processo nel modo giusto significa rispondere a quattro domande precise:

- **Cosa si fa**: i passi, in ordine, con le eccezioni rilevanti (magari avendo anche un documento di *procedura* e non solo di *processo*)
- **Chi lo fa**: ruoli, non nomi — perché i nomi cambiano
- **Quando e perché**: i trigger, i confini, le condizioni di ingresso e uscita
- **Come si sa che è fatto bene**: i criteri di completamento o di escalation

Un documento che risponde a queste quattro domande ha una probabilità concreta di essere usato. Uno che non risponde a nessuna delle quattro è solo carta.

## Di cosa parla questo blog

Non di strumenti. O meglio: degli strumenti parlerà, ma come conseguenza di scelte metodologiche, non come punto di partenza.

Parla di come si decide cosa merita di essere documentato e cosa no. Di come si sceglie il livello di dettaglio giusto. Di come si assegna la responsabilità di un documento in modo che qualcuno la senta davvero. Di come si costruisce un sistema che si mantiene nel tempo invece di degradare appena smette di essere un progetto attivo.

Per chi gestisce un reparto di una azienda e ha già capito che Mario è un rischio, ma non ha ancora trovato un modo pratico per ridurlo.
