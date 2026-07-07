---
title: Word ha vinto, ma non ha ragione
date: 2026-07-07
description: "Word non è uno strumento sbagliato, è uno strumento sproporzionato per scrivere un processo. Perché markdown costringe a pensare per struttura, non per aspetto."
draft: false
tags: [Editor, Markdown, Word, Scrittura]
---

Apri Word per scrivere un processo e la prima cosa che fai è scegliere lo stile del titolo. Poi combatti con una tabella che non si formatta come dici tu. Cominci a scrivere e ti viene in mente di fare un copia/incolla da un altro documento, peccato che lo stile è diverso. Allora cominci a chiederti se esiste un template aziendale ed effettivamente c'è, ma di tre anni fa con il logo sbagliato. Dopo 2 ore di lavoro la lista degli stili è diventata lunga come una Quaresima, doppioni a non finire, titoli che _sembrano_ uguali ma che non lo sono; poi arriva il momento in cui vuoi inserire un'immagine e lì la confusione diventa altissima, purissima... Passano altre ore: ora il documento è scritto in _tecnicolor_ per i continui copia/incolla da altri documenti, per immagini che hanno stili diversi e diagrammi che non c'entrano con lo scopo del documento. La comprensibilità è precipitata ed è tutta colpa di Bill Gates.

## No, la colpa è delle scelte

Word è uno strumento complesso che fa, principalmente, impaginazione. Non serve per redigere un testo, ma per impaginarlo. Tralasciando che ho visto fin troppe persone che non lo sanno usare e che creano solo più confusione, è anche una conseguenza della sua natura [WYSIWYG](https://en.wikipedia.org/wiki/WYSIWYG): tu vedi il risultato, ma non _cosa_ lo ha generato (e ci mancherebbe, visto quanto codice usa Word!).

![Anatomia di un file Word](https://kroki.io/plantuml/svg/eNp1k8FugzAMhu88hcVpuyC1T1Bpp90q0dNQVaVgKCKJo8RodBPvvgBdCzS9IIvf_-fkl7NzLCy3SkauqbURVijISRnSqDnlq0SwmLPQlcRZixF5IyqcGkqSBdoouv2EuKC8Vd5Pia86ePv63L_H8BvBAw1xln2QZl-eDleD7ph0Sh7jyDfdOSeL0k3GpTUZBN8M0C8Mftzekgl6hDG3EWslJ4uvpNYxqbu4nNbJ0Bx3ERaLlG2tKxfEZm6IbdLW0jfZ5kzUTOKoruMQDjo51rfpLwFTTGNPv2LxBRXGIcCobB6HWzuNvxijTZF5uGGQserZJOdah2nDcd0FkcOgUZod5lnczpIKZjXRl3m9wMzyGk76_-2jfrbcxlKOzlGiivVOZwf065JASpKAx_o4eDUxwpnYrxJQuUR4QFUzFHVZQtnqn5q0SCLUBQyuZ2_wbc0hihxb4f_EPnRhr1DWftlGDW08Q-985R_-H7j3S-s=)

Un buon modo per concentrarsi sul contenuto è liberarsi di tutto questo e occuparsi solo, appunto, del contenuto, cioè di quello che devo comunicare.

È molto vecchio, ma negli ultimi anni, grazie al suo utilizzo nell'IA, il [markdown](https://daringfireball.net/projects/markdown/) sta conoscendo una grande impennata di utilizzatori.

## Lo strumento impone la struttura, non finge

In Word puoi selezionare del testo, aumentarne il corpo, metterlo in grassetto, e a colpo d'occhio quello sembra un titolo. Ma non lo è. Strutturalmente resta un paragrafo qualunque con una formattazione diversa (e per alcuni imparare a domare gli stili di Word è già un mestiere a sé): non entra nel sommario automatico, non è navigabile, non è riconoscibile da uno script che deve convertire, indicizzare o validare il documento. È un titolo da vedere, ma non "funziona" da titolo.

In `markdown` questo non è possibile. `##` è un titolo di secondo livello. Punto. Non puoi _fingere_ una gerarchia — o la dichiari esplicitamente, o quel testo resta un paragrafo. Questo obbliga a decidere la struttura del documento prima di scrivere il contenuto, non dopo per sistemarne l'aspetto: quante sezioni ha questo processo, quali sono i sottopassaggi, cosa è primario e cosa è di dettaglio. La domanda "come strutturo questo?" viene posta prima, non aggirata con un +2 di dimensione del font.

Non è un dettaglio tecnico. Esistono studi[^1] che sostengono che la lingua che usiamo plasma la struttura del pensiero (semplifico parecchio). Lo stesso vale, su scala più piccola, per lo strumento con cui scriviamo: se lo strumento permette di _sembrare_ strutturato senza esserlo, quella scorciatoia verrà presa. Se lo strumento non la permette, la struttura va pensata davvero.

[^1]: Frana, I., Panzeri, F. (2024). _Lingua e pensiero. Teorie e ricerca sperimentale_. Carocci.

Quindi, scrivendo il tipo di documentazione di cui parliamo in questo blog, è un vantaggio non da poco servirsi di uno strumento che guida, in parte, il nostro ragionamento, il nostro modo di implementare e strutturare il contenuto. Essendo, di base, un file di testo, non c'è testo nascosto, non posso perdere informazioni, è tutto sequenziale e scritto "dritto-per-dritto". Questo forza la nostra scrittura ad essere **rigorosa**. Può non piacere, ma a livello di contenuto è decisamente un vantaggio.

### Editor `markdown`

L'elenco degli editor markdown è sterminato. Non solo: è sterminato l'elenco di elenchi di editors, quindi qui non ne faremo cenno, solo un riferimento a [questa](https://md-handbook.com/markdown-editors/) breve lista che racchiude alcuni editor (senza contare tutti quegli strumenti che usano `markdown` come base per integrare altri strumenti o linguaggi). Ma sarà facile trovarne uno che fa al caso nostro con le caratteristiche a cui siamo abituati. Forse bisognerà fare un po' di test, ma uno si trova di sicuro.

### Output diversi

Un altro vantaggio è che -- con pochi passaggi -- da uno stesso file `.md` si possono produrre file diversi: PDF. HTML, Word, ... i passaggio non sono sempre immediati, ma il vantaggio è molto alto in alcuni contesti.

## Il contenuto sopravvive allo strumento

Senza contare il fatto che un file `.md` scritto nel 2010 si apre oggi e produce lo stesso identico risultato. Un file `.docx` dipende da come Word, LibreOffice o Google Docs interpretano in quel momento quello specifico XML — e lo hai visto tu stesso più sopra (per non parlare di tutte le volte che uno stesso file transita tra editor diversi, tra Word, Google Docs, etc.): la stessa "anatomia" che genera confusione quando un file passa da una macchina all'altra è la stessa ragione per cui un `.docx` di qualche anno fa può aprirsi con stili diversi da quelli con cui è stato scritto.

Un file Word (o qualsiasi altro XML) porta con sé più informazioni di quelle che vedi a schermo — versioni precedenti non ripulite, commenti rimasti, metadata. Non è il tema di questo post, ma è un altro motivo per cui un file di testo puro resta la scelta più semplice.

## La scelta giusta

Quindi, come sempre, la scelta giusta è la nostra, è quella che ci fa raggiungere il risultato, ma -- potendo scegliere -- utilizziamo quella che è nostra alleata, non la scelta che ci impone ancora **più** lavoro.
