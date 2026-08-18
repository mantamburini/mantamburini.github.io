# AGENTS.md — Blog Instrumenta

Contesto per agenti LLM (CLI, opencode, ecc.) che operano in questa repo, e per le sessioni di chat dedicate a questo progetto. Leggere prima di qualsiasi modifica o di iniziare a scrivere.

Questo è l'unico documento di riferimento attivo per il progetto: la nota di pianificazione iniziale (naming, brainstorming, decisioni sul tema) è stata chiusa e archiviata nel vault una volta esaurita la fase di setup — resta consultabile lì per il "perché" storico delle scelte, ma non va più tenuta sincronizzata con questo file.

## 1. Stato attuale

Repo `mantamburini.github.io`, pubblicata via GitHub Actions → GitHub Pages. Riavvio completo di un vecchio blog (PaperMod, poi Hugo Theme Stack, poi LoveIt) la cui impostazione è stata abbandonata. Tutto il materiale precedente è stato rimosso: la repo è stata ricostruita da zero con il tema Hugo Bear.

Struttura attuale:

- **Home** (`content/_index.md`): contiene il testo "Chi sono", recuperato dal vecchio sito. Non esiste più una pagina `/about/`.
- **Post**: in `content/blog/`, categorizzati via tag. Nessuna sezione tematica.
- **Menu** in `hugo.toml`: Home, Blog, Tags.

Fase di setup (naming, scelta tema, sottotitolo, albero editoriale) conclusa. Da qui in avanti il lavoro è produzione: scrittura ed editing dei post.

## 2. Cosa deve diventare

Sito personale: **Instrumenta**. Brain dump diretto di 20+ anni di esperienza in IT Operations, ITSM, Service Delivery (ruoli da Head of Operations — SPS Global, Berlin Packaging, Sopra Steria, Beta 80 Group). Target: manager in generale, non solo IT.

Non è un blog consulenziale da LinkedIn. Non aneddoti simpatici. Contenuto su decisioni sbagliate, persone che hanno insegnato qualcosa nel modo peggiore, processi saltati, convinzioni rivelatesi sbagliate col tempo.

Il nome viene dal capitolo IV della Regola di San Benedetto (*"Quae sunt instrumenta bonorum operum"*): gli strumenti concreti da esercitare ogni giorno, con costanza. Non un elenco di precetti dall'alto — coerente con "diretto, pratico, senza pretesa di guru".

Sottotitolo: **"Gli strumenti del mestiere, usati ogni giorno"** — impostato in `hugo.toml` (`params.description`).

## 3. Chi sono / Home

Il testo "Chi sono" è stato recuperato dal vecchio sito e vive nel corpo di `content/_index.md` (non esiste più una pagina dedicata). Regole:

- Non riscriverlo da zero, non inventare fatti biografici.
- Modificarlo solo per coerenza col tono (§6), senza cambiare i fatti.

## 4. Setup tecnico

- **Generatore**: Hugo (versione allineata al workflow, oggi 0.164.0+extended).
- **Tema**: **Hugo Bear** (`janraasch/hugo-bearblog`), installato come git submodule in `themes/hugo-bearblog`. Non proporre alternative, non installare Hugo Terminal.
- **Config**: `hugo.toml` minimale Bear. Usa `locale = "it-IT"`, non `languageCode` (deprecato da Hugo 0.158). Sottotitolo in `params.description`.
- **Pipeline**: GitHub Actions → GitHub Pages, invariata. Il workflow fa `submodules: recursive`, quindi il tema submodule viene recuperato da solo.
- **Dominio**: nessun dominio custom. Resta `mantamburini.github.io`. Il "flavour tecnico" dell'URL GitHub Pages è voluto, non un difetto da correggere.
- **Editor di riferimento**: nvim (non serve setup particolare lato repo).

> **Nota importante**: riferirsi scrupolosamente alle istruzioni indicate qui: https://github.com/janraasch/hugo-bearblog quando ci sarà il caso di creare nuovi *archetypes* e/o sezioni del sito

## 5. Struttura dei contenuti

Decisione presa in sessione: **niente sezioni tematiche**. Un tentativo a 7 sezioni è stato abbandonato; i contenuti sono organizzati per **tag**.

- I post vivono in `content/blog/` (struttura nativa del tema Bear: solo lì il tipo è `blog` e il tema mostra la data; in `content/posts/` la data sparirebbe).
- Creare un post con `hugo new blog/nome-post.md`: usa `archetypes/blog.md` a livello sito, che genera front matter YAML minimo (`title`, `date`, `draft`, `tags`). Gli archetype nativi del tema producono TOML, per questo esiste l'override.
- Un post con `draft: true` nel front matter non viene pubblicato. Per vederlo in locale: `hugo server -D`.
- I tag funzionano coi default di Hugo, senza configurazione extra: pagina `/tags/`, pagine `/tags/<tag>/`, link `#tag` nei post e nella lista `/blog/`.
- Front matter minimo: `title`, `date`, `draft`, `tags`.

Le sette aree che seguono **non sono sezioni del sito**: sono il backlog editoriale da cui derivano i tag e i temi dei post. Guida flessibile, non vincolo rigido — soprattutto in fase di scelta dei contenuti.

1. **Processi**
   - Perché lavorare per processi (sicurezza, ripetibilità, economia)
   - I trigger per le eccezioni
   - Misurazioni, KPI, SLA
   - Efficientamento
2. **Persone**
   - Gestione operativa del team
   - Percorsi di crescita e responsabilità
   - Assunzioni sbagliate
   - Gestione della crisi/incidente
3. **Comunicazione**
   - Verso il cliente/fornitore
   - Verso il basso (strategia condivisa)
   - Branding nei documenti e template
4. **Economia e negoziazione**
   - Accordi e contratti
   - Vendor management
   - Produttività delle commesse
   - Budget e negoziazione interna
5. **Cambiamento organizzativo**
   - Riorganizzazioni, fusioni, cambi di management sopra di te
6. **Reportistica**
   - Fonti dati e come collegarcisi
   - Scelta dello span temporale
   - Cosa presentare per dire cosa
   - Come presentare (formato, livello di dettaglio)
7. **Forma mentis / strumenti**
   - Perché markdown (e la forma mentis dietro la scelta)
   - Semplicità come scelta, non come limite

La sezione 6 (Reportistica) è volutamente più densa delle altre — contiene sotto-temi tecnici specifici che le altre non hanno. Intenzionale, non un difetto della lista.

### 5.1. Referral images

Le immagini sono prese generalmente da unsplash.com. Utilizzare rigorosamente le loro linee guida di referral, compreso `utm_source` e `utm_medium`.

## 6. Stile di scrittura — vincolante per qualsiasi contenuto generato

Se produci testo di esempio, placeholder o contenuto reale per le pagine, applica queste regole (derivate dalla skill personale di Marcello, `anti-ai-writing-style`):

- Niente aperture tipo "Ottima domanda", "Bentornati", entusiasmo posticcio.
- Niente costruzioni "Non è solo X, è Y" o "X non è solo un tool, è un mindset".
- Niente parole da marketing/consulenza: *leverage*, *robust*, *seamlessly*, *holistic*, *comprehensive*, *cutting-edge*, *game-changer*, ecc. (e i loro equivalenti italiani: "sinergie", "a 360 gradi", "best practice" usato come riempitivo).
- Niente chiusure tipo "Spero che questo sia utile" o inviti a "esplorare oltre".
- Frasi dirette, un'idea per paragrafo. Se qualcosa è complesso, spiega cosa lo rende complesso — non limitarti a etichettarlo come tale.
- Nessuna emoji.
- Questo vincolo si applica ancora più rigidamente qui rispetto ad altri contesti, per via del tono richiesto dal sito (diretto, senza pretesa di guru, niente linguaggio da consulente).

Se generi solo struttura/scaffolding (file `_index.md` con front matter e titolo, senza corpo) questa sezione si applica comunque a qualsiasi testo descrittivo che scrivi.

## 7. Principi operativi (da rispettare in ogni scelta tecnica)

- **KISS**: se una configurazione, un plugin o uno shortcode non è strettamente necessario, non aggiungerlo. Niente overengineering del setup Hugo.
- Markdown-first: contenuti in `.md` semplice, front matter YAML minimo (`title`, `date`, `draft`, `tags` — non serve altro a meno che il tema Bear lo richieda).
- Workflow reale: la scrittura avviene in una cartella locale dentro un repo Codeberg esistente, poi viene pushata su GitHub per la pubblicazione. La CLI opera direttamente nella cartella del repo GitHub Pages — non serve replicare la sincronizzazione Codeberg, è un processo manuale di Marcello a monte.
- Se una decisione tecnica non è coperta da questo documento, non improvvisare in modo silenzioso: segnala la scelta fatta e perché, così Marcello può correggerla.

## 8. Convenzioni operative

- Il deploy avviene al push su `main` via GitHub Actions. Non committare/pubblicare senza richiesta esplicita di Marcello.
- Prima di un commit, verificare la build locale (`hugo`) e che eventuali post `draft: true` non compaiano in `public/`.
- Se una scelta non è coperta da questo documento, segnalarla invece di decidere in silenzio (§7).

## 9. Metodo editoriale — come lavorare sui singoli post

Marcello scrive tutti i contenuti. Il ruolo dell'agente/di Claude è **sparring partner ed editor**, non autore: non riscrivere un post da zero al posto suo. Il lavoro è identificare problemi strutturali e discuterli, non produrre la prosa finale — quella arriva sempre da una revisione di Marcello stesso.

**Disciplina editoriale principale: scena concreta, non principio dichiarato.**
Mostrare un episodio invece di spiegarlo, lasciando che sia il lettore a trarre la conclusione, non l'autore a fornirla in chiaro.

**Due difetti strutturali da segnalare quando compaiono, con nomi propri:**

- *Astrazione universalizzante* (il problema del guru): generalizzare un episodio in una lezione o un principio esplicito.
- *Enumerazione esplicativa* (il problema del framework): organizzare la riflessione in blocchi titolati che somigliano a un deliverable da consulente.

Quando uno dei due compare, segnalarlo e discuterne concettualmente con Marcello — non correggere direttamente il testo al posto suo.

**Un episodio per articolo.** Materiale in più (aneddoti, dettagli, digressioni) si tiene da parte per articoli futuri, non si stipa nel pezzo corrente per renderlo "completo".

**"Corto vs lungo" è la cornice sbagliata.** La distinzione reale è tra un singolo episodio e un processo pluriennale — è quello, non la lunghezza in parole, a determinare la forma dell'articolo.
